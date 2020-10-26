---
title:  "MongoDB Setup"
permalink: /howto/mongodb-setup/
layout: default
date:   2018-04-18
category:
  - howto
tags:
  - mongodb
  - server
---

## Setting up a standard installation of MongoDB on OS X

These instructions are based on our specific use, but should work in general for MongoDB installations under OS X (tested up to 10.13.4 "High Sierra").

### Install the MongoDB binary

MongoDB is available from the [download center](https://www.mongodb.com/download-center#community) (community version); only there one can see which version is the most recent (there does not seem to be an "latest" endpoint).

The installation itself (including download) proceeds like this:

```bash
mkdir mongodb
curl -O https://fastdl.mongodb.org/osx/mongodb-macos-x86_64-4.2.0.tgz
tar -xvf mongodb-macos-x86_64-4.2.0.tgz -C ./mongodb --strip-components 1
sudo mkdir -p /usr/local/bin
sudo cp mongodb/bin/* /usr/local/bin/
sudo touch /var/log/mongodb.log
```


The databases have to go somewhere; one example with system-wide availability would be `/data/db/mongodb/`. The same path has to be used in the configuration below (`--dbpath`).

```bash
sudo mkdir -p /Library/MongoDB
sudo chmod g+w /Library/MongoDB
sudo chmod o+w /Library/MongoDB
```

The following installation steps are only required for first time installations.

### Create a launch item

The last point is just to use a standard place for the DB files. This has to be reflected in the launch file, which in this case is saved as /Library/LaunchDaemons/org.mongo.mongod.plist. One has to write this as root, e.g. using

```bash
sudo nano /Library/LaunchDaemons/org.mongo.mongod.plist
```
... and paste the following content; then CTRL-O

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
   <dict>
      <key>Label</key>
         <string>org.mongo.mongod</string>
      <key>RunAtLoad</key>
         <true/>
      <key>ProgramArguments</key>
         <array>
            <string>/usr/local/bin/mongod</string>
            <string>--dbpath</string>
            <string>/Library/MongoDB/</string>
            <string>--logpath</string>
            <string>/var/log/mongodb.log</string>
            <string>--bind_ip</string>
            <string>127.0.0.1</string>
         </array>
   </dict>
</plist>
```

Now the launch file has to be activated; it will start mongos and keep it alive.

```bash
sudo chown root:wheel /Library/LaunchDaemons/org.mongo.mongod.plist
sudo launchctl load /Library/LaunchDaemons/org.mongo.mongod.plist
sudo launchctl start org.mongo.mongo
```

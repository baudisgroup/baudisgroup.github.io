---
template: post.html
title: "Migrating the Site's Server"
description: "Increasing data sovereignity..."
template: post.html 
authors:
  - '@mbaudis'
date: 2026-02-17
pdf_file_name:
links:
  - '[Too much Copilot...](https://www.heise.de/en/news/Too-much-Copilot-Gentoo-switches-from-GitHub-to-Codeberg-11179401.html)'
---

We are in the process of migrating the site from Github pages to self hosting (on
Progenetix server instances). At the moment the site's source is still hosted at
Github but the build process & hosting are already running on our own infrastructure.

Particularly, all article & presentation PDF files are now accessed through the
`docs.baudisgroup.org` subdomain which is hosted on our own server; please adjust old
URLs accordingly (_i.e._ change `https://baudisgroup.org/pdf/...` to `https://docs.baudisgroup.org/pdf/...`).
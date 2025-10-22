---
title: Installing `vrs-python` on Mac OS (non-containerized)
---

This is a simplified (e.g. no UTA/transcript support), non-containerized
installation procedure for [vrs-python](https://github.com/ga4gh/vrs-python) on Mac OS. It is based on the 
[documentation](https://github.com/ga4gh/vrs-python/blob/main/README.md) there as well as on some testing when extending [`bycon`](https://bycon.progenetix.org)
for VRSification (e.g. by using & extending the `translator.py` module).

```
brew install libpq postgresql@14
brew services start postgresql@14
pip3 install 'ga4gh.vrs[extras]' seqrepo
brew install rsync
brew link rsync
which rsync
```

... should give you /opt/homebrew/bin/rsync but if not you can force it anyway…
<!--more-->

??? note "pysam Error"

    Some versions of `pysam` (_i.e._ 0.23.0) have a `Cython` based problem. This
    was fixed in pysam >-0.23.1; at the time pip wasn't updated yet one could
    download from source & install, e.g.:

    <https://github.com/pysam-developers/pysam/releases/tag/v0.23.3>

    
    ```
    cd ~/Downloads/pysam-0.23.3 &&
    python3 -m build --no-isolation --sdist . &&
    pip3 install ./dist/*tar.gz --no-index --no-build-isolation --break-system-packages  
    ```

```
seqrepo --rsync-exe /opt/homebrew/bin/rsync list-remote-instances
```

... should give you a list; take the latest, e.g.

```
… 
2024-05-23
2024-12-20
```

… from which we take the last:

```
export SEQREPO_VERSION=2024-12-20
export SEQREPO_ROOT_DIR="/Users/Shared/seqrepo"
```

```
sudo mkdir -p $SEQREPO_ROOT_DIR
sudo chown -R root:staff $SEQREPO_ROOT_DIR
sudo chmod -R 775 $SEQREPO_ROOT_DIR
seqrepo --rsync-exe /opt/homebrew/bin/rsync pull -i $SEQREPO_VERSION
seqrepo --rsync-exe /opt/homebrew/bin/rsync update-latest 
```

Note: checking the progress in another terminal can be done with

```
du -hs $SEQREPO_ROOT_DIR
```

... so you know when the ~13.7GB will be done.

## Python use

```
from ga4gh.vrs.dataproxy import create_dataproxy
seqrepo_rest_service_url = 'seqrepo+file:///Users/Shared/seqrepo/2024-12-20'

seqrepo_dataproxy = create_dataproxy(uri=seqrepo_rest_service_url)
```

Now one can e.g. translate sequences:

```
seqrepo_dataproxy.translate_sequence_identifier("refseq:NC_000007.14", "ga4gh")
seqrepo_dataproxy.translate_sequence_identifier("GRCh38:7", "refseq")
```

----

Last change 2025-08-28 by @mbaudis
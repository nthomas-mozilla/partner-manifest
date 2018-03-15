mozilla-EME-free-manifests
==========================

This repo contains the manifest of other repositories needed to repack mozilla-EME-free builds.

Prereqs
-------

```
brew install p7zip
```

Setup
-----

```
mkdir repacks && cd repacks
curl https://raw.githubusercontent.com/mozilla/git-repo/master/repo > ./repo
chmod u+x ./repo
./repo init --no-repo-verify -u git@github.com:mozilla-partners/mozilla-EME-free-manifest.git
./repo sync
```

Build
-----

This will build unsigned repacks that you could use to do initial QA or verify your repack config.

```
VERSION=45.0.2
cd scripts
python partner-repacks.py -v ${VERSION}
```

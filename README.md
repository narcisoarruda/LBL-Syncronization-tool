LinkedBrainz Live tool
==========

[LinkedBrainz Live](http://www.arida.ufc.br/livesynrdbrdf/) continuously [generates zipped N-Triples files](http://virtuoso.mooo.com/files/changesets/) containing added/deleted triples upon its run.
This tool starts downloading those files and updates a local Virtuoso triple store.

VOS Setup
=========
DBpedia Live triple store update happens we have the following enabled:
  1. `http://www.arida.ufc.br/livesynrdbrdf/linkedbrainzlive.html`: contains real time updated data from MusicBrainz
 
Execution
=========
In order to execute from source, download the code from the repo
`git clone https://github.com/narcisoarruda/LBL-Syncronization-tool.git`

  1. Setup your VOS instance and `mirror-live.ini` file.
  2. Download and load the [latest dump](http://virtuoso.mooo.com/files/changesets/dumps/)
  3. Copy `lastDownloadDate.dat.default' to `lastDownloadDate.dat` and adapt the date according to the dump file
  3. run one of the scripts in the `bin/` folder
    1. `sh bin/liveSync.sh` script that applies existing triple patches and waits until new ones get published 
    2. `sh bin/liveSyncOnce.sh Onetime` script that applies existing triple patches and exits.
    3. `sh bin/ontologySync.sh` script that keeps the DBpedia ontology up-to-date
    4. `sh bin/ontologySync.sh Onetime` script that updates the DBpedia ontology to the latest version and exists

Jar files are not distributed at the moment but will be on request.

Dependencies
=========
  1. Maven 3
  2. Java 7

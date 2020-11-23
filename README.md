rsp-data
--------

Data for https://github.com/SchweizerischeBundesbahnen/RSP

Requires [Git Large File Storage (LFS)](https://git-lfs.github.com/)

Sync files
```shell script
cd rsp-data
export AGENDA=HUGE
mkdir -p ./DENSITY_VARIATION_EXPERIMENTS_${AGENDA}_ENV
rsync -a --include "experiment_agenda.pkl" --exclude "*.pkl" ../rsp/DENSITY_VARIATION_EXPERIMENTS_${AGENDA}_ENV/ ./DENSITY_VARIATION_EXPERIMENTS_${AGENDA}_ENV
export AGENDA=LARGE
mkdir -p ./DENSITY_VARIATION_EXPERIMENTS_${AGENDA}_ENV
rsync -a --include "experiment_agenda.pkl" --exclude "*.pkl" ../rsp/DENSITY_VARIATION_EXPERIMENTS_${AGENDA}_ENV/ ./DENSITY_VARIATION_EXPERIMENTS_${AGENDA}_ENV

mkdir -p "PUBLICATION_DATA"
rsync -a --include "experiment_agenda.pkl" --exclude "*.pkl" ../rsp/PUBLICATION_DATA/ ./PUBLICATION_DATA
git add PUBLICATION_DATA
```
 

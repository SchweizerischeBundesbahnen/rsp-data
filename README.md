rsp-data
--------

Data for https://github.com/SchweizerischeBundesbahnen/RSP

Requires [Git Large File Storage (LFS)](https://git-lfs.github.com/)

Sync files
```shell script
cd rsp-data
export AGENDA=HUGE
mkdir -p ./DENSITY_VARIATION_EXPERIMENTS_${AGENDA}_ENV/infras
rsync -a  ../rsp/DENSITY_VARIATION_EXPERIMENTS_${AGENDA}_ENV/infras ./DENSITY_VARIATION_EXPERIMENTS_${AGENDA}_ENV/infras
rsync -a --include "experiment_agenda.pkl" --exclude "*.pkl" ../rsp/DENSITY_VARIATION_EXPERIMENTS_${AGENDA}_ENV/ ./DENSITY_VARIATION_EXPERIMENTS_${AGENDA}_ENV
export AGENDA=LARGE
mkdir -p ./DENSITY_VARIATION_EXPERIMENTS_${AGENDA}_ENV/infra
rsync -a  ../rsp/DENSITY_VARIATION_EXPERIMENTS_${AGENDA}_ENV/infras ./DENSITY_VARIATION_EXPERIMENTS_${AGENDA}_ENV/infras
rsync -a --include "experiment_agenda.pkl" --exclude "*.pkl" ../rsp/DENSITY_VARIATION_EXPERIMENTS_${AGENDA}_ENV/ ./DENSITY_VARIATION_EXPERIMENTS_${AGENDA}_ENV

mkdir -p "PUBLICATION_DATA/infra"
rsync -a  ../rsp/PUBLICATION_DATA/infras ./PUBLICATION_DATA/infras
rsync -a --include "experiment_agenda.pkl" --exclude "*.pkl" ../rsp/PUBLICATION_DATA/ ./PUBLICATION_DATA
git add PUBLICATION_DATA
```

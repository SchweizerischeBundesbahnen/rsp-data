rsp-data
--------

Data for https://github.com/SchweizerischeBundesbahnen/RSP

Requires [Git Large File Storage (LFS)](https://git-lfs.github.com/)

Sync files on AWS:
```shell script
cd rsp-data
export AGENDA=HUGE
mkdir -p ./DENSITY_VARIATION_EXPERIMENTS_${AGENDA}_ENV/infra
rsync -a  ../rsp/DENSITY_VARIATION_EXPERIMENTS_${AGENDA}_ENV/infra ./DENSITY_VARIATION_EXPERIMENTS_${AGENDA}_ENV/infra
rsync -a --include "experiment_agenda.pkl" --exclude "*.pkl" ../rsp/DENSITY_VARIATION_EXPERIMENTS_${AGENDA}_ENV/ ./DENSITY_VARIATION_EXPERIMENTS_${AGENDA}_ENV
export AGENDA=LARGE
mkdir -p ./DENSITY_VARIATION_EXPERIMENTS_${AGENDA}_ENV/infra
rsync -a  ../rsp/DENSITY_VARIATION_EXPERIMENTS_${AGENDA}_ENV/infra ./DENSITY_VARIATION_EXPERIMENTS_${AGENDA}_ENV/infra
rsync -a --include "experiment_agenda.pkl" --exclude "*.pkl" ../rsp/DENSITY_VARIATION_EXPERIMENTS_${AGENDA}_ENV/ ./DENSITY_VARIATION_EXPERIMENTS_${AGENDA}_ENV

mkdir -p "PUBLICATION_DATA/infra"
rsync -a  ../rsp/PUBLICATION_DATA/infra ./PUBLICATION_DATA/infra
rsync -a --include "experiment_agenda.pkl" --exclude "*.pkl" ../rsp/PUBLICATION_DATA/ ./PUBLICATION_DATA
git add PUBLICATION_DATA
```

Check out single file locally:
```shell script
git lfs pull -I PUBLICATION_DATA/infra/000/infratructure.pkl
```
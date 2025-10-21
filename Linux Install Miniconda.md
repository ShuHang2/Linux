# Miniconda

## Install
mkdir -p ~/Program/miniconda3
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/Program/miniconda3/miniconda.sh
bash ~/Program/miniconda3/miniconda.sh -b -u -p ~/Program/miniconda3
rm ~/Program/miniconda3/miniconda.sh

## Activate
source ~/Program/miniconda3/bin/activate
conda init --all
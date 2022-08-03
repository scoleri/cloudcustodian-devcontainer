# Dev Container for Cloud Custodian Development/Contribution

## Building container *scratch*
```
docker run -it ubuntu:latest /bin/bash
apt update
apt install \
  python3 \
  python3-pip \
  python3-venv \
  curl \
  git
python3 -m venv custodian
source custodian/bin/activate
pip install c7n c7n-org c7n_azure c7n_gcp
### Poetry
curl -sSL https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py | python -
export PATH=$PATH:~/.poetry/bin
### Source - For contribution see NOTE about fork:  https://cloudcustodian.io/docs/developer/installing.html
git clone https://github.com/cloud-custodian/cloud-custodian.git
```

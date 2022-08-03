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
  vim \
  git
python3 -m venv custodian
source custodian/bin/activate
pip install c7n c7n-org c7n_azure c7n_gcp
### Poetry
curl -sSL https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py | python -
export PATH=$PATH:~/.poetry/bin
### Source - For contribution see NOTE about fork:  https://cloudcustodian.io/docs/developer/installing.html
git clone https://github.com/cloud-custodian/cloud-custodian.git
### Setup Bash Prompt (invaluable for git work)
cd
git clone https://github.com/magicmonty/bash-git-prompt.git ~/.bash-git-prompt --depth=1
cat<<EOF >>~/.bashrc
if [ -f "$HOME/.bash-git-prompt/gitprompt.sh" ]; then
    GIT_PROMPT_ONLY_IN_REPO=1
    source $HOME/.bash-git-prompt/gitprompt.sh
fi
EOF
```

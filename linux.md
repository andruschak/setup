# Quick notes on setting up a linux box for development (may not be copy:paste)


# ssh setup - create key, add to key file, once completed "cat ~/.ssh/id_rsa.pub" and paste into github
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

eval $(ssh-agent -s)

ssh-add ~/.ssh/id_rsa

# configure git (should be install by default, if not, "apg-get install git")

git config --global user.name "name"

git config --global user.email "user@mail.com"

# data science - install anaconda (https://www.anaconda.com/download/, copy the linux link and paste to curl (4.4.0 at time of writing))

curl -O https://repo.continuum.io/archive/Anaconda3-4.4.0-Linux-x86_64.sh

sha256sum Anaconda3-4.4.0-Linux-x86_64.sh (confirm against "https://docs.anaconda.com/anaconda/install/hashes/lin-3-64")

bash Anaconda3-4.4.0-Linux-x86_64.sh

source ~/.bashrc

# jupyter notebooks - installed with anaconda, since on vm, need to convert to using password

jupyter notebook --ip=* --generate-config

jupyter notebook password

screen jupyter notebook --ip=* 
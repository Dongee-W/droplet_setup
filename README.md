Droplet Setup
==========

```sh
cd $HOME
sudo apt-get install -y git-core
git clone https://github.com/sctech/droplet_setup.git
./droplet_setup/setup.sh
```
###Create user account
```
adduser YOUR_ID
```
After setting the username and password, run:
```
visudo
```
add "YOUR_ID     ALL=(ALL:ALL) ALL" right after "root     LL=(ALL:ALL) ALL", exit and reconnect.


###vim setup

1. BACKUP your `.vim` directory and `.vimrc` first.(IMPORTANT!)

2. `cd ~` to change directory to your home directory.

3. copy files to your home directory:
```
git clone git://github.com/sctech/vim.git
```
4. cd to `vim` directory and execute the `update.sh` to get latest version modules:
```
cd vim
./update.sh
```
5. make a symbolic link `.vim` to `vim` that you just cloned, or just rename it to `.vim` also be fine:
```
ln -s vim .vim
```
6. link the vimrc to
```
git clone git://github.com/sctech/vim.git
```
4. cd to `vim` directory and execute the `update.sh` to get latest version modules:
```
cd vim
./update.sh
```
5. make a symbolic link `.vim` to `vim` that you just cloned, or just rename it to `.vim` also be fine:
```
ln -s vim .vim
```
6. link the vimrc to
```
ln -s .vim/vimrc .vimrc
```

###git setup
```
git config --global user.name "sctech"
git config --global user.email "atfrontier@hotmail.com.tw"
git remote add origin git@github.com:sctech/myrepo.git
    or
git remote add origin https://github.com/sctech/myrepo.git
ssh-keygen -t rsa -C "atfrontier@hotmail.com.tw"
cat ~/.ssh/id_rsa.pub
```
Go to github.com/setting/ssh and paste the key

###hg setup
add .hgrc file to home directory
edit the .hgrc file:
```
[ui]
username = Your Name <your@mail>
```
hg push https://sctech@bitbucket.org/sctech/myrepo/

###Virtualenv
```
sudo apt-get install python3 python3-dev
mkdir temp
cd temp
curl -O http://python-distribute.org/distribute_setup.py
sudo python3 distribute_setup.py
sudo easy_install pip
cd ~
rm -rf temp
```

Add to `~/.bashrc`：
```
export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python3
```

Save and exit, run the code that just added to .bashrc in bash.
```
sudo pip install virtualenv
sudo pip install virtualenvwrapper
```

Add to `~/.bashrc` :
```
export PIP_REQUIRE_VIRTUALENV=true
export PIP_RESPECT_VIRTUALENV=true
source /usr/local/bin/virtualenvwrapper.sh
```

Save and exit, run the following codes in bash:
```
source /usr/local/bin/virtualenvwrapper.sh
export WORKON_HOME=~/.virtualenvs
```

可以視狀況 決定是否在 /etc/sudoers 的 Defaults   env_reset 下方多加入
```
Defaults   env_keep += "PIP_REQUIRE_VIRTUALENV"
Defaults   env_keep += "PIP_RESPECT_VIRTUALENV"
```
兩行

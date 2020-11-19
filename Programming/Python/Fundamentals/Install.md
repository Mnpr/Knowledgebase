#### Method 1: Source Install

```bash
---------------------------------------------------
sudo apt update

# install dependencies needed to build python source
sudo apt install build-essential zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev libreadline-dev libffi-dev wget

# get the source
cd /tmp
wget https://www.python.org/ftp/python/3.8.0/Python-3.8.0.tgz

# Extracting
tar -xf Python-3.8.0.tgz
cd Python-3.8.0
./configure --enable-optimizations

# Build
make -j 6 
sudo make altinstall # to get different copy

# Do not use the standard **make install** as it will overwrite the default system python3 binary…
python3.8 --version
---------------------------------------------------
```

#### Method 2: Installing Python via PPA

First install Ubuntu software properties package 

```bash
---------------------------------------------------
sudo apt update
sudo apt install software-properties-common

sudo add-apt-repository ppa:deadsnakes/ppa

sudo apt update
sudo apt install python3.8
----------------------------------------------------
```

***

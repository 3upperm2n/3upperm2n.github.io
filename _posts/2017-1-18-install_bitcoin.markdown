---
layout: post
title:  "Bitcoin Install"
date:   2017-1-18
categories: ["linux"]
author: "Leiming Yu"
---

### Download source code.
https://github.com/bitcoin/bitcoin.git

### Build Guide
https://github.com/bitcoin/bitcoin/blob/master/doc/build-unix.md
https://michael.mckinnon.id.au/2016/05/13/building-a-namecoin-server-with-ubuntu-16-04/

Install dependencies.

```sh
sudo apt-get install libdb++-dev
wget http://download.oracle.com/berkeley-db/db-4.8.30.NC.tar.gz
tar xzvf db-4.8.30.NC.tar.gz
cd db-4.8.30.NC/build_unix/
../dist/configure --enable-cxx
make
sudo make install

sudo apt-get install libboost-all-dev
sudo apt-get install libssl-dev
sudo apt-get install libevent-dev
```

```sh
./autogen.sh && ./configure --enable-hardening
make
sudo make install
```

**Run bitcoin**

https://github.com/bitcoin/bitcoin/tree/master/doc

```sh
bitcoin-qt
```

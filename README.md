CallMe
======

An Analysis Tool for Reentrancy Bug(Insecure message call) 

[![Gitter][gitter-badge]][gitter-url]
[![License: GPL v3][license-badge]][license-badge-url]
[![Build Status](https://travis-ci.org/melonproject/oyente.svg?branch=master)](https://travis-ci.org/melonproject/oyente)

## Quick Start

A container with the dependencies set up can be found [here](https://hub.docker.com/r/luongnguyen/oyente/).

To open the container, install docker and run:

```
docker pull luongnguyen/oyente && docker run -i -t luongnguyen/oyente
```

To evaluate the greeter contract inside the container, run:

```
cd /oyente/oyente && python oyente.py -s greeter.sol
```

and you are done!

Note - If need the [version of Oyente](https://github.com/melonproject/oyente/tree/290f1ae1bbb295b8e61cbf0eed93dbde6f287e69) referred to in the paper, run the container from [here](https://hub.docker.com/r/hrishioa/oyente/)

To run the web interface, execute
`docker run -w /oyente/web -p 3000:3000 oyente:latest ./bin/rails server`



## Full installation

### Install the following dependencies
#### solc
```
$ sudo add-apt-repository ppa:ethereum/ethereum
$ sudo apt-get update
$ sudo apt-get install solc
```

#### evm from [go-ethereum](https://github.com/ethereum/go-ethereum)

1. https://geth.ethereum.org/downloads/ or
2. By from PPA if your using Ubuntu
```
$ sudo apt-get install software-properties-common
$ sudo add-apt-repository -y ppa:ethereum/ethereum
$ sudo apt-get update
$ sudo apt-get install ethereum
```

#### [z3](https://github.com/Z3Prover/z3/releases) Theorem Prover version 4.5.0.

Download the [source code of version z3-4.5.0](https://github.com/Z3Prover/z3/releases/tag/z3-4.5.0)

Install z3 using Python bindings

```
$ python scripts/mk_make.py --python
$ cd build
$ make
$ sudo make install
```

#### [Requests](https://github.com/kennethreitz/requests/) library

```
pip install requests
```

#### [web3](https://github.com/pipermerriam/web3.py) library

```
pip install web3
```

### Evaluating Ethereum Contracts

```
#evaluate a local solidity contract
python oyente.py -s <contract filename> -td <assigment depth> -md <limitation depth>

```
The following require a Linux system to fufill. macOS instructions forthcoming.

[solc](https://github.com/melonproject/oyente#solc)
[evm](https://github.com/melonproject/oyente#evm-from-go-ethereum)
[oyente](https://github.com/melonproject/oyente/tree/master/oyente)

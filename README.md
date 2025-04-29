# 🚀 Incentive Mechanism on Blockchain

> A Solidity-based smart contract for decentralized task distribution and incentive rewards.

---

## 🔍 Features

- 📌 Smart contract-based incentive mechanism
- 🔐 Secure and verifiable with Ethereum VM
- 🚀 Tested on multiple blockchains including EOSIO, ChainMaker
- 🔄 Supports task publishing, accepting, completion, and verification

---

## 📦 Installation

```bash
git clone git@github.com:yourname/Incentive-Mechanism.git
cd Incentive-Mechanism
npm install
```

# 🚀 Geth Private Ethereum Network Setup

This project provides a step-by-step guide to setting up a private Ethereum blockchain network using [Geth (Go Ethereum)](https://geth.ethereum.org/).

## 🛠️ Prerequisites

- macOS / Linux / Windows
- [Geth](https://geth.ethereum.org/downloads)
- Terminal access

## 📦 Installation

### 1. Install Geth

#### macOS

```bash
brew tap ethereum/ethereum
brew install ethereum
```

#### Ubuntu / Debian

```bash
sudo add-apt-repository -y ppa:ethereum/ethereum
sudo apt update
sudo apt install ethereum
```

#### Windows

Download the installer from: https://geth.ethereum.org/downloads

### 2. Check Version

```bash
geth version
```

Expected output includes the current Geth version and architecture.

## 🔧 Setup a Private Ethereum Chain

### 1. Create a Data Directory

```bash
mkdir -p ~/eth-private/data
cd ~/eth-private
```

### 2. Create a Genesis File

#### Create genesis.json:

```json
{
  "config": {
    "chainId": 12345,
    "homesteadBlock": 0,
    "eip155Block": 0,
    "eip158Block": 0
  },
  "difficulty": "400",
  "gasLimit": "8000000",
  "alloc": {}
}
```

### Initialize the Chain

```bash
geth --datadir data init genesis.json
```

## 🚀 Start the Private Chain

```bash
geth --datadir data --networkid 12345 --http --http.addr "0.0.0.0" --http.port 8545 --port 30303 --nodiscover console
```

Explanation of flags:

```--datadir```: Specifies the custom data directory.

```--networkid```: Custom network ID (should match your genesis file).

```--http```: Enables the HTTP-RPC server.

```--console```: Opens the interactive JavaScript console.

## 🧪 Create Accounts

In the Geth console:

```javascript
personal.newAccount("your_password")
```

Repeat to create multiple accounts.

## 📤 Start Mining

Still in the Geth console:

```javascript
miner.start(1)
```

To stop mining:

```javascript
miner.stop()
```


# 🚀 EOSIO Local Development Environment Setup Guide

This project helps in setting up a local EOSIO development environment, including starting the `nodeos` node and `keosd` wallet, for smart contract development and testing.

---

## 📦 Dependencies

### Install EOSIO on macOS

```bash
brew tap eosio/eosio
brew install eosio
```

### Install Dependencies on Ubuntu (Optional)

```bash
sudo apt install -y clang cmake make gcc g++ curl git automake \
libbz2-dev libgflags-dev libsnappy-dev zlib1g-dev liblz4-dev libzstd-dev
```
## 🚀 Setup Steps

### 1. start Nodeos

```bash
bash scripts/start_nodeos.sh
```

### 2. Start Keosd 

```bash
bash scripts/start_keosd.sh
```

### 3. Create a Wallet

```bash
cleos wallet create --to-console
```

### 4. Import Development Private Key

```bash
cleos wallet import --private-key "YOUR PRIVATE KEY"
```

## 🛠 Deploy Example Smart Contract

```bash
cleos create account eosio alice <public_key>
cleos set contract alice ./contracts/hello
```

## 🐳 Docker One-click Setup (Optional)

```bash
docker run --name eosio \
  -d -p 8888:8888 -p 9876:9876 \
  -v ~/eosio-docker/data:/mnt/dev/data \
  eosio/eos:v2.1.0 nodeos -e -p eosio \
  --plugin eosio::chain_api_plugin \
  --plugin eosio::http_plugin \
  --contracts-console \
  --http-validate-host=false
```

# ChainMaker Quickstart via CLI

This project demonstrates how to quickly experience a ChainMaker blockchain network via command line. It follows the official ChainMaker v2.3.6 documentation.

## 📦 Prerequisites

- OS: Linux/macOS (recommended)
- Git
- wget or curl
- unzip
- Go 1.17+

---

## 🚀 Getting Started

### 1. Clone ChainMaker Repository

```bash
git clone https://git.chainmaker.org.cn/chainmaker/chainmaker-go.git
cd chainmaker-go
git checkout v2.3.6
```

### 2. Download Pre-compiled CLI Tools & Sample Chain Configuration

```bash
wget https://download.chainmaker.org.cn/chainmaker-v2.3.6/chainmaker-go-v2.3.6-linux-amd64.tar.gz
tar -zxvf chainmaker-go-v2.3.6-linux-amd64.tar.gz
cd chainmaker-go-v2.3.6-linux-amd64
```

Alternatively, for macOS:

```bash
wget https://download.chainmaker.org.cn/chainmaker-v2.3.6/chainmaker-go-v2.3.6-darwin-amd64.tar.gz
tar -zxvf chainmaker-go-v2.3.6-darwin-amd64.tar.gz
```

### 3. Start a Local ChainMaker Node

```bash
cd bin
./start.sh
```

This script starts 4 consensus nodes locally with default configuration.

### 4. Check Running Status

```bash
ps -ef | grep chainmaker
```

Expected output includes 4 processes named ```chainmaker```.

## 🧪 Use CLI to Interact with the Chain

Navigate to the CLI directory:

```bash
cd ../testdata/crypto-config/wx-org1.chainmaker.org/cli
```

View Block Height

```bash
./cmc client block getHeight \
  --contract-name=contract_manage \
  --sdk-conf-path=../../../../config/wx-org1.chainmaker.org/sdk_config.yml
```

## 📂 Directory Overview

```arduino
chainmaker-go-v2.3.6-linux-amd64/
├── bin/
│   └── start.sh
├── config/
├── data/
├── logs/
└── testdata/
```

## 🛑 Stop the Chain

```bash
cd bin
./stop.sh
```


# 💬 Contact

This `README.md` is formatted with Markdown and contains all the essential steps and instructions to set up local development environments for three popular blockchain platforms:

- **Geth (Go-Ethereum)** – the official Go implementation of the Ethereum protocol
- **EOSIO** – a high-performance WebAssembly-based smart contract platform
- **ChainMaker** – a consortium blockchain infrastructure developed in China

Each section walks you through environment setup, dependencies, and basic commands to get the local blockchain nodes running. Whether you’re building DApps, testing smart contracts, or just exploring blockchain protocols, this guide offers a unified way to explore multiple chains on your local machine.

If you need any additional help, configuration, or want to extend it with Docker support or contract examples, feel free to ask!


![Uploading image.png…]()

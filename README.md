# Zama FHE Protocol Technical Guides
I regularly update this repository with detailed guides on technical tasks related to the Zama protocol.

## Environment
**Linux Ubuntu OS**
* **VPS**: You can use a linux VPS to follow the guide
* **Windows**: Install Linux Ubuntu using WSL by following this [guide](https://github.com/0xmoei/Install-Linux-on-Windows)
* **Codespace**: If you don't have VPS or Windows WSL, you can use [Github Codespace](https://github.com/codespaces), create a blank template and run your codes.

## Install Dependecies
```console
# Packages:
sudo apt update && sudo apt upgrade -y
sudo apt install screen curl iptables build-essential git wget lz4 jq make gcc nano automake autoconf tmux htop nvme-cli libgbm1 pkg-config libssl-dev libleveldb-dev tar clang bsdmainutils ncdu unzip libleveldb-dev  -y

# Install Nodejs, npm, yarn
sudo apt update
sudo curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -
sudo apt install -y nodejs
node -v
npm install -g yarn
yarn -v

# Install Hardhat
sudo npm install -g hardhat
```

## Deploy FHECounter contract
```
git clone https://github.com/zama-ai/fhevm-hardhat-template
cd fhevm-hardhat-template
```

Install:
```
npm install
```

Replace `hardhat.config.ts` file:
```
curl -o hardhat.config.ts https://raw.githubusercontent.com/msnik/zama-fhe/refs/heads/main/hardhat.config.ts
```
# edit hardhat.config.ts and set privatekey, rpcurl

nano hardhat.config.ts

Compile and Deploy:
```
# Compile
npx hardhat compile

# Deploy
npx hardhat deploy --network sepolia
```
* It responds with your deployed contract address

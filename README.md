```bash
mkdir -p ~/.story/geth
mkdir -p ~/.story/story
```
```bash
sudo apt update && sudo apt install screen curl make jq build-essential gcc unzip wget lz4 aria2 -y
```
```bash
cd ~/.story/geth && wget https://story-geth-binaries.s3.us-west-1.amazonaws.com/geth-public/geth-linux-amd64-0.9.2-ea9f0d2.tar.gz && tar -xvf geth-linux-amd64-0.9.2-ea9f0d2.tar.gz
```
```bash
screen -S geth
```
```bash
geth-linux-amd64-0.9.2-ea9f0d2/geth --iliad --syncmode full
```
- Ctrl + A + D
```bash
cd
```
```bash
cd ~/.story/story && wget https://story-geth-binaries.s3.us-west-1.amazonaws.com/story-public/story-linux-amd64-0.9.11-2a25df1.tar.gz && tar -xvf story-linux-amd64-0.9.11-2a25df1.tar.gz
```
```bash
screen -S story
```
```bash
story-linux-amd64-0.9.11-2a25df1/story init --network iliad –moniker "NAME_OF_YOUR_MONIKER" --force
```
```bash
story-linux-amd64-0.9.11-2a25df1/story run
```
- Ctrl + A + D

<h2 align=center> Story Protocol Validator Node Guide </h2>

## Vps Configuration

| Component  | Requirement     |
|------------|-----------------|
| **CPU**    | 4 Cores         |
| **RAM**    | 8 GB            |
| **Disk**   | 200 GB          |
| **Bandwidth** | 10 MBit/s    |

## Installation Commands
- First create 2 directories using the below command
```bash
mkdir -p ~/.story/geth ~/.story/story
```
- Install necessary dependencies
```bash
sudo apt install screen curl git make jq build-essential gcc unzip wget lz4 aria2 -y
```
- Download and extract `geth` binary file in `~/.story/geth` directory
```bash
cd ~/.story/geth && wget https://story-geth-binaries.s3.us-west-1.amazonaws.com/geth-public/geth-linux-amd64-0.9.2-ea9f0d2.tar.gz && tar -xvf geth-linux-amd64-0.9.2-ea9f0d2.tar.gz
```
- Create a screen session named `geth`
```bash
screen -S geth
```
- Start `geth` using the below command
```bash
geth-linux-amd64-0.9.2-ea9f0d2/geth --iliad --syncmode full
```
- Now press `Ctrl+A+D` to detach from `geth` screen session
- Go to your `Home` directory
```bash
cd
```
- Download and extract `story` binary file in `~/.story/story` directory
```bash
cd ~/.story/story && wget https://story-geth-binaries.s3.us-west-1.amazonaws.com/story-public/story-linux-amd64-0.9.11-2a25df1.tar.gz && tar -xvf story-linux-amd64-0.9.11-2a25df1.tar.gz
```
- Create another screen session named `story`
```bash
screen -S story
```
- Initialise and then run `story` using below 2 commands
```bash
story-linux-amd64-0.9.11-2a25df1/story init --network iliad --force
```
```bash
story-linux-amd64-0.9.11-2a25df1/story run
```
- After running this command, you may face problem, so to resolve this use the below commands
- First use `Ctrl+C` to stop this
- Now use the below command to edit `config.toml`
```bash
nano config/config.toml
```
- You need to use `W` `A` `S` `D` key to move the cursor, Use `S` button to scroll down, You will see a `P2P configuration section`, Initially you will find `persistent_peers=""`, remove this line and then copy the below mentioned peer id and paste it there
```bash
persistent_peers="a320f8a15892bddd7b5502527e0d11c5b5b9d0e3@69.67.150.107:29931,2027b0adffea21f09d28effa3c09403979b77572@198.178.224.25:26656,59b94de50f52575174e771d75082f020cb8b5bfc@112.118.22.8:26956,51c6bda6a2632f2d105623026e1caf12743fb91c@204.137.14.33:36656,ccb6e8d1788bd46be4abec716e98236c2e21c067@116.202.51.143:26656,4c1904591cbc70bb7e11c5c11ec9b0586fe72d4b@138.201.85.253:26656,e5b80cd31b8f5c40644ce52834b58e51c6a24bfa@65.109.88.19:26656,537b4c11a17f282bd9f84ba578e5998944c49c79@176.9.155.156:28656,800bd9a3bb37a07d5c57c42a5de72d7ab370cfd1@194.146.12.193:26656,7bbc8241b81f18b185ded9fca3220ce062bc5a0c@141.98.154.42:26656,7ed2e34f5e80948e862ba96d3051c08e4fb3b696@194.48.168.43:26656,c2ae488ed7c74f7139d927e7518a9485fa5e0623@213.239.198.181:35656,d4c5dcfbec11d80399bcf18d83a157259ca3efc7@138.201.200.100:26656,b37eff82c86e867f8bf4df1199fbd90cc411b9dd@45.59.70.168:26656,17d69e7e7f6b43ef414ee6a4b2585bd9ee0446ce@135.181.139.249:46656,3b88917cdc563f463268820d9b89092c6df4df78@91.227.33.18:47656,aac5871efa351872789eef15c2da7a55a68abdad@88.218.226.79:26656,9fc21eaa5f39f3611875a951775c5b1ebdf032ee@84.32.186.154:26656,7f72d44f3d448fd44485676795b5cb3b62bf5af0@142.132.135.125:20656,502768c5256728123626411bcd85a5633af5a1bc@95.217.193.182:46656,5e16a409531f8cdbda53e7321aaf46c325148886@103.114.163.217:26656,dd8c1e59141bb27fc0577d2c3fcd4a01f05364a0@57.129.51.140:26656,6a1b35d7c8deae3f6b0588855300af1dfa8ebd17@49.12.172.31:13656,a03f525b72ece596b6ea3609b49c676751fafc14@94.141.103.163:26656,f1ec81f4963e78d06cf54f103cb6ca75e19ea831@217.76.159.104:26656,56e241d794ec8c12c7a28aa7863db1322589de0a@144.76.202.120:36656,a9b2953ce7bd844fee3c46e16615668e99524dee@135.181.144.149:26656,1e9d0e61fe26530f7f9c3b327e7195381bf93727@176.9.72.218:26656,590e680fe380769f733b7f2d0e008fe1f3c62964@37.27.56.53:26656,e4dcdc1218f8703a16f6cc8d7024af2457661198@198.7.125.195:26656,e8522a9777efdce9b4395981423e8157b4d1d0d1@65.21.45.194:27656,54a80c1ebac879c698e361621e338753c0510a17@5.9.73.13:25136,b7bead382ecc5a4367fa2fe627d7841ba359bf7f@45.159.220.151:26656,901f7c763100f36b21d3d5110b56dd6806991847@45.90.123.229:26656,9ed1e069802812f484faa68a2c6dd61f6bc1be0b@88.99.61.173:26656,aa16f5f6e2da8b3c4b14746b875edd2eff21eca4@195.179.229.137:26656,cf7804bd1ec369215d7ece864962e3787810074b@62.169.21.31:26656,3d45763a87ce7f62af06f31ba6d738370522a5c3@80.240.25.22:26656,903aac04aeac4f39998cc9cbefb796ca283090f2@45.61.156.53:2665,a15d9e52b1ac29daef23c62a33f3c3d26533d07b@213.239.207.162:26656,9d17f4db09af4f2d0d09e9ab73eebc5489df99e1@51.79.255.110:26656,6830d86391b26ee17b87bdd206e67e6202d5e3db@86.48.2.96:26656,84d347aba1869b924a6d709f133f7b135202a787@84.247.136.201:26656,612f7024069a19e430a8d24290ae8644b259f0db@66.42.53.180:26656,a750f8ee195c0ea3c26dbbd41931a002cb4cf0ae@117.6.160.195:26656,89fbc31f40fc7a4d5594cb76d8ed930e7859aaf5@144.91.72.10:26656,31f2591b19ffdfafbffe759e257eba7a207e4f08@156.67.81.231:26656,295d20a6011d2c25092761d5b4fdf5a2f5d9cd29@109.199.97.58:26656,f8b29354fbe832c1cb011b2fbe4f930f89a0d430@188.245.60.19:26656,36ae9a7911e9f9ca5cb04b5c740b94b96f1b20c8@38.242.211.97:26656,45a2764d43590b89a33dfde62645655fe693c065@152.53.3.39:26656,829e901d7b812e63d4516d931c6dcaf4aea697ed@192.248.189.168:26656,500208ae8b0b20f8d74c16d14ed5f26492825a2a@37.27.91.228:26656,2987184f6b773e88fdb8f6d22e93614c812140b3@37.27.48.77:26656,50acd65aff9b58ba96ed058764d76cee6f667316@183.81.47.245:29656,cf7712cab3f22912a2837ca5e48ae89da00067e5@49.13.90.192:26656,9f8c95e147955c3e040b6a621869ce42330ff89f@65.109.139.166:26656,c79ae014f5cca73cae4bba438ea99e664e0e0360@65.108.210.70:26656,88cf3523dd1d59d7af15ce832551cbb1748879a9@95.217.7.167:26656,5568ca144b3acf4260026037aa3314781e3f124a@144.76.70.103:24656,fe5b39d2bd701ed12a953894cc1449d4c5c6d699@135.125.189.91:26656,2333daf1b0c90fcad775595bb071478894f56392@144.126.139.139:26651,ef2f9d930fa65c0e3f184e2899ac7a9053fd1e69@49.13.4.170:26656,4ddd58724ad881d9a102c42da938d30c1dd8ffd8@185.242.87.10:26656"
```
- Save this file using `Ctrl+X` then `Y` and then press `Enter`
- If you check now, you'll notice a significant difference between your node and the latest block. Your node needs to synchronize with the most recent block
```bash
echo $(( $(curl -s https://staking.testnet.storyrpc.io/api/network_status | jq -r '.msg.consensus_block_height') - $(curl -s localhost:26657/status | jq -r '.result.sync_info.latest_block_height') ))
```
- So, I would recommend you to use snapshot, it does not mean that your node will be synchronised with latest block immedietly, there will be still some gap
- So to use snapshot first stop the `story` using `Ctrl+C` and then detach from the screen session `Ctrl+A+D`
- Move to the `home` directory using the below command
```bash
cd
```
- Reattach with `geth` screen session now, and then use `Ctrl+C` to stop it and then detach from this screen session using `Ctrl+A+D`
- Now visit [this docs](https://service.josephtran.xyz/testnet/story/snapshot)  by **Joseph Tran**, You don't need top stop node using his command, as our command is different, you just do these things from that doc `Download Geth-data and Story-data` , `Backup priv_validator_state.json` , `Remove old data` , `Extract Story-data and geth-data` , `Move priv_validator_state.json back`
- Now come back to my guide and use this command to restart again
```bash
screen -r geth
```
- Now use this command to start `geth` again
```bash
geth-linux-amd64-0.9.2-ea9f0d2/geth --iliad --syncmode full
```
- Detach from this screen session again using `Ctrl+A+D`
- Use the below command to reattach to `story` screen session
```bash
screen -r story
```
- Use this command to start `story`
```bash
story-linux-amd64-0.9.11-2a25df1/story run
```
- Detach from this screen session using `Ctrl+A+D`
- You need to wait until your node sync with latest block, you can check how many blocks are still left to synchronised with your node using below command
```bash
echo $(( $(curl -s https://staking.testnet.storyrpc.io/api/network_status | jq -r '.msg.consensus_block_height') - $(curl -s localhost:26657/status | jq -r '.result.sync_info.latest_block_height') ))
```
- You can also simply use the below command to check `catching_up` is `false`
```bash
curl -s localhost:26657/status | jq
```
- You need to wait until you see `catching_up` is `false`
- You can close your terminal now and check the status after 3-5 hrs using above 2 commands
- By default, when you initialised `story` in above steps,  a `validator key` is created for you. To view your validator key, run the following command:
```bash
$HOME/.story/story/story-linux-amd64-0.9.11-2a25df1/story validator export
```
- Request some [faucet](https://faucet.story.foundation/) (atleast 3 $IP) to this `EVM Public Key`
- In addition, if you want to export the derived EVM private key of your validator into the default data config directory, please run the following:
```bash
$HOME/.story/story/story-linux-amd64-0.9.11-2a25df1/story validator export --export-evm-key
```
- View your this EVM wallet private key and save it somewhere
```bash
cat $HOME/.story/story/config/private_key.txt
```
- Now create a validator using this command
```bash
story validator create --stake 1000000000000000000 --private-key PRIVATE_KEY_OF_EVM_YOU_COPIED_IN_THE_AVOBE_STEP
```
- Now copy this validator wallet's pruvate key as well and save it
```bash
cat $HOME/.story/story/config/priv_validator_key.json
```
- To participate in consensus, at least 1024 IP must be staked (equivalent to 1000000000000000000 wei) as of now lol
```bash
story validator stake \
   --validator-pubkey "VALIDATOR_PUB_KEY_IN_BASE64" \
   --stake 1024000000000000000000 \
   --private-key PRIVATE_KEY_OF_EVM_YOU_COPIED_EARLIER
```
- Replace `VALIDATOR_PUB_KEY_IN_BASE64` with the value you will get after running this command
```bash
curl -s localhost:26657/status | jq -r '.result.validator_info.value'
```
- Check your validator on [Explorer](https://testnet.story.explorers.guru/)

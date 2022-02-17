# ERC-721Example

First go to the [IPFS website](https://docs.ipfs.io/install/command-line/#official-distributions) and follow the install steps. I'm using arch btw so can install from the AUR with yay or aurman
```
yay go-ipfs
```
if on mac should work
```
brew install ipfs
```
if that dose not work then 
```
curl -O https://dist.ipfs.io/go-ipfs/v0.11.0/go-ipfs_v0.11.0_darwin-amd64.tar.gz
```
then unzip 
```
tar -xvzf go-ipfs_v0.11.0_darwin-amd64.tar.gz
```
the go into the dir and install using the install.sh 
```
cd go-ipfs
bash install.sh
```
you can check if ipfs is install by doing, if this dose not work then follow the [docs](https://docs.ipfs.io/install/command-line/#official-distributions), my ethical values bar me from putting a w****** install guide
```
$ ipfs --version
```
Then init your node using 
```
ipfs init
```
If you cat out the readme file for more info using 
```
ipfs cat /ipfs/<your-peer-iden>/readme
```
get the image and add it using ipfs add path for example
```
ipfs add image.png
```
it returns
```
added QmZzDTScryCxGxyUxPtPTCM5V9Y7jXePj5xcHjKsTCYzbi image.png
```
to view go to https://ipfs.io/ipfs/<your link> 
might need to open on a local server as sometimes takes a while to upload. Make sure to save the string. 
eg https://ipfs.io/ipfs/QmZzDTScryCxGxyUxPtPTCM5V9Y7jXePj5xcHjKsTCYzbi

Add a JSON file describing the file ie
```json
{
    "name" : "a name",
    "description" : "the description of the picture",
    "image" : "the link from before https://ipfs.io/ipfs/"
}
```
add the json the same way you did before
```
ipfs add nft.json
```
save the link
https://ipfs.io/ipfs/QmTJYGFqSFYNY6zVudLbjuk1wRC8qDB6myAScc34pZbLDx


you can chose many framworks like brownie or hardhad each one will have diffrent methods I will use hardhat 

install hardhat using 
```
npm install --save-dev hardhat
```
so make sure you have node installed and the init a new project
```
npm init -y
```
then init hardhat using 
```
npx hardhat
```
then chose 
```
$ npx hardhat
888    888                      888 888               888
888    888                      888 888               888
888    888                      888 888               888
8888888888  8888b.  888d888 .d88888 88888b.   8888b.  888888
888    888     "88b 888P"  d88" 888 888 "88b     "88b 888
888    888 .d888888 888    888  888 888  888 .d888888 888
888    888 888  888 888    Y88b 888 888  888 888  888 Y88b.
888    888 "Y888888 888     "Y88888 888  888 "Y888888  "Y888

Welcome to Hardhat v2.0.0

? What do you want to do? …
  Create a sample project
❯ Create an empty hardhat.config.js
  Quit
```
Install some extra pkgs 
```
npm install --save-dev @nomiclabs/hardhat-ethers ethers @nomiclabs/hardhat-waffle ethereum-waffle chai
```
also install the openzepplin contracts
```
npm install --save-dev @openzeppelin/hardhat-upgrades
```
create a .sol file and just copy and paste the file in my contract


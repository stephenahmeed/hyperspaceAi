### Hyperspace Depin Node 3 ways to farm

## 1. Directly from the site
   - Visit: node.hyper.space
   - Toggle the red button on the left to connect.  
  -  Save your PrivateKey

## 2. Installing the app on PC
   - Click "Download" on the right corner of the site.  
   - Choose your PC type, download, and install.  
   - Install a provider and connect it to Hyperspace.  
   - You can find your PrivateKey file key.pmf in directory Search hyperspace

Note:  Make sure to keep the red switch turned on because it can sometimes disconnect, possibly because of network issues.

## 3. Hyperspace Linux CLI Node (VPS)
* You can also check out [Official repository](https://github.com/hyperspaceai/aios-cli?tab=readme-ov-file) for more commands and info

### Install
```
curl https://download.hyper.space/api/install | bash

source /root/.bashrc
```

### Start your node

# Create a screen ro run it in background for later
```shell
screen -S hyperspace
```
# Run node

```shell
aios-cli start
```
* To continue, minimize your screen using `CTRL+A+D` or Open second terminal
* Turn back to screen: `screen -r hyperspace`
If showing any error update "screen: command not found" indicates that the screen utility is not installed on your system. Here's how to fix it by installing screen:

## Steps to Install screen:

1. Update the package list:
   
   sudo apt update
   
2. Install screen:
   
   sudo apt install screen

### Config Node

# Download a required model
```shell
aios-cli models add hf:TheBloke/phi-2-GGUF:phi-2.Q4_K_M.gguf
```
# Import your private key - Create a my.pem file using nano .pem and input a privatekey (You can get a privatekey from browser version)
```shell
aios-cli hive import-keys ./my.pem
```
# Set those keys as the preferred keys for this session
```shell
aios-cli hive login
```
# Make sure the model is registered
```shell
aios-cli hive connect
```
```shell
aios-cli hive select-tier 5
```

## Check Points

# To check your current multiplier and points

```shell
aios-cli hive points
```

![Screenshot_514](https://github.com/user-attachments/assets/b840775e-6c58-4fe4-bd95-a5b876ba7de5)


# Usefull commands
```console
# Shortcut for Start, Login and Connect to Hive commands, if you've stopped you node
aios-cli start --connect
# Update node
aios-cli version
# Stop node
aios-cli kill

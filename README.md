# MASS Network tutorial

## MASS Wallet
### masswallet binary

For list of all commands, just type:

```bash
./masswallet -h
```

### Admin rights needed

Probably you need to bring Admin rights to your Mac/Linux/Windows terminal if you want a fully functional MASS Wallet / Miner.

### Config file

MASS doesn't know where is the config.json file, so we'll use **/C** parameter to point it.
1. Copy *config.json* in this repo to your computer.
2. Execute following command to start syncing the blockchain in *chain* folder.

```bash
./masswallet /C "your/absolute/route/to/config.json"
```

In my case, the path is **C:\Users\Santiago Gimenez\Desktop\massminer-windows-amd64\config.json**. 

### Create wallet

The */create* parameter will give you a fresh new wallet for you. I recommend running this command in another terminal because that you can sync the blockchain in the first terminal we just created in "Config file" title.

```bash
./masswallet /C "your/absolute/route/to/config.json" /create
```


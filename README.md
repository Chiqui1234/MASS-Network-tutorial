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

## MASS Miner

Go to MASS Miner's folder and locate *conf* subfolder. There you'll have:
1. sample-config.core.json
2. sample-config.m1.json
3. sample-config.m2.json

Just look *help* page of this miner:

```bash
./massminer -h
NAME:
   massminer - Miner Full Node for MassNet Blockchain.

USAGE:
   massminer.exe [global options] command [command options] [arguments...]

COMMANDS:
   core     Run massminer in core mode (sync with network but never mine blocks)
   m1       Run massminer in m1 mode (mine blocks with native MassDB)
   m2       Run massminer in m2 mode (mine blocks with Chia DiskProver)
   [...]
```

I'm interested in MASS farming throught Chia plots, so **m2** is my way to go. This tutorial has special focus on **m2**, however I'm pretty sure **core** and **m1** has similar *config.json*.
I moved my *sample-config.m2.json* to MASS Miner's root folder, and renamed as *config.json*.

Then, open that config file and look this part:

```json
"proof_dir": [
      "/path/to/chia_plots1",
      "/path/to/chia_plots2",
      "/path/to/chia_plots3",
      "/path/to/chia_plots4",
      "/path/to/chia_plots5"
    ],
```

Now, point your Chia's plot folder into **proof_dir** array. If you don't know how to code JSON arrays, [see this tutorial](https://www.w3schools.com/js/js_json_arrays.asp).
Long story short: enclose your plots' paths between quotes, and separate them with a comma (**,**). Last path doesn't need a comma after the quotation mark... and ALL inside brackets (**[** and **]**) are values of the array called *proof_dir*.

Then, execute the miner:

```bash
./massminer -C "your/absolute/route/to/config.json"
```

And the miner won't start. This tutorial will continue when I figure out how this miner works (sadly, docs are very poor: just the *help* page of the app!).

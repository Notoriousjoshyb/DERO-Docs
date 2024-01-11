Mining DERO
===========

Downloading Miner
-----------------

Download here: https://github.com/deroproject/derohe/releases

Download the latest binaries for your platform

![image](/assets/stargatemining/stargatebinaries.png)

> ***NOTE:*** As the Binaries will be continuously updated, the actual version numbers might be different from the screenshot at the moment of reading.

Install Miner
-------------

### Windows

Right Click in the location where you wish to save the miner and create new folder

![image](/assets/stargatemining/cli1.png)

Using 7zip or similar extract latest binaries to the folder you created

![image](/assets/stargatemining/cli2.png)

Local Mining
------------

To mine locally you will require the daemon to be running.

For Windows users please follow this guide: https://docs.dero.io/rtd_pages/stargate_daemon.html

For Linux users please follow this guide: https://docs.dero.io/rtd_pages/basic_ubuntu.html

Once you have the daemon running you can start the miner.

To do this type CMD into the search bar. This will then open the command prompt box

![image](/assets/stargatemining/cli3.png)

You will then need to type

```
dero-miner-windows-amd64 --wallet-address dero1qykyta6ntpd27nl0yq4xtzaf4ls6p5e9pqu0k2x4x3pqq5xavjsdxqgny8270 --mining-threads 6

```

For Linux users you can start the miner using

```
./dero-miner-linux-amd64 --wallet-address dero1qykyta6ntpd27nl0yq4xtzaf4ls6p5e9pqu0k2x4x3pqq5xavjsdxqgny8270 --mining-threads 6

```

As you have the daemon running your machine will mine to this node and you will recieve block, miniblock & Node rewards.

Remote Mining
-------------

If you wish to host a full node you can recieve 9% mining rewards for the block mined whilst connected to your node. To do this miners will need to add the daemon rpc address at the end of the command to start the miner.

To set up a node for Windows with rewards please follow this guide: https://docs.dero.io/rtd_pages/stargate_daemon.html

To set up a node for Linux with rewards please follow this guide: https://docs.dero.io/rtd_pages/basic_ubuntu.html

To run DERO miner type CMD into the search bar. This will then open the command prompt box

![image](/assets/stargatemining/cli3.png)

You will then need to type

```
dero-miner-windows-amd64 --wallet-address dero1qykyta6ntpd27nl0yq4xtzaf4ls6p5e9pqu0k2x4x3pqq5xavjsdxqgny8270 --mining-threads 6 --daemon-rpc-address minernode1.dero.io:10100

```

For Linux users please type

```
./dero-miner-linux-amd64 --wallet-address dero1qykyta6ntpd27nl0yq4xtzaf4ls6p5e9pqu0k2x4x3pqq5xavjsdxqgny8270 --mining-threads 6 --daemon-rpc-address minernode1.dero.io:10100

```

> ***NOTE:*** Change DERO Address to match your wallet address, Mining threads to what you require & daemon address to the address of your full node

![image](/assets/stargatemining/miner1.png)

Congratulations you are now mining DERO

![image](/assets/stargatemining/miner2.png)
Running A Node with Windows
===========================

Downloading Daemon
------------------

Download here: [DERO Github](https://github.com/deroproject/derohe/releases)

Download the latest binaries for your platform

![image](/assets/stargatemining/stargatebinaries.png)

> ***NOTE:*** As the Binaries will be continuously updated, the actual version numbers might be different from the screenshot at the moment of reading.

Install
-------

Right Click in the location where you wish to save the daemon and create new folder

![image](/assets/stargatedaemon/cli1.png)

Using 7zip or similar extract latest binaries to the folder you created

![image](/assets/stargatedaemon/cli2.png)

Running Full Node
-----------------

To run a full node type CMD into the search bar. This will then open the command prompt box

![image](/assets/stargatedaemon/cli3.png)

You will then need to type derod-windows-amd64.exe

![image](/assets/stargatedaemon/daemon6.png)

The daemon is now launched and will sync the entire blockchain.

Full Node Recommended Specs
---------------------------

For the best possible performance we reccomend you use at least a 4 core CPU and 8gb Ram.

Setting up for Node Rewards
---------------------------

With the release of Sigma-Mining each daemon can become its own pool, which tracks mining shares from devices connected to it. The daemon itself will retain a fixed fee (currently 9%) for the daemon operator, the rest will be distributed to all miners that contributed shares to that daemon. For most miners, they will be mining using their own daemon, so all rewards and fees will be credited.

To do this you will need to follow the above steps but change the command to launch the daemon to the following

```
derod-windows-amd64 --integrator-address dero1qypj3sctlt7mefhvdhrvrygj55m40ugl7ml2dukzypxdtd2agpgsjqq2v3n6h

```

You will then need to connect your miner to the node by using the following command

For Windows

```
dero-miner-windows-amd64 --wallet-address dero1qypj3sctlt7mefhvdhrvrygj55m40ugl7ml2dukzypxdtd2agpgsjqq2v3n6h --mining-threads 6 --daemon-rpc-address 45.82.66.55:10100

```

For Linux

```
./dero-miner-linux-amd64 --wallet-address dero1qypj3sctlt7mefhvdhrvrygj55m40ugl7ml2dukzypxdtd2agpgsjqq2v3n6h --mining-threads 6 --daemon-rpc-address 45.82.66.55:10100

```

For a full mining guide please visit here: https://docs.dero.io/rtd_pages/stargate_mining.html
Creating a DERO Home Network
============================

Downloading Daemon
------------------

Download here: https://github.com/deroproject/derohe/releases

Download the latest binaries for your platform

![image](/assets/stargatemining/stargatebinaries.png)

> ***NOTE:*** As the Binaries will be continuously updated, the actual version numbers might be different from the screenshot at the moment of reading.

Install Daemon
--------------

Right Click in the location where you wish to save the daemon and create new folder

![image](/assets/stargatedaemon/cli1.png)

Using 7zip or similar extract latest binaries to the folder you created

![image](/assets/stargatedaemon/cli2.png)

Running Full Node on Home Network
---------------------------------

To run a full node type CMD into the search bar. This will then open the command prompt box

![image](/assets/stargatedaemon/cli3.png)

You will then need to type

```
derod-windows-amd64.exe --rpc-bind=0.0.0.0:10102

```

> ***NOTE:*** This option is only to be used in Private/Local LAN/Home Network only. Traffic is TCP and un-encrypted on port 10102

![image](/assets/stargatedaemon/daemon6.png)

The daemon is now launched and will sync the entire blockchain.

Downloading Miner
-----------------

Download here: https://github.com/deroproject/derohe/releases

Download the latest binaries for your platform

![image](/assets/stargatemining/stargatebinaries.png)

> ***NOTE:*** As the Binaries will be continuously updated, the actual version numbers might be different from the screenshot at the moment of reading.

Install Miner
-------------

Right Click in the location where you wish to save the miner and create new folder

![image](/assets/stargatemining/cli1.png)

Using 7zip or similar extract latest binaries to the folder you created

![image](/assets/stargatemining/cli2.png)

Connect Miner to Home Network Node
----------------------------------

To run DERO miner type CMD into the search bar. This will then open the command prompt box

![image](/assets/stargatemining/cli3.png)

You will then need to type the following to connect it to the daemon on your home network

```
dero-miner-windows-amd64 --wallet-address dero1qykyta6ntpd27nl0yq4xtzaf4ls6p5e9pqu0k2x4x3pqq5xavjsdxqgny8270 --mining-threads 6 --daemon-rpc-address  localnodeip:10100

```

![image](/assets/Swap/swap43.PNG)

> ***NOTE:*** You will need to find the IPV4 address of your pc which is running the node. You will then be able to connect using --daemon-rpc-address LocalNodeIP:10100

Downloading Wallet
------------------

Download here: https://github.com/deroproject/derohe/releases

Download the latest binaries for your platform

![image](/assets/stargatewallet/stargatebinaries.png)

> ***NOTE:*** As the Binaries will be continuously updated, the actual version numbers might be different from the screenshot at the moment of reading.

Install Wallet
--------------

Create a folder called 'Stargate Mainnet'

![image](/assets/Swap/swap22.PNG)

Open the folder 'Stargate Mainnet' and open the zip file you have downloaded form the DERO GitHub page and copy files from the zip file to the 'Stargate Mainnet' Folder.

![image](/assets/Swap/swap23.PNG)

Opening Wallet and Connect to Home Network
------------------------------------------

Open the folder you have copied over to your 'Stargate Mainnet' folder

![image](/assets/Swap/swap24.PNG)

Open up command prompt and cd to the location of your folder you have just created. In my example it is C:\Users\joshy\Desktop\Stargate Mainnet\dero_windows_amd64

![image](/assets/Swap/swap25.PNG)

Once you are in the folder in your command prompt window type

```
dero-wallet-cli-windows-amd64.exe --daemon-address= localnodeip:10102

```

![image](/assets/Swap/swap42.PNG)

You now have your wallet and miner connected to your node within your home network. Please repeat this guide to connect multiple devices to your home node.
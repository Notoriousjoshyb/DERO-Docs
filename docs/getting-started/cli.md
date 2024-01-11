CLI Wallet User Guide (Stargate)
================================

> ***NOTE:*** You will require a running Node to access your wallet. Please follow this guide to running a node https://docs.dero.io/rtd_pages/stargate_daemon.html

Downloading Wallet
------------------

Download here: https://github.com/deroproject/derohe/releases

Download the latest binaries for your platform

![image](/assets/stargatemining/stargatebinaries.png)

> ***NOTE:*** As the Binaries will be continuously updated, the actual version numbers might be different from the screenshot at the moment of reading.

Install Wallet
--------------

### Windows

Create a folder called 'Stargate Mainnet'

![image](/assets/Swap/swap22.PNG)

Open the folder 'Stargate Mainnet' and open the zip file you have downloaded form the DERO GitHub page and copy files from the zip file to the 'Stargate Mainnet' Folder.

![image](/assets/Swap/swap23.PNG)

Opening Wallet
--------------

Open the folder you have copied over to your 'Stargate Mainnet' folder

![image](/assets/Swap/swap24.PNG)

Open up command prompt and cd to the location of your folder you have just created. In my example it is C:\Users\joshy\Desktop\Stargate Mainnet\dero_windows_amd64

![image](/assets/Swap/swap25.PNG)

Once you are in the folder in your command prompt window type dero-wallet-cli-windows-amd64.exe

![image](/assets/Swap/swap26.PNG)

Create New Wallet
-----------------

Click option number 2 by pressing 2 then enter

![image](/assets/Swap/swap27.PNG)

You will now need to enter a name for the wallet. Please use wallet.db

![image](/assets/Swap/swap28.PNG)

Enter a password for your wallet and store this securely

![image](/assets/stargatewallet/cnw4.png)

You will now need to enter a password for the wallet. Please make sure you save this password somewhere safe.

![image](/assets/Swap/swap29.PNG)

You will be then asked to enter the password again

![image](/assets/Swap/swap30.PNG)

You will now need to select a language for your wallet. Please select the number next to your language and hit enter.

![image](/assets/Swap/swap31.PNG)

You will noe be given your wallet seed. It is important that you do not lose this as it is the key to your coins. Please ensure you save this and do not lose it.

![image](/assets/Swap/swap32.PNG)

You have now successfully created you wallet. Please proceed to registering your wallet on the blockchain chain.

Registering Wallet to the blockchain
------------------------------------

You will now need to select option 4 and press enter to register your wallet address.

> ***NOTE:*** This can take up to 2 hours for your wallet to be registered to the network.

![image](/assets/Swap/swap33.PNG)

Once your wallet is registered it will look like this

![image](/assets/Swap/swap34.PNG)

Recover existing wallet from seed
---------------------------------

To open wallet type CMD into the search bar. This will then open the command prompt box

![image](/assets/stargatewallet/cli3.png)

You will then need to type dero-wallet-cli-windows-amd64.exe

![image](/assets/stargatewallet/cli4.png)

The wallet CLI wallet is now launched

![image](/assets/stargatewallet/cli5.png)

Select Option 3 Recover wallet from seed

![image](/assets/stargatewallet/cnw10.png)

Select name for wallet example: wallet.db

![image](/assets/stargatewallet/cnw3.png)

Enter a password for your wallet and store this securely

![image](/assets/stargatewallet/cnw4.png)

Enter password again to confirm

![image](/assets/stargatewallet/cnw5.png)

Enter your 25 word seed that you have saved securly and press enter

![image](/assets/stargatewallet/cnw11.png)

Congratulations you have now recovered your wallet from seed

![image](/assets/stargatewallet/cnw12.png)

Recover wallet using recovery key
---------------------------------

To restore a wallet from recovery keys first you will need to the keys for the wallet. To find the keys for your own wallet please select option 3

![image](/assets/stargatewallet/cnw13.png)

You will then need to enter your wallet password

![image](/assets/stargatewallet/cnw14.png)

You will now be given a secret key and a public key. Please save these in a secure location.

You will then need to open wallet type CMD into the search bar. This will then open the command prompt box

![image](/assets/stargatewallet/cli3.png)

You will then need to type dero-wallet-cli-windows-amd64.exe

![image](/assets/stargatewallet/cli4.png)

The wallet CLI wallet is now launched

![image](/assets/stargatewallet/cli5.png)

You will then need to chose option 4

![image](/assets/stargatewallet/cnw16.png)

Select name for wallet example: wallet.db

![image](/assets/stargatewallet/cnw3.png)

Enter a password for your wallet and store this securely

![image](/assets/stargatewallet/cnw4.png)

Enter password again to confirm

![image](/assets/stargatewallet/cnw5.png)

You will then need to input the secret key and press enter

![image](/assets/stargatewallet/cnw17.png)

You will then need to select the language for your wallet-cli-windows-amd64

![image](/assets/stargatewallet/cnw18.png)

Congratulations you have now recovered your wallet from recovery key

![image](/assets/stargatewallet/cnw19.png)

CLI Wallet Functions
--------------------

![image](/assets/stargatewallet/stargatemainwallet.png)

### Display Account Address

![image](/assets/stargatewallet/stargatewallet1.png)

### Display Seed

![image](/assets/stargatewallet/stargateseed1.png) ![image](/assets/stargatewallet/stargateseed2.png)

### Display Keys (Hex)

To find the keys for your own wallet please select option 3

![image](/assets/stargatewallet/cnw13.png)

You will then need to enter your wallet password

![image](/assets/stargatewallet/cnw14.png)

You will now be given a secret key and a public key. Please save these in a secure location.

![image](/assets/stargatewallet/stargateview2.png)

Command Line Help Functions
---------------------------

```
    help            this help
    address         Display user address
    balance         Display user balance
    get_tx_key      Display tx proof to prove receiver for specific transaction
    integrated_address      Display random integrated address (with encrypted payment ID)
    menu            Enable menu mode
    rescan_bc       Rescan blockchain to re-obtain transaction history
    password        Change wallet password
    payment_id      Print random Payment ID (for encrypted version see integrated_address)
    seed            Display seed
    show_transfers  Show all transactions to/from current wallet
    set             Set/get various settings
    status          Show general information and balance
    spendkey        View secret key
    transfer        Transfer/Send DERO to another address
                    Eg. transfer <address> <amount>
    transfer_all    Transfer everything to another address
    flush   Flush local wallet pool (for testing purposes)
    version         Show version
    bye             Quit wallet
    exit            Quit wallet
    quit            Quit wallet
```
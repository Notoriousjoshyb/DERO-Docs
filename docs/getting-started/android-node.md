Android DERO Node
=================

Install Termux
--------------

A fresh install of Termux will be required. This can be found here: https://f-droid.org/packages/com.termux

Termux on Android

![image](/assets/android/1.jpg)

Update Packages
---------------

To update the packages please type the following command

```
pkg update

```

![image](/assets/android/2.jpg)

Type Y and press and enter

This what updating looks like

![image](/assets/android/3.jpg)

Install wget
------------

To install wget please type following command and press enter

```
pkg install wget

```

![image](/assets/android/4.jpg)

This is what installation looks like

![image](/assets/android/5.jpg)

Download DERO Daemon
--------------------

You will now need to type the following command to download the required DERO files

```
wget https://github.com/deroproject/derohe/releases/latest/download/dero_linux_arm64.tar.gz

```

> ***NOTE:*** Please ensure you change the link to the latest release

![image](/assets/android/6.jpg)

Extract DERO Files
------------------

To extract the files please enter the following commands

```
tar -xf dero_linux_arm64.tar.gz

```

![image](/assets/android/7.jpg)

Changing Directory
------------------

You will need to move into the newly download DERO directory. You can do this using the following command

```
cd dero_linux_arm64

```

![image](/assets/android/8.jpg)

![image](/assets/android/9.jpg)

Listing Directory Contents
--------------------------

You can see what files are in the current folder by typing the following

```
ls

```

![image](/assets/android/10.jpg)

![image](/assets/android/11.jpg)

Running the DERO Daemon
-----------------------

To start the daemon you will need to type the following command

```
./derod-linux-arm64

```

![image](/assets/android/12.jpg)

> ***NOTE:*** You can zoom on Termux by pinching the screen in and out

We would like to thank our community member "secretnamebasis" for this guide on how to run DERO on Android!
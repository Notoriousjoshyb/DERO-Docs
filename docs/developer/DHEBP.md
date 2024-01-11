DHEBP (DERO Homomorphic Encryption Blockchain Protocol)
=======================================================

DHEBP alpha code to demonstrate FHE blockchain transactions.
------------------------------------------------------------

Transaction Details
-------------------

Each transaction consists of 2 parts:

1.  Statement which contains ring members keys, commitments, encrypted balances ( this grows linear ) basicaly 4 curve points per ring member.
2.  Proof which grows log in ring members for Eg : 8 ring size proof is only 1997 bytes 512 ring size proof is only 3965 bytes

Ring Size, Tx Size data
-----------------------

```
    Ring size, tx size (fixed) in bytes irrespective of balance
    2      1669 bytes   (    328 byte statement, 1341 bytes proof )
    4      2261 bytes   (    592 byte statement, 1669 bytes proof )
    8      3117 bytes   (   1120 byte statement, 1997 bytes proof )
    16     4501 bytes   (   2176 byte statement, 2325 bytes proof )
    32     6941 bytes   (   4288 byte statement, 2653 bytes proof )
    64    11493 bytes   (   8512 byte statement, 2981 bytes proof )
    128   20269 bytes   (  16960 byte statement, 3309 bytes proof )
    256   37493 bytes   (  33856 byte statement, 3637 bytes proof )
    512   71613 bytes   (  67648 byte statement, 3965 bytes proof )

```

Build
-----

1.  Switch to directory containing this Readme.md file
2.  export GOPATH=pwd
3.  go run *.go

Note: Developed and tested on linux go version 1.12.7

Output Sample
-------------

```
    Creating Transaction
    I0706 16:05:28.258801   93136 main.go:101] Transferring 10 from sender to receiver (ring size 8) tx size 3117 bytes
    I0706 16:05:28.258810   93136 main.go:102] Total tx size 3117 bytes   (  1120 byte statement, 1997 bytes proof )
    I0706 16:05:28.341387   93136 main.go:107] Transfer successful
    I0706 16:05:28.343528   93136 main.go:116]       Sender Balance        150 -        10 =       140
    I0706 16:05:28.343533   93136 main.go:117]     Receiver Balance          0 +        10 =        10
    I0706 16:05:28.345662   93136 main.go:98]

    Creating Transaction
    I0706 16:05:28.568605   93136 main.go:101] Transferring 90 from sender to receiver (ring size 16) tx size 4501 bytes
    I0706 16:05:28.568614   93136 main.go:102] Total tx size 4501 bytes   (  2176 byte statement, 2325 bytes proof )
    I0706 16:05:28.680647   93136 main.go:107] Transfer successful
    I0706 16:05:28.682788   93136 main.go:116]       Sender Balance        140 -        90 =        50
    I0706 16:05:28.682792   93136 main.go:117]     Receiver Balance         10 +        90 =       100
    I0706 16:05:28.682796   93136 main.go:74]
                            Successful
```
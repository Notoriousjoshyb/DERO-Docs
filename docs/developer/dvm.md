DERO Virtual Machine
====================

DERO Virtual Machine represents entire DERO Smart Contracts eco-system which runs on the DERO block chain.

**Documentation**

DVM is a decentralized platform that runs both public and private smart contracts: applications that run exactly as programmed without any possibility of downtime, censorship, fraud or third-party interference.Public Smart contracts are open versions. However, the DVM is being designed to support Private Smart Contracts where everything is hidden, eg parties, and information involved. Smart Contracts are nothing but rules which apply on transacting parties.

Current version of DVM is an interpretor based system to avoid security vulneribilities, issues and compiler backdoors. This also allows easy audits of Smart Contracts for quality,bug-testing and security assurances. DVM supports a new language DVM-BASIC.

DVM apps run on a from scratch custom built privacy supporting, encrypted blockchain, an enormously powerful shared global infrastructure that can move value around and represent the ownership of assets/property without leaking any information.No one knows who owns what and who transferred to whom.

-   This enables developers to create puzzles, games, voting, markets, store registries of debts or promises, move funds in accordance with instructions given long in the past (like a will or a futures contract) and many other ideas/things that have not been invented yet, all without a middleman or counterparty risk.
-   DVM-BASIC is a contract-oriented, high-level language for implementing smart contracts. It is influenced by GW-BASIC, Visual Basic and C and is designed to target the DERO Virtual Machine (DVM). It is very easy to program and very readable.
-   DVM runs Smart Contracts which are a collection of functions written in DVM-BASIC. These functions can be invoked over the blockchain to do something. SCs can act as libraries for other SCs.
-   DVM supports number of comments formats such as ', // , // as good documentation is necessary.

**Example Factorial Program**

```
    ' This is a comment
    // This comment is supported
    /* this is multi-line comment  */
    // printf is not supported in latest DVM. Please comment or remove printf from all old Smart Contracts.
     Function Factorial(s Uint64) Uint64   // this is a commment
        10  DIM result,scopy as Uint64     /* this is also comment */
        15  LET scopy =  s
        20  LET result = 1
        30  LET result = result * s
        40  LET s = s - 1
        50  IF s >= 2 THEN GOTO 30
        //60  PRINTF "FACTORIAL of %d = %d" scopy result // printf is not supported in latest DVM.
        70  RETURN result
    End Function

```

**DVM are written in a DVM-BASIC custom BASIC style language with line numbers.**

**DVM supports uint64 and string data-types.**

**DVM interprets the smart-contract and processes the SC line-line**

-   uint64 supports almost all operators namely +,-,*,/,%
-   uint64 support following bitwise operators & ,|, ^, ! , >> , <<
-   uint64 supports following logical operators >, >= , <, <=, == , !=
-   string supports only + operator. string support concatenation with a uint64.
-   string supports ==, != logical operators.
-   All DVM variables are mandatory to define and are initialized to default values namely 0 and "".

A SC execution must return 0 to persist any changes made during execution. During execution, no panics should occur.

DIM Statement
-------------

DIM stands for data in memory and is used to define variable names within a function

syntax

10 DIM variable1 as type 20 DIM variable1,variable2 as type

type can be any type supported by DVM

Defining a varible initializes a variable to its ZERO value.

Function statement
------------------

Function statement is used to define a function. See eg, below for a function which adds 2 numbers

```
    Function ADD(x uint64, y uint64) uint64
    10 RETURN x + y
    End Function

```

Function syntax is of 2 types

1.  Function function_name( 0 or more arguments )
2.  Function function_name( 0 or more arguments ) return type

The rules for functions are as follows

-   All functions begin with Function keyword
-   Function name should be alpha-numeric. If the first letter of the function is Upper case alphabet, it can be invoked by blockchain and other smart-contracts. Otherwise the function can only be called by other functions within the smart contract.
-   Function may or may not have a return type
-   All functions must use RETURN to return from function or to return a value. RETURN is mandatory.
-   All functions must end with End Function. End Function is mandatory
-   A function can have a implicit parameter value of type uint64, which contains amount of DERO value sent with the transaction.

Any error caused during processing will immediately stop execution and discard all changes that occur during SC execution.

Any Entrypoint which returns uint64 value 0 is termed as success and will make transaction to commit all state changes.

GOTO Statement
--------------

It is used to jump to any point within the function. It cannot cross function-boundary

syntax GOTO line-number

IF
--

If statement is used to evaluate expression and make decisions.It has following forms

1.  IF expr1 condition expr2 THEN GOTO line number
2.  IF expr1 condition expr2 THEN GOTO line number ELSE GOTO line number

This is used to change execution flow based on conditions. Conditions can be as complex expressions

LET Statement
-------------

LET is used to assign a value to a variable. value can be as complex as possible and can contain complex expression

syntax

line number LET variable_name = expression;

expression can invoke other functions,eg

10 LET x = 2 + 3 + ADD(2,3)

ANY assignments within DVM can only be done using LET

Return Statement
----------------

It is used to return from a function and can be used anywhere within a function

syntax

1.RETURN ( return nil ) 2.RETURN expression ( evaluates expression and returns value )

Any return value must match with the type defined while declaring function

Support Functions
-----------------

**VERSION(v String)**

-   Description: Sets a version to dvm.VERSION. Returns 1 if successful, panics otherwise.
-   Return Type: Uint64
-   ComputeCost: 1000
-   StorageCost: 0

**LOAD(variable)**

-   Description: Loads a variable which was previously stored in the blockchain using STORE function. Return type will depend on what is stored. It will panic if the value does NOT exist.
-   Return Type: Uint64/String (depending what is stored)
-   ComputeCost: 5000
-   StorageCost: 0

**EXISTS(variable)**

-   Description: Return 1 if the variable is stored in DB via STORE and 0 otherwise.
-   Return Type: Uint64
-   ComputeCost: 5000
-   StorageCost: 0

**STORE(key variable, value variable)**

-   Description: Stores key and value in the DB. All storage state of the SC is accessible only from the SC which created it. Returns 1.
-   Return Type: Uint64
-   ComputeCost: 10000
-   StorageCost: 0

**DELETE(variable)**

-   Description: Sets the rawkey value to []byte{} effectively deleting it from storage. Returns 1.
-   Return Type: Uint64
-   ComputeCost: 3000
-   StorageCost: 0

**MAPEXISTS(variable)**

-   Description: Returns 1 if the variable has been stored in RAM (current invoke session) via MAPSTORE and 0 otherwise.
-   Return Type: Uint64
-   ComputeCost: 1000
-   StorageCost: 0

**MAPGET(variable)**

-   Description: Loads a variable which was previously stored in RAM (current invoke session) via MAPSTORE. Return type will depend on what is stored. I twill panic if the value does NOT exist.
-   Return Type: Uint64/String (depending on what is stored)
-   ComputeCost: 1000
-   StorageCost: 0

**MAPSTORE(key variable, value variable)**

-   Description: Stores key and value in RAM (current invoke session). All MAPSTORE state is accessible only from the session in which it is stored. Returns 1.
-   Return Type: Uint64
-   ComputeCost: 1000
-   StorageCost: 0

**MAPDELETE(variable)**

-   Description: Deletes the element from the map in RAM (current invoke session). If the key does not exist, delete has no action. Returns 1.
-   Return Type: Uint64
-   ComputeCost: 1000
-   StorageCost: 0

**RANDOM(limit Uint64)**

-   Description: RANDOM returns a random using a PRNG seeded on BLID,SCID,TXID. First form gives a uint64, second form returns random number in the range 0 - (limit), 0 is inclusive, limit is exclusive.
-   Return Type: Uint64
-   ComputeCost: 2500
-   StorageCost: 0

**SCID()**

-   Description: Returns SMART CONTRACT ID which is currently running.
-   Return Type: String
-   ComputeCost: 2000
-   StorageCost: 0

**BLID()**

-   Description: Returns current BLOCK ID which contains current execution-in-progress TXID.
-   Return Type: String
-   ComputeCost: 2000
-   StorageCost: 0

**TXID()**

-   Description: Returns current TXID which is execution-in-progress.
-   Return Type: String
-   ComputeCost: 2000
-   StorageCost: 0

**DERO()**

-   Description: Returns a string representation of zerohash which is of type crypto.Hash.
-   Return Type: String
-   ComputeCost: 10000
-   StorageCost: 0

**BLOCK_HEIGHT()**

-   Description: Returns current chain height of BLID().
-   Return Type: Uint64
-   ComputeCost: 2000
-   StorageCost: 0

**BLOCK_TIMESTAMP()**

-   Description: Returns current timestamp of BLID().
-   Return Type: Uint64
-   ComputeCost: 2500
-   StorageCost: 0

**SIGNER()**

-   Description: Returns address of who signed this transaction. Ringsize of tx must be 2 for this value to be known or else empty.
-   Return Type: String
-   ComputeCost: 5000
-   StorageCost: 0

**UPDATE_SC_CODE(sc_code String)**

-   Description: Stores updated SC code of type string. If it is not of type string, return 0, else return 1.
-   Return Type: Uint64
-   ComputeCost: 5000
-   StorageCost: 0

**IS_ADDRESS_VALID(address String)**

-   Description: Returns 1 if address is valid, 0 otherwise.
-   Return Type: Uint64
-   ComputeCost: 50000
-   StorageCost: 0

**ADDRESS_RAW(address String)**

-   Description: Returns address in RAW form as 33 byte keys, stripping away textual/presentation form. 2 address should always be compared in RAW form.
-   Return Type: String
-   ComputeCost: 60000
-   StorageCost: 0

**ADDRESS_STRING(p String)**

-   Description: Returns address in STRING form. If it can be evaluated, a string form of an address will be returned, otherwise return an empty string.
-   Return Type: String
-   ComputeCost: 50000
-   StorageCost: 0

**SEND_DERO_TO_ADDRESS(a String, amount Uint64)**

-   Description: Sends amount DERO from SC DERO balance to a address which should be raw form. Address must be in string DERO/DETO form. If the SC does not have enough balance, it will panic.
-   Return Type: Uint64
-   ComputeCost: 70000
-   StorageCost: 0

**SEND_ASSET_TO_ADDRESS(a String, amount Uint64, asset String)**

-   Description: Sends amount ASSET from SC ASSET balance to a address which should be raw form. Address must be in string DERO/DETO form. If the SC does not have enough balance, it will panic.
-   Return Type: Uint64
-   ComputeCost: 90000
-   StorageCost: 0

**DEROVALUE()**

-   Description: Gets the amount of DERO sent within this transaction.
-   Return Type: Uint64
-   ComputeCost: 10000
-   StorageCost: 0

**ASSETVALUE(asset String)**

-   Description: Gets the amount of a given ASSET sent within this transaction.
-   Return Type: Uint64
-   ComputeCost: 10000
-   StorageCost: 0

**ATOI(s String)**

-   Description: Returns a Uint64 representation of a string. Else panic.
-   Return Type: Uint64
-   ComputeCost: 5000
-   StorageCost: 0

**ITOA(n Uint64)**

-   Description: Returns string representation of a Uint64. Else panic.
-   Return Type: String
-   ComputeCost: 5000
-   StorageCost: 0

**SHA256(s String)**

-   Description: Returns a string sha2-256 hash of a given string. Else panic.
-   Return Type: String
-   ComputeCost: 25000
-   StorageCost: 0

**SHA3256(s String)**

-   Description: Returns a string sha3-256 hash of a given string. Else panic.
-   Return Type: String
-   ComputeCost: 25000
-   StorageCost: 0

**KECCAK256(s String)**

-   Description: Returns a string sha3-keccak256 hash of a given string. Else panic.
-   Return Type: String
-   ComputeCost: 25000
-   StorageCost: 0

**HEX(s String)**

-   Description: Returns a hex encoded string value of a given string. Else panic.
-   Return Type: String
-   ComputeCost: 10000
-   StorageCost: 0

**HEXDECODE(s String)**

-   Description: Returns a hex decoded string value of a given hex string. Else panic.
-   Return Type: String
-   ComputeCost: 10000
-   StorageCost: 0

**MIN(f Uint64, s Uint64)**

-   Description: Returns the minimum value of 2 Uint64 values. Else panic.
-   Return Type: Uint64
-   ComputeCost: 5000
-   StorageCost: 0

**MAX(f Uint64, s Uint64)**

-   Description: Returns the maximum value of 2 Uint64 values. Else panic.
-   Return Type: Uint64
-   ComputeCost: 5000
-   StorageCost: 0

**STRLEN(s String)**

-   Description: Returns the length of a given string in Uint64. Else panic.
-   Return Type: Uint64
-   ComputeCost: 20000
-   StorageCost: 0

**SUBSTR(s String, offset Uint64, length Uint64)**

-   Description: Returns the substring of a given string with offset and length defined. Else panic.
-   Return Type: String
-   ComputeCost: 20000
-   StorageCost: 0

**PANIC**

-   Description: Panics.
-   Return Type: Panic
-   ComputeCost: 10000
-   StorageCost: 0

Lottery SC Guide
----------------

**Dero Stargate DVM Smart Contracts guide to install and test various function of lottery Smart Contract.**

**Download** DERO Stargate testnet `source <https://github.com/deroproject/derohe>`* and `binaries. <https://github.com/deroproject/derohe/releases>`*

./derod-linux-amd64 --testnet;

**Start DERO wallet in testnet.**

dero-wallet-cli-linux-amd64 --rpc-server --wallet-file testnet.wallet --testnet;

**Start Dero wallet second instance to test transfer/ownership functions etc.**

```
dero-wallet-cli-linux-amd64 --wallet-file testnet2.wallet --testnet --rpc-server --rpc-bind=127.0.0.1:40403;

```

**Dero testnet Explorer**

`./explorer-linux-amd64 --rpc-server-address 127.0.0.1:30306 --http-address=0.0.0.0:8080;`

**DERO Stargate Testnet Explorer**

https://testnetexplorer.dero.io/

**Installing Smart Contract**

Download Lottery.bas <https://git.dero.io/DeroProject/derosuite_stargate/src/master/cmd/dvm/lottery.bas>

curl --request POST --data-binary @lottery.bas http://127.0.0.1:40403/install_sc;

Download SC Code,check balance and variables from chain

```
curl http://127.0.0.1:40402/json_rpc -d '{"jsonrpc":"2.0","id":"0","method":"getsc","params":{ "scid":"aacaa7bb2388d06e523e5bc0783e4e131738270641406c12978155ba033373af" , "code":false, "keysstring":["deposit_count"]}}' -H 'Content-Type: application/json';

```

**Examples of various lottery Smart Contract functions Eg: To play lottery**

`curl http://127.0.0.1:40403/json_rpc -d '{"jsonrpc":"2.0","id":"0","method":"transfer","params":{ "transfers":[{"amount":111111,"destination":"deto1qxqqen6lqmksmzmxmfqmxp2y8zvkldtcq8jhkzqflmyczepjw9dp46gc3cczu"}],"scid":"aacaa7bb2388d06e523e5bc0783e4e131738270641406c12978155ba033373af","sc_rpc":[{"name":"entrypoint","datatype":"S","value":"Lottery"}] }}' -H 'Content-Type: application/json';`

**Eg: Withdraw balance only for smart contract owner**

`curl http://127.0.0.1:40403/json_rpc -d '{"jsonrpc":"2.0","id":"0","method":"transfer","params":{ "transfers":[{"amount":111111,"destination":"deto1qxqqen6lqmksmzmxmfqmxp2y8zvkldtcq8jhkzqflmyczepjw9dp46gc3cczu"}],"scid":"aacaa7bb2388d06e523e5bc0783e4e131738270641406c12978155ba033373af", "sc_rpc":[{"name":"entrypoint","datatype":"S","value":"Withdraw"}, {"name":"amount","datatype":"U","value":2 }] }}' -H 'Content-Type: application/json';`

**Eg: To transfer ownership**

`curl http://127.0.0.1:40403/json_rpc -d '{"jsonrpc":"2.0","id":"0","method":"transfer","params":{ "transfers":[{"amount":111111,"destination":"deto1qxqqen6lqmksmzmxmfqmxp2y8zvkldtcq8jhkzqflmyczepjw9dp46gc3cczu"}],"scid":"aacaa7bb2388d06e523e5bc0783e4e131738270641406c12978155ba033373af", "sc_rpc":[{"name":"entrypoint","datatype":"S","value":"TransferOwnership"}, {"name":"newowner","datatype":"S","value":"deto1qxsplx7vzgydacczw6vnrtfh3fxqcjevyxcvlvl82fs8uykjkmaxgfgulfha5" }] }}' -H 'Content-Type: application/json';`

**Eg: To claim ownership**

`curl http://127.0.0.1:40403/json_rpc -d â€˜{â€œjsonrpcâ€:â€œ2.0â€,â€œidâ€:â€œ0â€,â€œmethodâ€:â€œtransferâ€,â€œparamsâ€:{ â€œtransfersâ€:[{â€œamountâ€:111111,â€œdestinationâ€:â€œdeto1qxqqen6lqmksmzmxmfqmxp2y8zvkldtcq8jhkzqflmyczepjw9dp46gc3cczuâ€}],â€œscidâ€:â€œaacaa7bb2388d06e523e5bc0783e4e131738270641406c12978155ba033373afâ€, â€œsc_rpcâ€:[{â€œnameâ€:â€œentrypointâ€,â€œdatatypeâ€:â€œSâ€,â€œvalueâ€:â€œClaimOwnershipâ€}] }}â€™ -H â€˜Content-Type: application/jsonâ€™;`

Lottery.bas
-----------

```
    /* Lottery Smart Contract in DVM-BASIC

```

This lottery smart contract will give lottery wins every xth try. */

```
    Function Lottery(value Uint64) Uint64
10  dim deposit_count,winner as Uint64
20  LET deposit_count =  LOAD("deposit_count")+1
25  IF value == 0 THEN GOTO 110  // if deposit amount is 0, simply return
30  STORE("depositor_address" + (deposit_count-1), SIGNER()) // store address for later on payment
40  STORE("deposit_total", LOAD("deposit_total") + value )
50  STORE("deposit_count",deposit_count)
60  IF LOAD("lotteryeveryXdeposit") > deposit_count THEN GOTO 110 // we will wait till X players join in
  // we are here means all players have joined in, roll the DICE,
70  LET winner  = RANDOM() % deposit_count // we have a winner
80  SEND_DERO_TO_ADDRESS(LOAD("depositor_address" + winner) , LOAD("lotterygiveback")*LOAD("deposit_total")/10000)

        // Re initialize for another round
90   STORE("deposit_count", 0)   //  initial players
100  STORE("deposit_total", 0)   //  total deposit of all players
110  RETURN 0
End Function

// this function is used to initialize parameters during install time
Function Initialize() Uint64
10  STORE("owner", SIGNER())   // store in DB  ["owner"] = address
20  STORE("lotteryeveryXdeposit", 2)   // lottery will reward every X deposits
    // how much will lottery giveback in 1/10000 parts, granularity .01 %
30  STORE("lotterygiveback", 9900)   // lottery will give reward 99% of deposits, 1 % is accumulated for owner to withdraw
33  STORE("deposit_count", 0)   //  initial players
34  STORE("deposit_total", 0)   //  total deposit of all players
// 35 printf "Initialize executed"
40 RETURN 0
End Function

// Used to tune lottery parameters
Function TuneLotteryParameters(input Uint64, lotteryeveryXdeposit Uint64, lotterygiveback Uint64) Uint64
10  dim key,stored_owner as String
20  dim value_uint64 as Uint64
30  IF LOAD("owner") == SIGNER() THEN GOTO 100  // check whether owner is real owner
40  RETURN 1

100  STORE("lotteryeveryXdeposit", lotteryeveryXdeposit)   // lottery will reward every X deposits
130  STORE("lotterygiveback", value_uint64)   // how much will lottery giveback in 1/10000 parts, granularity .01 %
140  RETURN 0 // return success
End Function

// This function is used to change owner
// owner is an string form of address
Function TransferOwnership(newowner String) Uint64
10  IF LOAD("owner") == SIGNER() THEN GOTO 30
20  RETURN 1
30  STORE("tmpowner",ADDRESS_RAW(newowner))
40  RETURN 0
End Function

// Until the new owner claims ownership, existing owner remains owner
    Function ClaimOwnership() Uint64
10  IF LOAD("tmpowner") == SIGNER() THEN GOTO 30
20  RETURN 1
30  STORE("owner",SIGNER()) // ownership claim successful
40  RETURN 0
End Function

// if signer is owner, withdraw any requested funds
// if everthing is okay, they will be showing in signers wallet
    Function Withdraw( amount Uint64) Uint64
10  IF LOAD("owner") == SIGNER() THEN GOTO 30
20  RETURN 1
30  SEND_DERO_TO_ADDRESS(SIGNER(),amount)
40  RETURN 0
End Function

// if signer is owner, provide him rights to update code anytime
// make sure update is always available to SC
    Function UpdateCode( code String) Uint64
10  IF LOAD("owner") == SIGNER() THEN GOTO 30
20  RETURN 1
30  UPDATE_SC_CODE(code)
40  RETURN 0
End Function

```

Token SC Guide
--------------

**Dero Stargate DVM Smart Contracts guide to install and test various function of private token Smart Contract.**

Notes: 1. All wallet Addressess need to be registerd first with SC before they need to interact with. This condition will be removed in future. 2. Requirement of detoAnyRandomAddressFromExplorer during SC invocation will be removed in future. 3. burn is equal to deposit if SCID is defined else DERO/token will dissappear/burn from network forever. burn will renamed to something more meaningful. This can be proved with cryptographic proof.

**Download** DERO Stargate testnet `source <https://github.com/deroproject/derohe>`* and `binaries. <https://github.com/deroproject/derohe/releases>`*

**Start Dero daemon in testnet mode**

```
./derod-linux-amd64  --testnet;

```

**Start Dero wallet in testnet.**

```
dero-wallet-cli-linux-amd64 --rpc-server --wallet-file testnet.wallet --testnet;

```

**Start Dero wallet second instance to test transfer/ownership functions etc.**

```
dero-wallet-cli-linux-amd64 --wallet-file testnet2.wallet --testnet --rpc-server --rpc-bind=127.0.0.1:40403;

```

**Dero testnet Explorer, Not required but if you want to host your own explorer for privacy reasons.**

```
./explorer-linux-amd64  --http-address=0.0.0.0:8080 ;

```

**Connect to explorer using browser on localhost:8080**

**Dero Stargate Testnet Explorer** https://testnetexplorer.dero.io/

**To send DERO to multiple users in one transaction**

```
curl http://127.0.0.1:40403/json_rpc -d '{"jsonrpc":"2.0","id":"0","method":"transfer","params":{ "transfers":[{"amount":100000,"destination":"deto1ADDRESS1"},{"amount":300000,"destination":"deto1ADDRESS12}] }}' -H 'Content-Type: application/json';

```

**DERO has 2 types of SCs, public and private.**

1.Public SCs are public with all data/code/exchanges are public. 2.Private SCs have their smart contract data public. But no one knows how many tokens a particular user own or how much is he sending or how much is he receiving. Best example is to understand private SCs as banks and private tokens as cash. Once cash is out from the bank, Bank doesnâ€™t know â€œwho has what amount or how is it being used/sent/received etc.â€. This makes all private tokens completely private.

**Installing Private Smart Contract.**

Download token.bas <https://git.dero.io/DeroProject/derosuite_stargate/src/master/cmd/dvm/token.bas>

```
curl  --request POST --data-binary   @token.bas http://127.0.0.1:40403/install_sc;

```

**To check private token balance in wallet, type this command in wallet.**

```
balance SCID;

```

**Download SC Code,check SC balance and variables from chain**

```
curl http://127.0.0.1:40402/json_rpc -d '{"jsonrpc":"2.0","id":"0","method":"getsc","params":{ "scid":"aacaa7bb2388d06e523e5bc0783e4e131738270641406c12978155ba033373af" , "code":true}}' -H 'Content-Type: application/json';

```

Examples of various private token Smart Contract functions Eg: To send private tokens from one wallet to another wallet, this does not involve SC Eg: this also showcases to send multiple assets( DERO and other tokens on DERO Network) within a single transaction

```
curl http://127.0.0.1:40403/json_rpc -d '{"jsonrpc":"2.0","id":"0","method":"transfer","params":{ "transfers":[{"amount":111111,"destination":"deto1qxqqen6lqmksmzmxmfqmxp2y8zvkldtcq8jhkzqflmyczepjw9dp46gc3cczu"},{"amount":333333,"destination":"deto1qxqqen6lqmksmzmxmfqmxp2y8zvkldtcq8jhkzqflmyczepjw9dp46gc3cczu","scid": "aacaa7bb2388d06e523e5bc0783e4e131738270641406c12978155ba033373af" }] }}' -H 'Content-Type: application/json';

```

Eg: Convert DERO to tokens 1:1 swap, we are swapping 44 DERO atomic units to get some tokens

```
curl http://127.0.0.1:40403/json_rpc -d '{"jsonrpc":"2.0","id":"0","method":"transfer","params":{"transfers":[{"amount":1,"destination":"deto1qxqqen6lqmksmzmxmfqmxp2y8zvkldtcq8jhkzqflmyczepjw9dp46gc3cczu", "burn":44}],"scid":"aacaa7bb2388d06e523e5bc0783e4e131738270641406c12978155ba033373af", "sc_rpc":[{"name":"entrypoint","datatype":"S","value":"IssueTOKENX"}] }}' -H 'Content-Type: application/json';

```

Convert tokens to DERO 1:1 swap, we are swapping 9 token atomic units to get 9 DERO atomic units This tx shows transferring tokens natively, no dero fees etc, this is under evaluation, **Currently these show as coinbase rewards**

```
curl http://127.0.0.1:40403/json_rpc -d '{"jsonrpc":"2.0","id":"0","method":"transfer","params":{"transfers":[{"scid":"aacaa7bb2388d06e523e5bc0783e4e131738270641406c12978155ba033373af", "amount":1,"destination":"deto1qxqqen6lqmksmzmxmfqmxp2y8zvkldtcq8jhkzqflmyczepjw9dp46gc3cczu", "burn":9}],"scid":"aacaa7bb2388d06e523e5bc0783e4e131738270641406c12978155ba033373af", "sc_rpc":[{"name":"entrypoint","datatype":"S","value":"ConvertTOKENX"}] }}' -H 'Content-Type: application/json';

```

Eg: To withdraw balance only for smart contract owner

```
curl http://127.0.0.1:40403/json_rpc -d '{"jsonrpc":"2.0","id":"0","method":"transfer","params":{ "transfers":[{"amount":111111,"destination":"deto1qxqqen6lqmksmzmxmfqmxp2y8zvkldtcq8jhkzqflmyczepjw9dp46gc3cczu"}],"scid":"aacaa7bb2388d06e523e5bc0783e4e131738270641406c12978155ba033373af", "sc_rpc":[{"name":"entrypoint","datatype":"S","value":"Withdraw"}, {"name":"amount","datatype":"U","value":2 }] }}' -H 'Content-Type: application/json';

```

Eg: To transfer ownership of smart contract to new address/owner

```
curl http://127.0.0.1:40403/json_rpc -d '{"jsonrpc":"2.0","id":"0","method":"transfer","params":{ "transfers":[{"amount":111111,"destination":"deto1qxqqen6lqmksmzmxmfqmxp2y8zvkldtcq8jhkzqflmyczepjw9dp46gc3cczu"}],"scid":"aacaa7bb2388d06e523e5bc0783e4e131738270641406c12978155ba033373af", "sc_rpc":[{"name":"entrypoint","datatype":"S","value":"TransferOwnership"}, {"name":"newowner","datatype":"S","value":"deto1qxsplx7vzgydacczw6vnrtfh3fxqcjevyxcvlvl82fs8uykjkmaxgfgulfha5" }] }}' -H 'Content-Type: application/json';

```

Eg: To claim ownership of smart contract

```
curl http://127.0.0.1:40403/json_rpc -d '{"jsonrpc":"2.0","id":"0","method":"transfer","params":{ "transfers":[{"amount":111111,"destination":"deto1qxqqen6lqmksmzmxmfqmxp2y8zvkldtcq8jhkzqflmyczepjw9dp46gc3cczu"}],"scid":"aacaa7bb2388d06e523e5bc0783e4e131738270641406c12978155ba033373af", "sc_rpc":[{"name":"entrypoint","datatype":"S","value":"ClaimOwnership"}] }}' -H 'Content-Type: application/json';

```

Eg: To update smart contract code

```
curl http://127.0.0.1:40403/json_rpc -d '{"jsonrpc":"2.0","id":"0","method":"transfer","params":{ "transfers":[{"amount":111111,"destination":"deto1qxqqen6lqmksmzmxmfqmxp2y8zvkldtcq8jhkzqflmyczepjw9dp46gc3cczu"}],"scid":"aacaa7bb2388d06e523e5bc0783e4e131738270641406c12978155ba033373af", "sc_rpc":[{"name":"entrypoint","datatype":"S","value":"UpdateCode"}, {"name":"code","datatype":"S","value":"new code should be placed here" }] }}' -H 'Content-Type: application/json';

```

Token.bas
---------

```
/* Private Token Smart Contract Example in DVM-BASIC.

```

DERO Smart Contracts Tokens privacy can be understood just like banks handle cash. Once cash is out from the bank, bank is not aware about it (who owns what value), until it is deposited back. Smart contract only maintains supply and other necessary items to keep it working. DERO Tokens can be tranfered to other wallets just like native DERO with Homomorphic Encryption and without involvement of issuing Smart Contracts. Token issuing Smart Contract cannot hold/freeze/control their tokens once they are issued and sent to any wallet. This token is Private. Use Function InitializePrivate() Uint64 to make any Smart Contract private.

```
*/

// Issue tokens after depositing DERO (Convert DERO to TOKENX)
Function IssueTOKENX() Uint64
10  SEND_ASSET_TO_ADDRESS(SIGNER(), DEROVALUE(),SCID())   // Increment balance of user, without knowing original balance, this is done homomorphically
20  RETURN 0
End Function

// Convert TOKENX to DERO after depositing TOKENX. Smart Contract can give DERO, Only if DERO balance exists.
Function ConvertTOKENX() Uint64
10  SEND_DERO_TO_ADDRESS(SIGNER(),ASSETVALUE(SCID()))   // Increment balance of user, without knowing original balance, this is done using Homomorphic Encryption.
20  RETURN 0
End Function

// This function is used to initialize parameters during install time
// InitializePrivate initializes a private SC
Function InitializePrivate() Uint64
10  STORE("owner", SIGNER())   // Store in DB  ["owner"] = address

```

30 SEND_ASSET_TO_ADDRESS(SIGNER(), 1600000, SCID()) // Gives initial encrypted balance of 1600000. 40 RETURN 0 End Function

```
// This function is used to change owner
// owner is an string form of address
Function TransferOwnership(newowner String) Uint64
10  IF LOAD("owner") == SIGNER() THEN GOTO 30
20  RETURN 1
30  STORE("tmpowner",ADDRESS_RAW(newowner))
40  RETURN 0
End Function

// Until the new owner claims ownership, existing owner remains owner
    Function ClaimOwnership() Uint64
10  IF LOAD("tmpowner") == SIGNER() THEN GOTO 30
20  RETURN 1
30  STORE("owner",SIGNER()) // ownership claim successful
40  RETURN 0
End Function

// if signer is owner, withdraw any requested funds
// if everthing is okay, they will be showing in signers wallet

```

Function Withdraw( amount Uint64) Uint64 10 IF LOAD("owner") == SIGNER() THEN GOTO 30 20 RETURN 1 30 SEND_DERO_TO_ADDRESS(SIGNER(),amount) 40 RETURN 0 End Function

```
// if signer is owner, provide him rights to update code anytime
    // make sure update is always available to SC
    Function UpdateCode( code String) Uint64
10  IF LOAD("owner") == SIGNER() THEN GOTO 30
20  RETURN 1
30  UPDATE_SC_CODE(code)
40  RETURN 0
End Function

```

ASSETS Interchange Smart Contract
---------------------------------

This Smart Contract converts assetOne to assetTwo as per defined ratio in contract. Provided exchange has sufficient assets balances.

**Steps to create an exchange contract.**

First create two tokens and deposit it to exchange. Then anyone can use exchange smart contract for conversion of assets.

Step 1] https://github.com/deroproject/documentation/tree/master/DVMDOCS/examples/token

`curl --request POST --data-binary @token.bas http://127.0.0.1:40403/install_sc`

Step 2] https://github.com/deroproject/documentation/tree/master/DVMDOCS/examples/token

`curl --request POST --data-binary @token2.bas http://127.0.0.1:40403/install_sc`

STEP 3] Create and install https://github.com/deroproject/documentation/blob/master/DVMDOCS/examples/assetexchange/asset_exchange.bas

`curl --request POST --data-binary @asset_exchange.bas http://127.0.0.1:40403/install_sc`

Step 4] Deposit assetOne/token1 to exchange contract.

`curl --silent http://127.0.0.1:40403/json_rpc -d '{"jsonrpc":"2.0","id":"0","method":"transfer","params":{"scid":"'"Interchange-SCID"'","ringsize":2, "sc_rpc":[{"name":"entrypoint","datatype":"S","value":"Deposit"}], "transfers": [ {"scid":"'"ASSET_ONE_SCID"'", "burn":AssetOneCount_DEPOSITED_TO_EXCHANGE}] }}' -H 'Content-Type: application/json'`

Step 5] Deposit assetTwo/token2 to exchange contract.

`curl --silent http://127.0.0.1:40403/json_rpc -d '{"jsonrpc":"2.0","id":"0","method":"transfer","params":{"scid":"'"Interchange-SCID"'","ringsize":2, "sc_rpc":[{"name":"entrypoint","datatype":"S","value":"Interchange"},{"name":"incoming","datatype":"H","value":"'"ASSET_ONE_SCID"'"},{"name":"outgoing","datatype":"H","value":"'"ASSET_TWO_SCID"'"}], "transfers": [{"scid":"'"ASSET_ONE_SCID"'", "burn":AssetOneCount_TO_BE__Converted}] }}' -H 'Content-Type: application/json'`

step 7] In wallet check balance of assetTwo.

balance ASSET_TWO_SCID

**NB: Following used above are variables, please change them. SCIDs are transaction-IDs returned by respective commands.**

Interchange-SCID ASSET_ONE_SCID ASSET_TWO_SCID AssetOneCount_DEPOSITED_TO_EXCHANGE AssetTwoCount_DEPOSITED_TO_EXCHANGE AssetOneCount_TO_BE__Converted

Asset.bas
---------

/* Private Token Smart Contract Example in DVM-BASIC.\
DERO Smart Contracts Tokens privacy can be understood just like banks handle cash. Once cash is out from the bank, bank is not aware about it (who owns what value), until it is deposited back. Smart contract only maintains supply and other necessary items to keep it working. DERO Tokens can be tranfered to other wallets just like native DERO with Homomorphic Encryption and without involvement of issuing Smart Contracts. Token issuing Smart Contract cannot hold/freeze/control their tokens once they are issued and sent to any wallet. This token is Private. Use Function InitializePrivate() Uint64 to make any Smart Contract private.

```
*/

// Issue Asset after depositing DERO (Convert DERO to TOKENX)
Function IssueAsset() Uint64
10  SEND_ASSET_TO_ADDRESS(SIGNER(), DEROVALUE(),SCID())   // send asset without knowing original balance, this is done homomorphically
20  RETURN 0
End Function

// This function is used to initialize parameters during install time
// InitializePrivate initializes a private SC
Function InitializePrivate() Uint64
40  RETURN 0
End Function

```

Assetexchange.bas
-----------------

```
   // Asset Interchange/Exchnage  Smart Contract Example in DVM-BASIC.
//    This SC allows you to deposit an arbitrary token, into it
//    and later allows you to swap one token with another
// if the SC has enough balance to cover outgoing transfer it will be done

    // deposits an arbitrary token
    //  owner should deposits all arbitrary types

   Function Deposit() Uint64
    20  RETURN 0
    End Function

// incoming represents incoming asset type basicallly an SCID
// outgoing represents outgoing asset type basicallly an SCID
   Function Interchange(incoming String, outgoing String) Uint64
    10  SEND_ASSET_TO_ADDRESS(SIGNER(),ASSETVALUE(incoming)/2, outgoing)   // 1:1/2 interchange of assets
    20  RETURN 0
    End Function

    Function Initialize() Uint64
    10 STORE("owner", SIGNER())   // store in DB  ["owner"] = address
    40  RETURN 0
    End Function

// everything below this is supplementary and not required

    // This function is used to change owner
    // owner is an string form of address
    Function TransferOwnership(newowner String) Uint64
    10  IF LOAD("owner") == SIGNER() THEN GOTO 30
    20  RETURN 1
    30  STORE("tmpowner",ADDRESS_RAW(newowner))
    40  RETURN 0
    End Function

    // Until the new owner claims ownership, existing owner remains owner
        Function ClaimOwnership() Uint64
    10  IF LOAD("tmpowner") == SIGNER() THEN GOTO 30
    20  RETURN 1
    30  STORE("owner",SIGNER()) // ownership claim successful
    40  RETURN 0
    End Function

    // if signer is owner, withdraw any requested funds
    // if everthing is okay, they will be showing in signers wallet
   Function Withdraw(amount Uint64, asset String) Uint64
    10  IF LOAD("owner") == SIGNER() THEN GOTO 30
    20  RETURN 1
    30  SEND_ASSET_TO_ADDRESS(SIGNER(),amount,asset)
    40  RETURN 0
    End Function

    // if signer is owner, provide him rights to update code anytime
        // make sure update is always available to SC
        Function UpdateCode( code String) Uint64
    10  IF LOAD("owner") == SIGNER() THEN GOTO 30
    20  RETURN 1
    30  UPDATE_SC_CODE(code)
    40  RETURN 0
    End Function

```

Nameservice
-----------

**Register and associate DERO wallet to username.**

Step 1] Check whether username is already registered. You cannot register username if already registered.

`curl http://127.0.0.1:40402/json_rpc -d '{"jsonrpc":"2.0","id":"0","method":"nametoaddress","params":{"name":"TESTUSERNAME" }}' -H 'Content-Type: application/json'`

Step 2] Register and associate DERO wallet to username.

`curl http://127.0.0.1:40403/json_rpc -d '{"jsonrpc":"2.0","id":"0","method":"scinvoke","params":{"scid":"0000000000000000000000000000000000000000000000000000000000000001","ringsize":2, "sc_rpc":[{"name":"entrypoint","datatype":"S","value":"Register"}, {"name":"name","datatype":"S","value":"TESTUSERNAME" }] }}' -H 'Content-Type: application/json'`

**NB: Replace TESTUSERNAME with your desired available username in abvove steps.**

**NB: "scid":"0000000000000000000000000000000000000000000000000000000000000001" is reserved for nameservice registration.**

Nameservice.bas
---------------

```
   /* Name Service SMART CONTRACT in DVM-BASIC.
   Allows a user to register names which could be looked by wallets for easy to use name while transfer
*/

 // This function is used to initialize parameters during install time
    Function Initialize() Uint64
    10  RETURN 0
    End Function

    // Register a name, limit names of 5 or less length
    Function Register(name String) Uint64
    10  IF EXISTS(name) THEN GOTO 50   // if name is already used, it cannot reregistered
    20  IF STRLEN(name) >= 6 THEN GOTO 40
    30  IF SIGNER() != address_raw("deto1qyvyeyzrcm2fzf6kyq7egkes2ufgny5xn77y6typhfx9s7w3mvyd5qqynr5hx") THEN GOTO 50
    40  STORE(name,SIGNER())
    50  RETURN 0
    End Function

    // This function is used to change owner
    // owner is an string form of address
    Function TransferOwnership(name String,newowner String) Uint64
    10  IF LOAD(name) != SIGNER() THEN GOTO 30
    20  STORE(name,ADDRESS_RAW(newowner))
    30  RETURN 0
    End Function
```
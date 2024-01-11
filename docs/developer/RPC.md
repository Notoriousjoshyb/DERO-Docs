DERO Stargate RPC API
=====================

Daemon RPC API
--------------

### Echo

Test endpoint to verify that the RPC server is enabled and working well on the daemon side.

**Available parameters**

![image](/assets/rpcapistargate/rpc1.PNG)

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "DERO.Echo",
    "params": ["Hello", "World", "!"]
}

```

**cURL Request**

```
curl -X POST\
    http://127.0.0.1:40402/json_rpc\
    -H 'content-type: application/json'\
    -d '{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "DERO.Echo",
    "params": ["Hello", "World", "!"]
}'

```

**Result**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "result": "DERO Hello World !"
}

```

### Ping

Simple Ping request

**Available Parameters**

No Parameters

**Body**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "DERO.Ping"
}

```

**cURL Request**

```
curl -X POST\
  http://127.0.0.1:40402/json_rpc\
  -H 'content-type: application/json'\
  -d '{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "DERO.Ping"
}'

```

**Result**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "result": "Pong "
}

```

### Get Info

Returns all infos

**Available Parameters**

No Parameters

**Body**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "DERO.GetInfo"
}

```

**cURL Request**

```
curl -X POST\
  http://127.0.0.1:40402/json_rpc\
  -H 'content-type: application/json'\
  -d '{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "DERO.GetInfo"
}'

```

**Result**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "result": {
        "alt_blocks_count": 0,
        "difficulty": 23467,
        "grey_peerlist_size": 0,
        "height": 35995,
        "stableheight": 35987,
        "topoheight": 35995,
        "treehash": "2C4A2F8954EA978104D9F4A4D170256B2531F62C30E52A11517FB6375A0D5F29",
        "averageblocktime50": 17.63982,
        "incoming_connections_count": 0,
        "outgoing_connections_count": 0,
        "target": 18,
        "target_height": 0,
        "testnet": true,
        "network": "",
        "top_block_hash": "7ed9939d4c910876ef04312cfefe724d62c18c6b8fb2ab342e9671c511c69b88",
        "tx_count": 0,
        "tx_pool_size": 0,
        "dynamic_fee_per_kb": 0,
        "total_supply": 0,
        "median_block_size": 0,
        "white_peerlist_size": 0,
        "version": "3.4.106-0.DEROHE.STARGATE+18012022",
        "status": "OK"
    }
}

```

### Get Block

Returns all the information of the requested block.

**Available parameters**

![image](/assets/rpcapistargate/rpc2.PNG)

**Body**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "DERO.GetBlock",
    "params": {
        "height": 420
    }
}

```

**cURL Request**

```
curl -X POST\
  http://127.0.0.1:40402/json_rpc\
  -H 'content-type: application/json'\
  -d '{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "DERO.GetBlock",
    "params": {
        "height": 420
    }
}'

```

**Result**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "result": {
        "blob": "01010000017e9e872cb1a403010000021f9bcc1208dee302769931ad378a4c0c4b2c21b0cfb3e752607e12d2b6fa6425000000000000000000000000000000000000000000000000000000000000000000016a6856b51e9ffd5b07c6c33ca635d984910f3b7fbbaaaebbb61a99780629e4490a41ee3400000001a46a6856b500000000eec07ce3efc1425bc0ad7e8c72d13b0500000000940d24de2854e800a2da520141f38100000001a46a6856b500000000c3443540c243d11f706b6836d516a95500000000d0bd228895e3da00ef774a0441f49600000001a46a6856b500000000eec07ce3efc1425bc0ad7e8c72d13b050000000064bdff4901054101003a190041fdd400000001a46a6856b500000000eec07ce3efc1425bc0ad7e8c72d13b05000000000cf2b45163efe300a2efe6014105a100000001a46a6856b500000000c3443540c243d11f706b6836d516a95500000000e57c84673a12fe00ef9e52044105ca00000001a46a6856b500000000eec07ce3efc1425bc0ad7e8c72d13b0500000000acb0839b3a13a400a2f8010141082a00000001a46a6856b500000000c3443540c243d11f706b6836d516a955000000006d01841f72304000efa43e0441086d00000001a46a6856b500000000c3443540c243d11f706b6836d516a955000000003fd27e20d1ab8800efca2901410d7200000001a46a6856b500000000c3443540c243d11f706b6836d516a955000000000b1fb80d5442e400a29c8e02712cb100000001a46a6856b500000000a063e24bc973c78fd057fec97cacd720000000006bb830fa72959300eff8080400",
        "json": "{\"major_version\":1,\"minor_version\":1,\"timestamp\":1643337166001,\"height\":420,\"miner_tx\":{\"version\":1,\"source_network\":0,\"dest_network\":0,\"txtype\":2,\"value\":0,\"miner_address\":[31,155,204,18,8,222,227,2,118,153,49,173,55,138,76,12,75,44,33,176,207,179,231,82,96,126,18,210,182,250,100,37,0],\"c\":[0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],\"s\":[0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],\"height\":0,\"blid\":[0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],\"scdata\":null,\"Payloads\":null},\"tips\":[\"6a6856b51e9ffd5b07c6c33ca635d984910f3b7fbbaaaebbb61a99780629e449\"],\"miniblocks\":[{\"Version\":1,\"HighDiff\":false,\"Final\":false,\"PastCount\":1,\"Timestamp\":60980,\"Height\":420,\"Past\":[1785222837,0],\"KeyHash\":\"eec07ce3efc1425bc0ad7e8c72d13b0500000000000000000000000000000000\",\"Flags\":0,\"Nonce\":[2483889374,676653056,2732216833]},{\"Version\":1,\"HighDiff\":false,\"Final\":false,\"PastCount\":1,\"Timestamp\":62337,\"Height\":420,\"Past\":[1785222837,0],\"KeyHash\":\"c3443540c243d11f706b6836d516a95500000000000000000000000000000000\",\"Flags\":0,\"Nonce\":[3502056072,2514737664,4017572356]},{\"Version\":1,\"HighDiff\":false,\"Final\":false,\"PastCount\":1,\"Timestamp\":62614,\"Height\":420,\"Past\":[1785222837,0],\"KeyHash\":\"eec07ce3efc1425bc0ad7e8c72d13b0500000000000000000000000000000000\",\"Flags\":0,\"Nonce\":[1690173257,17121537,3807488]},{\"Version\":1,\"HighDiff\":false,\"Final\":false,\"PastCount\":1,\"Timestamp\":64980,\"Height\":420,\"Past\":[1785222837,0],\"KeyHash\":\"eec07ce3efc1425bc0ad7e8c72d13b0500000000000000000000000000000000\",\"Flags\":0,\"Nonce\":[217232465,1676665600,2733630977]},{\"Version\":1,\"HighDiff\":false,\"Final\":false,\"PastCount\":1,\"Timestamp\":1441,\"Height\":420,\"Past\":[1785222837,0],\"KeyHash\":\"c3443540c243d11f706b6836d516a95500000000000000000000000000000000\",\"Flags\":0,\"Nonce\":[3850142823,974323200,4020130308]},{\"Version\":1,\"HighDiff\":false,\"Final\":false,\"PastCount\":1,\"Timestamp\":1482,\"Height\":420,\"Past\":[1785222837,0],\"KeyHash\":\"eec07ce3efc1425bc0ad7e8c72d13b0500000000000000000000000000000000\",\"Flags\":0,\"Nonce\":[2897249179,974365696,2734162177]},{\"Version\":1,\"HighDiff\":false,\"Final\":false,\"PastCount\":1,\"Timestamp\":2090,\"Height\":420,\"Past\":[1785222837,0],\"KeyHash\":\"c3443540c243d11f706b6836d516a95500000000000000000000000000000000\",\"Flags\":0,\"Nonce\":[1828815903,1915764736,4020518404]},{\"Version\":1,\"HighDiff\":false,\"Final\":false,\"PastCount\":1,\"Timestamp\":2157,\"Height\":420,\"Past\":[1785222837,0],\"KeyHash\":\"c3443540c243d11f706b6836d516a95500000000000000000000000000000000\",\"Flags\":0,\"Nonce\":[1070759456,3517679616,4023003393]},{\"Version\":1,\"HighDiff\":false,\"Final\":false,\"PastCount\":1,\"Timestamp\":3442,\"Height\":420,\"Past\":[1785222837,0],\"KeyHash\":\"c3443540c243d11f706b6836d516a95500000000000000000000000000000000\",\"Flags\":0,\"Nonce\":[186628109,1413669888,2728168962]},{\"Version\":1,\"HighDiff\":true,\"Final\":true,\"PastCount\":1,\"Timestamp\":11441,\"Height\":420,\"Past\":[1785222837,0],\"KeyHash\":\"a063e24bc973c78fd057fec97cacd72000000000000000000000000000000000\",\"Flags\":0,\"Nonce\":[1807233274,1922405120,4026009604]}],\"tx_hashes\":null}",
        "block_header": {
            "depth": 35589,
            "difficulty": "15743",
            "hash": "60e7e9f73a4a0f2c1b4a97976150ef6f53f0253f8552c6b2e7e4a010929d8259",
            "height": 420,
            "topoheight": 420,
            "major_version": 1,
            "minor_version": 1,
            "nonce": 0,
            "orphan_status": false,
            "syncblock": true,
            "sideblock": false,
            "txcount": 0,
            "reward": 0,
            "tips": [
                "6a6856b51e9ffd5b07c6c33ca635d984910f3b7fbbaaaebbb61a99780629e449"
            ],
            "timestamp": 1643337166001
        },
        "status": "OK"
    }
}

```

### Get Block Header By Topo Height

Returns the header of the requested block.

**Available parameters**

![image](/assets/rpcapistargate/rpc3.PNG)

**Body**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "DERO.GetBlockHeaderByTopoHeight",
    "params": {
        "topoheight": 420
    }
}

```

**cURL Request**

```
curl -X POST\
  http://127.0.0.1:40402/json_rpc\
  -H 'content-type: application/json'\
  -d '{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "DERO.GetBlockHeaderByTopoHeight",
    "params": {
        "topoheight": 420
    }
}'

```

**Result**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "result": {
        "block_header": {
            "depth": 35605,
            "difficulty": "15743",
            "hash": "60e7e9f73a4a0f2c1b4a97976150ef6f53f0253f8552c6b2e7e4a010929d8259",
            "height": 420,
            "topoheight": 420,
            "major_version": 1,
            "minor_version": 1,
            "nonce": 0,
            "orphan_status": false,
            "syncblock": true,
            "sideblock": false,
            "txcount": 0,
            "reward": 0,
            "tips": [
                "6a6856b51e9ffd5b07c6c33ca635d984910f3b7fbbaaaebbb61a99780629e449"
            ],
            "timestamp": 1643337166001
        },
        "status": "OK"
    }
}

```

### Get Block Header By Hash

Returns the header of the requested block.

**Available parameters**

![image](/assets/rpcapistargate/rpc4.PNG)

**Body**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "DERO.GetBlockHeaderByHash",
    "params": {
        "hash": "6a6856b51e9ffd5b07c6c33ca635d984910f3b7fbbaaaebbb61a99780629e449"
    }
}

```

**cURL Request**

```
curl -X POST\
  http://127.0.0.1:40402/json_rpc\
  -H 'content-type: application/json'\
  -d '{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "DERO.GetBlockHeaderByHash",
    "params": {
        "hash": "6a6856b51e9ffd5b07c6c33ca635d984910f3b7fbbaaaebbb61a99780629e449"
    }
}'

```

**Result**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "result": {
        "block_header": {
            "depth": 35615,
            "difficulty": "15528",
            "hash": "6a6856b51e9ffd5b07c6c33ca635d984910f3b7fbbaaaebbb61a99780629e449",
            "height": 419,
            "topoheight": 419,
            "major_version": 1,
            "minor_version": 1,
            "nonce": 0,
            "orphan_status": false,
            "syncblock": true,
            "sideblock": false,
            "txcount": 0,
            "reward": 0,
            "tips": [
                "886ffd7ca424f8c1ea3cd4f361c0e3fe865205fc669cf2c5f5bfe692e022e177"
            ],
            "timestamp": 1643337148002
        },
        "status": "OK"
    }
}

```

### Get Tx Pool

Returns the list of pending transactions (not included in a block).

**Available parameters**

No parameters

**Body**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "DERO.GetTxPool"
}

```

**cURL Request**

```
curl -X POST\
  http://127.0.0.1:40402/json_rpc\
  -H 'content-type: application/json'\
  -d '{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "DERO.GetTxPool"
}'

```

**Result**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "result": {
        "txs": [
            "1b527cc1c2c58f59d339873a9a31873507e79b5877afb2e9c9f480ba5360257e",
            "337db1b7a0da82fe7d800b2b5f7790913a8dfdcc2d331579f14b935934be53df",
            "3f7aca6ede435296902e362a73ec2f801f6f24f1cf93c69ffe607b7e5a82d8c4",
            "25ad0a277174063d786c40752ad740514a1f16266932a6650d0f267a164e077c",
            "c8d2b5a8d6cb97d2fa39e797ed795ede0caa1e5413492af2a9efd61638ff9e17",
            "38a43e4f188c7bd5c0ce52376a693e156cab71dc6cf0705f3987169969367388",
            "6f056cae1f2e692ea9e066e3d7703f14484125b2f732b7f31a48481f96299965",
            "0d6e4a43048f23fcf60ba52720ff8cebbd210ebfaab124d8a1147833b7a237fc",
            "3a8df3121e63e41a274d201f08bd7e5b1cbbab0b09c71887fcc05f1d758401bb",
            "8bd83e78bd958c5594039b703a09f72efbfe20367d28eb1e942f2c4f13be0989"
        ],
        "status": "OK"
    }
}

```

### Get Random Address

Returns a random list of different DERO addresses registered on the blockchain.

**Available parameters**

![image](/assets/rpcapistargate/rpc5.PNG)

**Body**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "DERO.GetRandomAddress"
}

```

**cURL Request**

```
curl -X POST\
  http://127.0.0.1:40402/json_rpc\
  -H 'content-type: application/json'\
  -d '{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "DERO.GetRandomAddress"
}'

```

**Result**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "result": {
        "address": [
            "deto1qyyusphxgu67m7ymvn79z0j5av4xsjf9hdf0dvwr0xgf846ae66muqgnks5sr",
            "deto1qy5tfxzc9sv0wamaacza0uup5330ds6je93wpkn6rgp38z6jjaeqgqqpf524e",
            "deto1qy92f6p3t5nytfsa3er6t8ecvxn53v7yz952xcxgnme5h8jw67ux2qqnrhstn",
            "deto1qyh8622rswt9efyzkm00shq5nq5cxaxpznham5g6ajnlw7tvmupf2qgg3f24k",
            "deto1qyv6sd4s8zrjy8lgp4x8cv4um6wj4x5hn95x85nkdzjdy99qvl062qqyqnc48",
            "deto1qy4mxumzmgxk94x8aumle2wneuns9pwfh0zu4gs4n4j9yasvdnvdvqqmyhc2r",
            "deto1qyczrgwkhzmqjhexwqjf9v7crzz6sg8jyx8g3asx2ntxhfjq6htvvqg8e2uxx",
            "deto1qy06ucenpf397vez8cdxerw3red6uw4l8afj23ezczkzx9cyqnf0sqgpekxa0",
            "deto1qyvmh00j23h2x0604ft60fujrg2hf25x25mwz7zmhkfv89ectyjqzqqcx2g77",
            "deto1qyw6f0wkfacudv707rew6ekq4azqsey3whx2tgum4tzs62srejl8zqqaqs3gr",
            [...]
        ],
        "status": "OK"
    }
}

```

### Get Transaction

Returns information related to a transaction.

**Available parameters**

![image](/assets/rpcapistargate/rpc6.PNG)

**Body**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "DERO.GetTransaction",
    "params": {
        "txs_hashes": ["6f056cae1f2e692ea9e066e3d7703f14484125b2f732b7f31a48481f96299965", "3f7aca6ede435296902e362a73ec2f801f6f24f1cf93c69ffe607b7e5a82d8c4"]
    }
}

```

**cURL Request**

```
curl -X POST\
  http://127.0.0.1:40402/json_rpc\
  -H 'content-type: application/json'\
  -d '{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "DERO.GetTransaction",
    "params": {
        "txs_hashes": ["6f056cae1f2e692ea9e066e3d7703f14484125b2f732b7f31a48481f96299965", "3f7aca6ede435296902e362a73ec2f801f6f24f1cf93c69ffe607b7e5a82d8c4"]
    }
}'

```

**Result**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "result": {
        "txs_as_hex": [
            "01000003e69902fc9485e50fdea029153c274613ad208c6799e0c862bf8cc6239419deda7286440100000000000000000000000000000000000000000000000000000000000000000000f26b7c2a5c3a9d763ecab209229726dc0a5f4b60243929873f59bf4182ee7041a03089e8cdb0040799ebc9ed5883d7d275f35d40cbd91a77529116d98cc14eff7b5782eb5156c23a39b1e0e3443ff9270db16e1b9efc946a1b54d723a502e1359bdd4c3681b91b508b11cde5f1c96061616e12a237deb71aa21553d26840125c4b1246bf87dd6afbdca9c73ac82b712e550405c303113dbeafa9bab25787d77a3bc3dc9da2d44ce40ce03c5e4952c6379798716690011fecf2c99cab204e39ac077e61b918d2f88eded45c595f64586f9d9cb7da8985a136dc192cc05668d6b9e6dec33963fb76588812348b86c3443540c2d218ddfb7a458a61408bbe3a930dfdbcebadcd6729d3e659cca0ac8c8bb608d92c879ec966cc139aa9c2a7469f302f49a97690ca011dd9f623802d9c47cb1c389296cbdfe11672cadd281358fd918e42dc82bd1c5a0007808b6f9df3722ea2cd1348c53e48b8eef5b7a07dc7ceadef267081f52e765f000f0d391589e70dfdbf10d76f664ed871c05383afc93a020ab973cdd0f9c0fa440117bea4708a833a267b87d634b6126f4f5a4be62f47f669c7eab31021e06378f4000856ba59668257dc115ad5382717b25aba1eee9b48cacff41336373f80fd56a8002a71272d83cd47ef24ace033f47a1bba1f8d22d2cdfb8757862d184f7c500e0d002324735d8b6acc63b649fd958a45a8e66c5151aee9939fdd78c917d48ed5619e0005bd24668cd20f0e9edf0955e3e1bf2a5e9ddd3eae65c7b6447984537cf1acca010cc58e9fe91a70aaf5e7499b51a18dffb1bdd5ddd3693f0789cdaabe99472499010427becbde3e356b7d6510b4c080053bce9a3ffabb968659ff5336386d7bc61600123a58d1e63341d2e4193ad1b4cfdf268828a6165a77a5c82144706c6137fc33011dfa92e61edb832f190334b89fbc4af595b0025b6bbb4f471442754197f1bbad0000a8fbddefeda6114a990e73c98fec8f2d9964bc76a4455bee110a02d938d7de0029ef38242cc8843ac6918a3425db7f288f8fc3634a23d558760a9d299a867eff0124f2105b8160426af4907faf86f0a2996fd25ccc71d6787ee95e7485fc1a23040003e4f445af3db81c59697f029960560a0e6bab0a5c067c54806f74c5676c751916a15b0ff4ccbf61e6b8f9447452f3914a305e1b64816cf24dd6e399ff4e047f011638e26605561f36d122bf63b36d3a611173d51501b8f30bf8180cbfedef1b4a0118529975d3d285220fa60ab2b7515bb67cc9d5eb383093b7f21daf9786166147000927a9f2dc6ec4e57f97f2edfa7aa4ae56c16bc706398293e7af86d1d1d063710126d2ca6b0a4b65f1713f54a50535c7835c98ba57c00d50c706ab847d6558f394000507000ea1ee57e4df8809971519c9ee0a26fb4b4c278bc4d995d8d378835c630118e7775ba54ae56eb569bd32544c804d8dc25b3d0d7c7f12fb35af7621cc2fff000a4219708f8aff0c97e9b78a09f5f38a8a3beb6c98474e8fb2d0c2b30638ea34001b6169e608eaf0896c839e00aae7b4aac2807ac2043dbc170cbf2787f08e4493012900f70bb1e03158b62c7974b453adb65ff333dcbc608c84c6f8c9c0005f34fc0023955a9fdf9c56b425090ef030494acc83bb7386654d86fedba23be66323ecf3010f8e7cedeb37731317ed7f736aca1b6374a88cf16b73ac02cce7eea17c762a7f002abd5fa748a2d0dd22fb7009e9d340634b1ef564f4b5bc91c7901479fc3e74e30015b9f3e2dfc97a3279de2f4e5bccbee8d43545514ce26868db4c8db579a6d1d20007827ae78b2c074436510d75436bd9bb66c766cafe5824c4f5accfced038e64c0021f82d411243884c79481bfd9baa856cc231e771b1b17e1fcae371f42ff42239010f1bcbc0cddac7d3b1ae3cda20e6db83b7599756517e3c8fec4f13e5f7f97187002440277fbcb9d1cb94cd59b49b6a4cbcb1a42208735561a1318b3ab78ff9d1de000dff51722f806a2d5df6196b3a521c47708857b51341001b950db12ce96e2b26010ea6cb87ccc338c38b2307caa4438623f1a14b8d0b8f187a9f80e08c68cda9150006517f26865df7a7819d7d5a1c74ef4fe15d4a54da2d6a8debd382e957c2ea51002098ba0f690059d55df8165af1a55e4798b9bb1daaa937b53c01d4a8cc4b9edb00150fd91deb00ad30e3caadd5669e0fd5d4cc4b59ea35cfc346d18050d1348f630003bc4f527a9a48f929e237fd7fc38cb917855e8fd8169f693e5a8e64113aac3e000c108da5314b747e7c4f757422977fb6237c3be338b1f5d1ba5e03e26b50c1c00002da3ed171d24913ebe897ab2ea667f024c71a5cb7ef1726f30a5cf74af2dc050017804fba37ac116e2c8500ea1a4a18e6cb0c4cd1321807dba586a7c737abe568011a72a5d6dd8d2db136897096aed41c20d7ebbe9d9c586636786a83945bac68c60007ef74facdbf94c0dbce28c5331b2b4db401c81f6bf0dbb6b2208e06b103d847010ab72c8375e59fa9da6d24e2dabd238b5ad10cc8e7243748c030554ac7add51301274b1f9397af3a0256385b00fd05fb406fdae5f4dcacf2af18c70d80072332d0012626fc2c876cb5091fc64950eb82962aa524a197dc8632cfe665a56711f07edb0127878b7e0b43601f305265aeb2870c40c1169e5b18043c7df5c33eae137550bc0017ab6786adadf6a3f63619295c5bd9c19dba3c17635c41552bc68ebbe6fc5a31002845094d3e7125879d1e858360fc0e21e91b29b96a96b7dab9da308b5fe0019d0114b1018d2f9e7c80a13c5ab647c54fa146c3166bb19fbdb5b09ed1dac8b6263d010a1b630a3ce5cd9e9a10b65c98175e8d9f9b2798f35f1f4cca7fdebbdd583e0e01000000000000000000000000000000000000000000000000000000000000000022b2ab9093612713f0b44ae740a34ef0d8f017dd2f54f892e9544b04795574c9276a8cfd17248a823c8016064e17a36804925e565c70a6b9dcee66c2a0839acd2460bd2aa01033fae4b083bfd59130c019b76f7588fb001da0f2810c2a2d4d811ed8d399e2ae59afbee965aa8c57a6cccb6fe5d1d0ed1f1e8b7ac16751dabe1227c537bc6896c90f49dfcf896adc7f4dbfe33bbec3597a5ad1df166b2b032dc4138839236ba09dd1fd6a335e4ba079aa0f74b66eafa30c1bb878386f3b1965022400be697d631b9bb807b9a49cd1031e7ee2c5ede5275ad96d37e81aa858376027489e2133df5e1951bb7a24b2e056f76aea2ffb9ebddd57da0970ac2971a017304bc7cf70d7f8322d53900540a4bf31f9ca311eb23294bf514fff9c87a1bbfc0117aa7e643fe76f43aad249e83c2feecf78fdbd3a1bf3a6036770f4d79114150b012ab7e0aab168908e0ecde7bde67e982d49fdf8de447d48ace141aabcdd91d8150b8668245d59512dd76a96e1c8f96480d2659fa2a1c701e3aaaf0d4601ee148e1f970a11ad5bcd041304bf5052b1432efc1d9416c8b5fa384f6ff749e1dc9ef911b147a25d9fa67c10da5fb3d7bf2fda1ba9a8ba0323771c57efc4211149694b13eac2bd2497ccf624b7c998ba09f797d27a4dc837443c7285b60373aed85c160246409e05eef1b532f1f6936fb546e8cfd9be1c8018655515e5e86bf0980a8b07f20eaaf6ae90526d2472138d176cca1b4a58667ee88b19d6e906b1a0eafdc70153743b0d3bc8ae4405e0f43a430d718574b6cb80ed34bf55417af8c58ffcf2266d86a26dfec8e282f85590898bcae2ff7e3fe32937eb0257fde6d1b38276ae1e8e94d31bd4a2c164053e3a65551a5582d14c26d790cbf5bbc0806241d9b51e002a3e47d15d2e70a0201fa2eb82462a51c16096f7052800da8a9da3220e45054d002f42f205ed9a09ddcb83ed212950f43f9389ee416127b52cb5006a470f5c29f70003ff4bddc6d753e6b087c5d0793148c8476f00be31b1fa64be5bec2b62d2781d011b4738d12826104a3b231f8975ea13f780cb8839d8d0cec7118a8952cce6fab3010025613eccb92dbf0ac99afcd8a626089c543eb0493dde59881c6461cb48d2e900000443901ac6c1254bfb7e61a8f74e095d82c68f099649674f2fd08a63d15f0e001393ecba1ab93b4f29f2e6e482b9b03c279c461f7b81840e26a5a4c1fcabc232002cc839ecaa1a488384811b5dc53008762aaa77630d605ede4f94eaeedbda3062012b05119a9c3961b533f6b1dad8cfb95afa45eda90de84b8ec8c4b4cf95181ca100238b29c579fe319d3e24a9a08433f88fa822a32fcd06c73d8d64a1afc840991c000450d30a9882faeb3c437796cce575a1d463b4a96d196d42eaaab8045afb1fba011be8e17cf5c22173437c96b574be0679c71452c17c7852db8dd75bb5d59a63630005dd000a330ac1068f56b4bf608cae8594c2ecc5b5faa2521218445f713c963700",
            "01000003e69902fc9485e50fdea029153c274613ad208c6799e0c862bf8cc6239419deda7286440100000000000000000000000000000000000000000000000000000000000000000000f7b00b62bb6ffeaf98ed7f252ea95b76b725fe050de30da128837ce772784dc69314c0a5701e123c83bac704c5fec14b6797e3a3cdcda16b9ed97240b4fe144d217a6243620dbd4a2eac6658efee534f82ebb6b94ee8d57311e5e2b6dc711cb75dbf5f11a82683b2291cff7643179e5b85cb5a5959d3588dfc26d199655f2da8cdad81257750e92bc9009213691481cefe0405c30309467aac2a2afcfb09bf242fac7921f1e82cdb4fada78dfe413d0d75514b1ef401ffb247cded31b2c6aa0ad40e324680c3443540c2149e1766f3a8472dca148bea450a6ba676c12aad51f03ae94fc1cd50e53ce915f54ececcbe67ebc8d8f8ca66ca06c1b3f4c07b218884620bc137492a0cbbce17be2d81c304839c0c53e1dcaa5d3debd0ca8c791c9ea1007bb8c884f70026d8a86d32cb79cec58f531754d31b85ec2b7149601ec918941ddb72d33d8333011d3a935cca64839795bd6016b876843295468de4764bb47147e7eb89ba8f405701014e68061e4573d9b491a8180dfc4411b2b4f5c7384770cb6915a09afb0ffa1e001d1c4a4c60a65c3ed5a4fb15bcd65fd7cfa045ac7db6b575f0f2efe1b3a80be90021d71e008c3bccc73b9f163df173a38d32a1567a6876894030b107a1ad9af0ce000b30b9c2106dc0ef5a1a2a1af46e5b1f68614145cd20367c732cd7281f678053010879409ed3cc903a1faf56e9299c6a2a19030ccb559497def01513e72781a8e90122128ab5550b5639812e1076e2cbae330c027b0b284c794aeada50cee433bc200106e23650a4fcfba8f60be26ae22bc863ca68aaad28feaaeeacfec29314a3664b000193659b96a95f31ec5127885fbc3585ad41cf282c01b519c1c0dcaf1628ec1e0026017814db424c1f594420a1c096ac01c48c3a654ff1541c7c8307203fdf6cee000113e0db3f56326973d51cdf3360e9cdae7972e39c0a7f3325c965e48504c5f00018aeb558aaa3ff41f3358faaebe05b52ed1ff233ec973e8bc621e9daf93edafd0107b116db3401423f4975bb5b9d39a3c06bad79f88df43bc3cc9d701ba2709d25000df70aad6d6bdaea8a3bae6e4dfc829e9356ec79de4a614006504e5365de7a810003e4f445af3db81c59697f029960560a0e6bab0a5c067c54806f74c5676c75192d5e86ed77f82ec40247a6058541888613ff9cedba5b0a2fdc87fc4e11c3dbed001c40b4ee98619123eb930c2684ccb3fa5146148a4da5b1d0898691e6367485ff012b08b0ec699421f84b06445e2a067729bfe64d6f072f3890a7277e3a1f5b792a000837564104fefa546b2e2330134a2a0d873e8fc33254fa54101d125816e2094a012d32ed55941b68d79fbe72de192d908924434c78231804b4d6fb01eecfb7edb1000e19c1613a2d2294549466c850d8729aafbe6c31f2c587450c3e01abe49ecb60002a15f0e4b815276858ff375183f44544dedb68e4ddd1d608c5d338c754807d6c0015a783fb7af458137e1100b2a34cda438c01fa2505c745af8e7845d14ab3efb3000befe5ff87e60c230a0d2e062c678904994ce5d998f720e8e821c458239100b30028a11eaee1e9b54026979d3723994624ed974b12063c7481c20df64160c0372701222c9d06da850263e367493c88bdbfb7f58e612492e19f54a6256d1501d8d987001e3aa30bb94c815072d0bf55563d40631bcc11d0832c8ca6278f96caf97a4249000adb571a55bcdef4a4aefb03304624b6158345e91385d14e0c2af7815c8cf5f7010c6fd971a2c9156e95a1a611a8801e0f7ac630f5403a8d79e74839ad5837cb6f001393112847debc1e51379e9cef1f7170d1e5a37844dfac85cf3c21ddaf431902002967be2102e25853016bd44868c0b573e6cb734659c15bc902089a9b710be6a0000abf40ad280302c64d027488c64fb045565d01fd2b79806e061b02fdd48c258b010067270b6d3bdffcc327606cbcaae0824a5311791a63c52ba5c36687f9d48b8801160bac150b6f73abcba7ca95297d9171699526e163dc800e2c51bd8d0a8a599f002e1504db4acba7cd8e36fb5abd2f2711240f02e382cd86b86fd9c25c14ee2c82012bb3ad75755bfb1257681ea4e8922cb77be35e95c4decd63b806fdfa3cd0902001115ecbcf1893b678df2ac70e600d031edaea8f22d7355965ccb5b02d844599ee001c4346a94088c351b48a4edfa4f2a42e4639d5ca77eadb113e6d4e11d5b84a83000359411a2c0cf7de244b4da2e4daf39d4ea9e4c1d0ba33bf755722d37d59efaf000833020cc0992588cf23ba7021c27d6eecd38917bd9f79fd3be3b29271bc73a6001175b41061df0baf57c82cdfe7222bf2322946a938e3320c8244e4ca5c21c612011ce87c2842bd8d1f5c2b7790e05395036350d89ce1b8d522e036e3be7c5855a2012be1a30de449f9a431025d38023a3596db63f9ea6a9bbdbdaa057a8b03079dd501005334ebf3ceb5028561c401dc971d6dcd10803bd7ad7c2c61516f6e8c6d13880015be77d1d0b878ac03cd2e766aa3a2517a157ce29c69b3f73dd55f600849390a0121d54ddeda9cd0938812a7e71aa9b195d19427ca635865cc0bd34e3fb0215f67011b6585ee33f5082b1164a6f8ca27448b616c614d32d9feb7eb06ed341049a52f0022941d16396895ec0c7fd4268497986cc466ef4eedec5453a29fec6bbaf171250023a361d8a6f836e5bc3fc9e2e56194a67fc6ed735707ae09587b2e35d495411a01084c39a1c2444da2f7459c107f403c2ad4770aab683f0b3b64e8c469230ef828011992cbb72047cbc8dd240700152e7051ebdff5f3b74d083384afdb04af215765010caa33c30a9542fd0c8f7d8dee6ec8ff0f899dbef5f5dd994f2e27c18ba53ee3000000000000000000000000000000000000000000000000000000000000000000103ffd6f8a27ed37431f145f4ea498063816b4948ff098f3ddc67b5b2653707d138c6bf2ea9a4718b0a50510b0124b75d24da9a9a07de08847416ab67ab75be3015115995367f4e81f3adb383e3cd7146f770fd3a63bdd9130621b84d17b208c018c80857b89283879764ab8f1ae16b2448621776513c0df487db9e336706a7e1c19a0c127ebf7762f5ee4f334aaa287c2a1af74471d88a22c45cf3348fa16952c30b32fc87990c5b6b9bb2795c85770dc07e541cf94aa7f357442f3ca08c8bb2aba3ed10ef9a8ef1cd20996853384190c4dc79095a91517be60c0d955c2f85e1b22da5326c2b88059b312f7b91b58f52cbf6d84df34834f7d044c7be6a13f041f690b83a6fac06dc6f0cbd7f2c4171aa426951382efbceec9853cdfb566005e00220e6871c0abb720c5b5466d9ab532d6b73797c82e6b570ce0b2d6d151dc154f012ce3e99fe03ea2787f781ba07b27ab73ab84c483762382ff1b69a54def410ad71536278c84543bbd1b5df2441d2078033ff200274d214e1fe602da99c44ca4d80ce6d41d3bb685763c787b4eadd06637eb33a4ab5f8ebcaefa2d23badfd6711a15f024315d03dfb65c01e2ded515109aaa19c56a788d6b81e52311c2113a42af293e1537d5a919ad8f3536602897f553ae8ca2342509815d8091d3099ef67b0014b6e179f0184e79dae1fb5f93e6d16b7ba99603aacd72dee1435b2d0a63dac10eaa5f6e82463a303708008c6d5ce83e1be8a88b0f4e0dc3c274ef1f35dda00b195e0fb94356ff1e390874fb7884866ee511315d348e3dd31b1b1741230ced7e2e3fb65a21ef0577ad6290bd41c94f539d7e613ed3868c80471ae5507876f06a2bd977607ffe9b66c929d8c978b2ab050d911389f35cd23962bbdcb07575ea4b0011932f82346cf49ee903c24acbec4373c6a6e24aed1d2ba6708656eb81affa12002817723dc1ce5f67c680e1742e0290620a4e689e309e664b44ed7fdd3d15d5460102f1cfc9cbb7d9fdb1b1e21480ed229b030fd9293bbd648753903fecfafda2a60128a29cf179688988929e8304ecdfdf1f7d5098cd88ce4b66ca2927cdbf9ebc3c002c861382f359b88d72b281adb8229539c6e7f622f75da274fa1a1ee3cecb1abf0022c07f8f152c80cbd6680533693fe0e76acab8ce4670696573f93f714aa369dc013041371db94160e159d725769ddf0d328745fb2af0a736fd2e8969876dd19662011c8c36dfa032c52f0c3442b7d9695b50d51dcd975d6374e6df1224e276462f6c001dddcfd90e2fbc717135f29af6387daaef87fa791249890d338d644e4532669f000bded5a6a000e08e4797154f5d9137f0e7fde06b0c84217d6c3e06f07eecf2990017f99e2e47bcc0ca0dd2ab1e170e0f828c30408869d9dc46ae75459918fceba700108598f111b389d27e110051a763382cc5ea3f396ae21b6970063a3cac17794b0126030ff863e81e5bbd10f3d434b0490d0a792f1ca50dcf419efdb6b366e364bf01"
        ],
        "txs": [
            {
                "as_hex": "",
                "block_height": 36074,
                "reward": 0,
                "ignored": false,
                "in_pool": false,
                "output_indices": null,
                "tx_hash": "",
                "valid_block": "e286bd3cedfbfaecbbc327f4cb5b1f5457053f322acdd177d6ff55cb6e897e7f",
                "invalid_block": null,
                "ring": [
                    [
                        "deto1qy2cl36z7rwqsrp9mqf3jf0lj6hxrvmt98dp6uq2zeathn00rv4rqqgwwwq6y",
                        "deto1qy2u9j4c3tv3exmmdd5za82f2gg6dqmaptmxat640ssvwca3zmxajqg67z4sv",
                        "deto1qyxwhayh9hc230g7dqtl76yhpj754dd7uh4kgptd4ya29538u4v8wqgvrfdt4",
                        "deto1qy56vq7gfrhv2jrgjpcrsd65vsgpf7qpz6c0h03wy5ke9fumewkyuqgxshj8c",
                        "deto1qysxfqq9aweksl80wnnxf9n4eqwzxgt9d2uezp2h7rqz5kf2cj5gyqg3pg7eh",
                        "deto1qykz0y7k86fpgymege4uy2zzxmehhzqun9u6azs46ze9adwamupk5qg4j9lvt",
                        "deto1qyywdf79xhw9kmljtef786rx8j6q7tg3uakvgjgvsz7dw5kuxfexjqgm6e2yj",
                        "deto1qyz8umf02tjzkxy2d7alhq2h7xsf6zsuapvy5m4kn67pqrpgc2er6qg6x6d0n",
                        "deto1qyynts8afn6fyxslpn7r420c5hehudwyncjgm6r2yfm5t3s370cuwqgn4j6x2",
                        "deto1qy04yamzkg64ndsc9u3knuknszed6hmxxtmrx6x387dq4r2hr7tezqq9md6rq",
                        "deto1qyyemtmskcpjn3fhguvn0yuquvkasjh5fxwqgk9zk5mn4x0fp7t06qgr7fkdr",
                        "deto1qy0ehnqjpr0wxqnknyc66du2fsxyktppkr8m8e6jvplp954klfjz2qqdzcd8p",
                        "deto1qy9gs9c683903sgc3cna60fwzuka6r4qgdennpreev60z6rsdw0zkqgy47zwm",
                        "deto1qy8z4awcnhnp624ma0fznkpj433wnl75hu47fx73287mk5vy2ga3wqgj9gtla",
                        "deto1qy0cx6faws9ypd7aw3500x93v8t8dgdwfsqmy8sqtsaa844ldgn2wqq0e70le",
                        "deto1qykhpc3ksq7c39sdvguuv02s62q0elcugr4fwnywhg8cnkkch29ryqqyvtq8g"
                    ]
                ],
                "signer": "",
                "balance": 0,
                "code": "",
                "balancenow": 0,
                "codenow": ""
            },
            {
                "as_hex": "",
                "block_height": 36074,
                "reward": 0,
                "ignored": false,
                "in_pool": false,
                "output_indices": null,
                "tx_hash": "",
                "valid_block": "e286bd3cedfbfaecbbc327f4cb5b1f5457053f322acdd177d6ff55cb6e897e7f",
                "invalid_block": null,
                "ring": [
                    [
                        "deto1qyxjcz77he9njxkm2rvd469hlv88yhp3mwwmem5d46jj3lpr6w03wqq8e27rg",
                        "deto1qyhvwyjkgmsg40hkau4csh0ksn4qm072uz0jr75gf45lqmdpxah2kqqrp8s4r",
                        "deto1qyptptr294w6aa38220um5as08krppx6de0qjk7mu5rdfelfn97h5qg6lfd0v",
                        "deto1qy0ehnqjpr0wxqnknyc66du2fsxyktppkr8m8e6jvplp954klfjz2qqdzcd8p",
                        "deto1qyt26zg5csas4h3a88dtqxgny6rlyfdr27jx335x94syjxn652f25qggmlag4",
                        "deto1qyye8v2zfdmpn9vsd98yflmghwgk90tpcrkfpeds645rvfsxvx5jzqq6ezejl",
                        "deto1qyr4pxj7qlxc62j3u7dxdpjgl7vjgmkcf5rwack9dm97etc8fjvx2qq83pmye",
                        "deto1qyr0rgqkh0r679ezp6znwgdyxkzlvq50jazuj3r5yslwkt7rssc4jqq78qwmq",
                        "deto1qy00rwqzshtn98nz6h42k39230k0v5gzkvp7ms83w49zn09s2tes5qguwuhpp",
                        "deto1qyww4r64c4t02qzs8w3cpfw28kfjnrrnth9flk4jped64ynslq8uvqge6hnd4",
                        "deto1qyyj99tnmng4mrk6r9n8kx8zyympm9ljkd07jujhhjudrw3e2nwrkqqc9k29f",
                        "deto1qyy86yhmx8mr3343dnlk9kc9gec3qek028t4xfdhxhk0ymhy88qzuqgyw9tgn",
                        "deto1qy4qyujjy02ayrxs8pgq0rk00n845sqk6dha8jdgp5358v86aqcngqqhld7yr",
                        "deto1qy598uhhf9kgdqlyz4aag7gzrjfeged48m8z9mccrf8yn0ufm8auzqggcyydd",
                        "deto1qyddyeqfnzg2lwgseuefhpl4564rp2d6p5zf9ud0uj7sepmsxnyhgqq7xdkxz",
                        "deto1qyjlw2w4kkfrs6yt4v62tv2zntlvjth435fsuzqafw2yvxt4ae7y6qggjcl4f"
                    ]
                ],
                "signer": "",
                "balance": 0,
                "code": "",
                "balancenow": 0,
                "codenow": ""
            }
        ],
        "status": "OK"
    }
}

```

### Send Raw Transaction

Broadcast a transaction on the DERO network.

**Available parameters**

![image](/assets/rpcapistargate/rpc7.PNG)

**Body**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "DERO.SendRawTransaction",
    "params": {
        "tx_as_hex": "01000003d39a02c1295e6cbaf9f98ed67ba0e6a06eb26b3c5d27fa83e0bd070a058c539d21da5d01000000000000000000000000000000000000000000000000000000000000000000000160678916fcfcb943bf579de316406d1dae91b0799701c38aba61129daa92c662074e559ea4165e259e261aaf4e80262398dfc3b0561a63f5c3da356cadfcb9932efb8e0db977e23c82c4f1c0b6014bf1bbb71b91d9d584bb7de5bddaa80a2a8dd9bf12bfd06ef252fab44884c683e0dc92262ead552b1c6dbc513fedaa59929fd5eb21c80d4a8bf44b346d9cd0a667e40404c3031b970faa7e70d5050842ad3c88679852a8f27b6a5afbec1fb8ad000bd189802200dc9e48d5452ec98e05beb43b51056a57c719ab7ec3443540807a908374c64207008c095ed633722a97c95073398e48de0076fec58f96fe3cd2ecb8d385086fb91e8c9c5028d6b6b5a48a432b8f7ac6c43e31eff39396a2074d8af19b7ab4154f01008c0798cf91f0892c4d8246743386fbf617f72a985634e0059a12eaec24a61001016b05ed80daf1e9580f2ccc66081c3765201f9e6ac230a2b7667a0bba427dc6002d7a9f01ff25296b171e036c9c68053d7de826b180323224417126de0fd0748501238b3a1dc5dbe62de9f0488264ee46c39c08925e2cb68f7b6dc60d8aecbb68620002c66dd5c29de5e9adab3bd7f268f64269e1e96921eeb9637505414c790c0a65011e4020fdc76b7a4a6fad84d0fe875cbd38fa7e816585b639d8c3032aca1b3064010e380630678bcc957c4a1cc8e57d2df9fe7996b98dabd42cf1c49eaa8625e1b80119eb616138a8c3606a3bc1f9a0052eaedf6f50ac4158ad2c42074ff02c3ef786001394a47cf5cfc88b357eb50c88d8f1554f9cd5f1fc00cfd54c35d3664e9c27ce00010990641ed8bea313d3201aa9a1b7dbde6e18376e07df73cdea1b5d1c11309c0122e645671fb85d7e8dc79729cb147a4fb534d17981d4d5d576f965492f3745f0001aecdcae49756e90d99500c31514f8e0421cc7678499dd7d6b8ea393cf3b29ef0116b78b380109adbe63d8597aac8a7d2d92ff655c93432ff70a2eacb5e5d75ae4011227aa289afebbbb5ed5d55cc988f39a818f46b75a6b804ebbe47ff021d0c032002442d20d3b09f99317d36dff5b4dd26b4832c0bd158814f9329506a257c235e800d516c08b48be26167e83850a13e0b3b07a1ff9c92aea0403ed60da213726b9371c815b9607b3f2ac78b8f4aacfbeadf7f7a800751ac231447b17606200b6eb0f01191641ed48d79ce5a064fdacfe40061de65b8c0d7aea1fae353b1effc7f2a2ac00270e2ac0dc68e423d1868f5cac869d64d94702ee9e772ef5fd52b4612ead6f5a0003a1c3d496a186a1a72cfe3078e88168ff326473b8af785b254aa124c69064e400163d332d26ea2e7f66022bd963c4163a6f205d44e35ac83eea7d5a0f1236f09c0023f155555baa1083840831c538443e2805966ab97c8ec333435ac7ab58a979fe002f4b9c816d0c5dfc46b6b507028dd967ba0574f6f3f3503c8cfefca4bd88be7300007ccba7bd0cf11585241ba0e573ab5fbcc159220bfb4669de2cd3d11b9ac8a60020369d2d52fd9c8997c6bd384c3627b03da0cc0c2d2f5aa4b0c74a330192f4c2012278d29396e1c6bfaeb67626da24ec117429f4d207ddd2b0632cb09d12652ec10101e3a4ff8846e1655b007195e1b6d800b4c62a88173d4328002d39f673809954001031c5badf10560137006f3e24fa54b27298109f45802311f72682f8416daf870017f293c47a044b8950bb2432f13aabce8d2778e06acbc77b7ff5c0f9fcf19a0d01192e4f040dade991bfccb215e86d43f6d1dcfdba6b990901fc0803205971a8630100c8de7797ac2233659edad98015d4b09fd72795c88b7e72abe67332b6dfe419011b4b31bb8f4839e93470fdf6466cfeebb71e8268fc4eee7e1fc18c693db1b0ee010635360ad6bc1ac35171de94f599ff94b5b99bb8cbcb752c0d8bf814dcb17bf3011d0e8b621bb2d2ccf391b98afe47b113c135357f5704729a7424eb7d43d692ce0028c2ed7d17398ec2c7430b48d95e5b4641ba9aa09d938aee68a156aa708db4b7012db0d18235dbf4800a23edda7f53a433cb6a7df84a0b5cc4c1e810c4f0a2bd8201034aad9debd087e6b816ac31e8233d08ba685bde235a5f794f908405398c12ee0016d5d080eb4042680548d29f8730198051a9dccd0996d40c5a13b6949f14e4910025f28597f07d17439457e9e41a5c7f7daabbc134f6228be485f452461d5b996701220584b24e5a87af99109c460b2052df26f15e631ef8c36f18004ffd7a71a519002ae7670e81dc479985dd0caa0cb08f2128307b43aea07a6d3c5ab84aa648a5a70004ef828ddc623cb574e87065a5d7c3006597716c910190a866969dfea37c30d600249fb654c861c3688c2898fed0aac1fac075b6478146e3fb99d34ccaf790a21d0012a06b85562f201047ed922fe938e72069e4a25f0cc5782b1aec718c0bce46ea002e0dae8b0fe9e50fbe0ba74c6e0565212fddefef7053529cad2747978265f8a8011c140a7bc045eb496e520b4bd08e9dbdf18b9a1bbf6733be4248442d10a9fb0500302c870c17f7ef67e711df82b6603b30603694e188024fa41a14fada846d8ba9012db86e12e976195f38cba6915f7228c2e98fe0a266df942e7174e3f528ddb1d00102222e91f9a9e91904b17d64977352c93e5ac2f6e1d694041f7863ead356f5ee011f4e1eeef0606a9ae6d87562ed0f81dc0402d327102471c4b9dbb3fa3651ba09010e42adcbf49d9050d82ecaa5c40a9c9858aa0f97976cc593de7141d9aacc0a6c00200be9027f39b0dadb36df2114f3a7605a90347e3625304e290d83841365fa2a0011da530bc17fb6e3c5fcd5291fb286c9b52b943a1c93f68b7ac220ff9b008f170000000000000000000000000000000000000000000000000000000000000000000eab3f99967f03bb3a3b1e689145e406155d4c9e027a1206a1cc972f1003be5612eea86bea3b0ee07dafbc2610fe9c71bdeccead3ba0a2702f5da0d89d084f2c053f0931828d42aec32cd555d5d81639005192e5903da3c23218938c7c3dc918227a34fb4889a56ea461988da95aeca6e17dbf5865696fbe738bd7033f51f0b40346b290197557ac24db3e9281f0fedf01110dfeb4daf4d71163de652dc8b2b61778b5e0bd4f45541b35c62923b99b53c3b94f1478dd81708e14112e152e489e2c1c4c580d3e35a9f0693449a0af566deb3f32340373c023ffa6c9ff8d91f80d07af281574a4822870a05678b41d97c4a9b35541e6940f0120b9d47fc4bb2b2003e95bd2ec3c63245602f21808a875ba0d1028ca3e7869b6c6682a7125c1f2ff011ece8eb96ff3e0e9af0947749056b806e554fde39f475f0ca2211cf9198058a4002703f5443f1886e1caf60f775b6431bc948e4b0e2b76f56a8fc8c29da23caded041917938e845f826ddc5f2ec6aca0a985e6f6c98ea0cbc51f9429e2616500e20605af191eac7bd2696409d65dcbf3108079ec1f6bd5f9601b43dd3b58304d9d205b1ef7b34578d80236c0615ac79f69fcc7c92491bbbd3130cc22e8f0ea1fd21d2d5bfc8da06e2ba48acf70477d1cfefa7165a0804166027f0945faa85057cc236797a65ada0329e7de91712b4974fd83bb99ea97042788bfde4b8b9b5f1b251f6853fc4ffbdff382b24f209d4357099ea1c0d0c383dfd7f03d64bb7bff199406aae7f59190862d36ebefe8d011825bc663c6731f6397d5019f00055a3f80b71ab3b3813d5d509d89432a722ee789db88ca86c86fa76d6224b7eb3c5e66822b1e57f77674481d0a3a7252d47c4da5feab251db1b0b146620a9d271ca951c33f001080c18c31919d2de622fe0170824cc31ecaedd90d8214afcf47a7486474d65200153ade04144d5c29e2e0d6003fcf160bec90d79a42afcb4fe230bc695ce956ba001f4b437e4531531b85e326ccdf160e87408454ecd811fd41a51cc7a9585700df01092a076eebb6fb76ae2443dd7f007fe8edc4c7f54a1bdf48e8e5ae59ca513a9901205d75965eb434dd10e8425ff82d7f6695d4cf0b97507e800c3e3d59a60b83f3002d1496857827c872a53a792e86a74da252f12316972cfadbb2afcfa40a2883790108ccf31a2fdd88201361a0d4313a98a0272173132d1fa3d9bf018f35a7b439b701301da927ac71fea5a0024920ecbadd76f5f05f06b2d8e6874ae9a5348316585b002806c45af761489705e347dcc764ab531fbd7205c36c15f44ad1b633a609dda3000a40291cb5b71269ce0535a8b81ee3440e3db8208e4dd2af38c6591121c6a6560127f8dbc559ca73ecc28c0df0f38b7991bd348121cf5c111c4c505b019d5ef8de0018aae0f6ef38795ec5bac7e55ac5e580599a95043bc57ecc4930d2e1279269b2001c77bc717a5a1788e6157bf937e3f089ec9e27b0a7ab4eab11c25eec1918045300"
    }
}

```

**cURL Request**

```
curl -X POST\
  http://127.0.0.1:40402/json_rpc\
  -H 'content-type: application/json'\
  -d '{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "DERO.SendRawTransaction",
    "params": {
        "tx_as_hex": "01000003d39a02c1295e6cbaf9f98ed67ba0e6a06eb26b3c5d27fa83e0bd070a058c539d21da5d01000000000000000000000000000000000000000000000000000000000000000000000160678916fcfcb943bf579de316406d1dae91b0799701c38aba61129daa92c662074e559ea4165e259e261aaf4e80262398dfc3b0561a63f5c3da356cadfcb9932efb8e0db977e23c82c4f1c0b6014bf1bbb71b91d9d584bb7de5bddaa80a2a8dd9bf12bfd06ef252fab44884c683e0dc92262ead552b1c6dbc513fedaa59929fd5eb21c80d4a8bf44b346d9cd0a667e40404c3031b970faa7e70d5050842ad3c88679852a8f27b6a5afbec1fb8ad000bd189802200dc9e48d5452ec98e05beb43b51056a57c719ab7ec3443540807a908374c64207008c095ed633722a97c95073398e48de0076fec58f96fe3cd2ecb8d385086fb91e8c9c5028d6b6b5a48a432b8f7ac6c43e31eff39396a2074d8af19b7ab4154f01008c0798cf91f0892c4d8246743386fbf617f72a985634e0059a12eaec24a61001016b05ed80daf1e9580f2ccc66081c3765201f9e6ac230a2b7667a0bba427dc6002d7a9f01ff25296b171e036c9c68053d7de826b180323224417126de0fd0748501238b3a1dc5dbe62de9f0488264ee46c39c08925e2cb68f7b6dc60d8aecbb68620002c66dd5c29de5e9adab3bd7f268f64269e1e96921eeb9637505414c790c0a65011e4020fdc76b7a4a6fad84d0fe875cbd38fa7e816585b639d8c3032aca1b3064010e380630678bcc957c4a1cc8e57d2df9fe7996b98dabd42cf1c49eaa8625e1b80119eb616138a8c3606a3bc1f9a0052eaedf6f50ac4158ad2c42074ff02c3ef786001394a47cf5cfc88b357eb50c88d8f1554f9cd5f1fc00cfd54c35d3664e9c27ce00010990641ed8bea313d3201aa9a1b7dbde6e18376e07df73cdea1b5d1c11309c0122e645671fb85d7e8dc79729cb147a4fb534d17981d4d5d576f965492f3745f0001aecdcae49756e90d99500c31514f8e0421cc7678499dd7d6b8ea393cf3b29ef0116b78b380109adbe63d8597aac8a7d2d92ff655c93432ff70a2eacb5e5d75ae4011227aa289afebbbb5ed5d55cc988f39a818f46b75a6b804ebbe47ff021d0c032002442d20d3b09f99317d36dff5b4dd26b4832c0bd158814f9329506a257c235e800d516c08b48be26167e83850a13e0b3b07a1ff9c92aea0403ed60da213726b9371c815b9607b3f2ac78b8f4aacfbeadf7f7a800751ac231447b17606200b6eb0f01191641ed48d79ce5a064fdacfe40061de65b8c0d7aea1fae353b1effc7f2a2ac00270e2ac0dc68e423d1868f5cac869d64d94702ee9e772ef5fd52b4612ead6f5a0003a1c3d496a186a1a72cfe3078e88168ff326473b8af785b254aa124c69064e400163d332d26ea2e7f66022bd963c4163a6f205d44e35ac83eea7d5a0f1236f09c0023f155555baa1083840831c538443e2805966ab97c8ec333435ac7ab58a979fe002f4b9c816d0c5dfc46b6b507028dd967ba0574f6f3f3503c8cfefca4bd88be7300007ccba7bd0cf11585241ba0e573ab5fbcc159220bfb4669de2cd3d11b9ac8a60020369d2d52fd9c8997c6bd384c3627b03da0cc0c2d2f5aa4b0c74a330192f4c2012278d29396e1c6bfaeb67626da24ec117429f4d207ddd2b0632cb09d12652ec10101e3a4ff8846e1655b007195e1b6d800b4c62a88173d4328002d39f673809954001031c5badf10560137006f3e24fa54b27298109f45802311f72682f8416daf870017f293c47a044b8950bb2432f13aabce8d2778e06acbc77b7ff5c0f9fcf19a0d01192e4f040dade991bfccb215e86d43f6d1dcfdba6b990901fc0803205971a8630100c8de7797ac2233659edad98015d4b09fd72795c88b7e72abe67332b6dfe419011b4b31bb8f4839e93470fdf6466cfeebb71e8268fc4eee7e1fc18c693db1b0ee010635360ad6bc1ac35171de94f599ff94b5b99bb8cbcb752c0d8bf814dcb17bf3011d0e8b621bb2d2ccf391b98afe47b113c135357f5704729a7424eb7d43d692ce0028c2ed7d17398ec2c7430b48d95e5b4641ba9aa09d938aee68a156aa708db4b7012db0d18235dbf4800a23edda7f53a433cb6a7df84a0b5cc4c1e810c4f0a2bd8201034aad9debd087e6b816ac31e8233d08ba685bde235a5f794f908405398c12ee0016d5d080eb4042680548d29f8730198051a9dccd0996d40c5a13b6949f14e4910025f28597f07d17439457e9e41a5c7f7daabbc134f6228be485f452461d5b996701220584b24e5a87af99109c460b2052df26f15e631ef8c36f18004ffd7a71a519002ae7670e81dc479985dd0caa0cb08f2128307b43aea07a6d3c5ab84aa648a5a70004ef828ddc623cb574e87065a5d7c3006597716c910190a866969dfea37c30d600249fb654c861c3688c2898fed0aac1fac075b6478146e3fb99d34ccaf790a21d0012a06b85562f201047ed922fe938e72069e4a25f0cc5782b1aec718c0bce46ea002e0dae8b0fe9e50fbe0ba74c6e0565212fddefef7053529cad2747978265f8a8011c140a7bc045eb496e520b4bd08e9dbdf18b9a1bbf6733be4248442d10a9fb0500302c870c17f7ef67e711df82b6603b30603694e188024fa41a14fada846d8ba9012db86e12e976195f38cba6915f7228c2e98fe0a266df942e7174e3f528ddb1d00102222e91f9a9e91904b17d64977352c93e5ac2f6e1d694041f7863ead356f5ee011f4e1eeef0606a9ae6d87562ed0f81dc0402d327102471c4b9dbb3fa3651ba09010e42adcbf49d9050d82ecaa5c40a9c9858aa0f97976cc593de7141d9aacc0a6c00200be9027f39b0dadb36df2114f3a7605a90347e3625304e290d83841365fa2a0011da530bc17fb6e3c5fcd5291fb286c9b52b943a1c93f68b7ac220ff9b008f170000000000000000000000000000000000000000000000000000000000000000000eab3f99967f03bb3a3b1e689145e406155d4c9e027a1206a1cc972f1003be5612eea86bea3b0ee07dafbc2610fe9c71bdeccead3ba0a2702f5da0d89d084f2c053f0931828d42aec32cd555d5d81639005192e5903da3c23218938c7c3dc918227a34fb4889a56ea461988da95aeca6e17dbf5865696fbe738bd7033f51f0b40346b290197557ac24db3e9281f0fedf01110dfeb4daf4d71163de652dc8b2b61778b5e0bd4f45541b35c62923b99b53c3b94f1478dd81708e14112e152e489e2c1c4c580d3e35a9f0693449a0af566deb3f32340373c023ffa6c9ff8d91f80d07af281574a4822870a05678b41d97c4a9b35541e6940f0120b9d47fc4bb2b2003e95bd2ec3c63245602f21808a875ba0d1028ca3e7869b6c6682a7125c1f2ff011ece8eb96ff3e0e9af0947749056b806e554fde39f475f0ca2211cf9198058a4002703f5443f1886e1caf60f775b6431bc948e4b0e2b76f56a8fc8c29da23caded041917938e845f826ddc5f2ec6aca0a985e6f6c98ea0cbc51f9429e2616500e20605af191eac7bd2696409d65dcbf3108079ec1f6bd5f9601b43dd3b58304d9d205b1ef7b34578d80236c0615ac79f69fcc7c92491bbbd3130cc22e8f0ea1fd21d2d5bfc8da06e2ba48acf70477d1cfefa7165a0804166027f0945faa85057cc236797a65ada0329e7de91712b4974fd83bb99ea97042788bfde4b8b9b5f1b251f6853fc4ffbdff382b24f209d4357099ea1c0d0c383dfd7f03d64bb7bff199406aae7f59190862d36ebefe8d011825bc663c6731f6397d5019f00055a3f80b71ab3b3813d5d509d89432a722ee789db88ca86c86fa76d6224b7eb3c5e66822b1e57f77674481d0a3a7252d47c4da5feab251db1b0b146620a9d271ca951c33f001080c18c31919d2de622fe0170824cc31ecaedd90d8214afcf47a7486474d65200153ade04144d5c29e2e0d6003fcf160bec90d79a42afcb4fe230bc695ce956ba001f4b437e4531531b85e326ccdf160e87408454ecd811fd41a51cc7a9585700df01092a076eebb6fb76ae2443dd7f007fe8edc4c7f54a1bdf48e8e5ae59ca513a9901205d75965eb434dd10e8425ff82d7f6695d4cf0b97507e800c3e3d59a60b83f3002d1496857827c872a53a792e86a74da252f12316972cfadbb2afcfa40a2883790108ccf31a2fdd88201361a0d4313a98a0272173132d1fa3d9bf018f35a7b439b701301da927ac71fea5a0024920ecbadd76f5f05f06b2d8e6874ae9a5348316585b002806c45af761489705e347dcc764ab531fbd7205c36c15f44ad1b633a609dda3000a40291cb5b71269ce0535a8b81ee3440e3db8208e4dd2af38c6591121c6a6560127f8dbc559ca73ecc28c0df0f38b7991bd348121cf5c111c4c505b019d5ef8de0018aae0f6ef38795ec5bac7e55ac5e580599a95043bc57ecc4930d2e1279269b2001c77bc717a5a1788e6157bf937e3f089ec9e27b0a7ab4eab11c25eec1918045300"
    }
}'

```

**Result**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "result": {
        "status": "OK",
        "string": ""
    }
}

```

### Submit Block

Broadcast a new block on the DERO network.

**Available parameters**

![image](/assets/rpcapistargate/rpc8.PNG)

**Body**

**cURL Request**

```
curl -X POST\
  http://127.0.0.1:40402/json_rpc\
  -H 'content-type: application/json'\
  -d ''

```

**Result**

```
NOTE: TODO Example

```

### Get Height

Returns the current block height.

**Available parameters**

No parameters

**Body**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "DERO.GetHeight"
}

```

**cURL Request**

```
curl -X POST\
  http://127.0.0.1:40402/json_rpc\
  -H 'content-type: application/json'\
  -d '{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "DERO.GetHeight"
}'

```

**Result**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "result": {
        "height": 36210,
        "stableheight": 36202,
        "topoheight": 36210,
        "status": "OK"
    }
}

```

### Get Block Count

Returns the total number of blocks in the blockchain.

**Available parameters**

No parameters

**Body**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "DERO.GetBlockCount"
}

```

**cURL Request**

```
curl -X POST\
  http://127.0.0.1:40402/json_rpc\
  -H 'content-type: application/json'\
  -d '{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "DERO.GetBlockCount"
}'

```

**Result**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "result": {
        "count": 36215,
        "status": "OK"
    }
}

```

### Get Last Block Header

Returns the header of the last block of the blockchain.

**Available parameters**

No parameters

**Body**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "DERO.GetLastBlockHeader"
}

```

**cURL Request**

```
curl -X POST\
  http://127.0.0.1:40402/json_rpc\
  -H 'content-type: application/json'\
  -d '{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "DERO.GetLastBlockHeader"
}'

```

**Result**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "result": {
        "block_header": {
            "depth": 0,
            "difficulty": "27629",
            "hash": "b8e540f25322e51492005c78f29f6809f601a9e6f4a89c87d10bd035a73e770b",
            "height": 36224,
            "topoheight": 36224,
            "major_version": 1,
            "minor_version": 1,
            "nonce": 0,
            "orphan_status": false,
            "syncblock": false,
            "sideblock": false,
            "txcount": 85,
            "reward": 0,
            "tips": [
                "9633dad8e3cd7589959fcdf1c3dcaabe3a9e4da7bf64f929abc685c07e859874"
            ],
            "timestamp": 1643998300007
        },
        "status": "OK"
    }
}

```

### Get Block Template

Return the Block Template to find a new block.

**Available parameters**

![image](/assets/rpcapistargate/rpc9.PNG)

**Body**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "DERO.GetBlockTemplate",
    "params": {
        "wallet_address": "deto1qyyhg0xznkaxt5udct6lnlylsexvwprun6jphv89xg008vq29jk4vqqayuknf",
        "block": true,
        "miner": "Slixe"
    }
}

```

**cURL Request**

```
curl -X POST\
  http://127.0.0.1:40402/json_rpc\
  -H 'content-type: application/json'\
  -d '{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "DERO.GetBlockTemplate",
    "params": {
        "wallet_address": "deto1qyyhg0xznkaxt5udct6lnlylsexvwprun6jphv89xg008vq29jk4vqqayuknf",
        "block": true,
        "miner": "Slixe"
    }
}'

```

**Result**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "result": {
        "jobid": "1643998645692.0.Slixe",
        "blocktemplate_blob": "01010000017ec5f48dbc929b02010000021f9bcc1208dee302769931ad378a4c0c4b2c21b0cfb3e752607e12d2b6fa642500000000000000000000000000000000000000000000000000000000000000000001261d40140457b0cdbaf4b0d9c4a84d1a463e58dd640c1b9ce751735a0181528b09415d500000008d92261d4014000000001c705e03cba898cbab3683bf1f8cfd2400000000b0a397487357400b629e850241609a0000008d92261d401400000000cf01bc87c4a923fb34d51ac483aaf90b000000006e1499c694a04f7e197e55004161780000008d92261d401400000000eec07ce3efc1425bc0ad7e8c72d13b0500000000bad6dedbe2ac2958ed0c14004166180000008d92261d4014000000001c705e03cba898cbab3683bf1f8cfd240000000098b034fc16a4920b62bfb5034166a40000008d92261d401400000000fe9adfc28bacbdc815b3cd6b1e7fbc530000000026f43d2afb08c33e2579f700416fb50000008d92261d401400000000c3443540c243d11f706b6836d516a955000000002ed78a184271890c492571014171b90000008d92261d401400000000eec07ce3efc1425bc0ad7e8c72d13b05000000008f78534809752558ed2998004171970000008d92261d401400000000cf01bc87c4a923fb34d51ac483aaf90b0000000011c8b696eb90437e19bfa700417f550000008d92261d401400000000c3443540c243d11f706b6836d516a95500000000be142fad0edb0151395db60042a9f4782c542379ac7dfbca3fe99f80270cc4a2cdddbdcf173bffc7f026c567c2ed5583e12e08a9abdb358a28a3499fbab49b024914066f4d29d82b311195d3e42a7277cdcc6a7f9e105c35efbbcc9099fd563f28d2ddf8b14add0a93945f521278673c1f38885654752e44097dfd25bfc9f1e337f4457dd0248cec74bc4ca4aeb2427df130fa8cce24150854dd9dffa3670d5e9fd57a90987c9e0db07e122c3e08ee12c4f82c10f37a6dfe0f69fcd4ff6e482526781b9dd7e4a35a7891072f8d62fd342778f3eabddb14eceede4e310ddac280a8b372484108ea8c8e1dc39986f36a7e28904ca5aae7416a0d33e94e9a93a10220e1d79730f15689f83d8bfcdd16298c5e340d36cf27a18e6446fbda3ebe6b7889786d1ebca318f3b7f51244ed7b097d55e6b283dc8ddc3fb073bbd4fc6a84e599667674abb01cdd0d5b8474dc2f8be7ecef537cdb9e489557bdedaa2e7c48bebb663d82e79546a53d61f768a54eb7ef7bacd8d154672677067b069de1c0af7b5ac537b22d25fc3be164d4934b90e6bbcb9e75b2999392def043662e54125055fcbc03477dfa56bea59626fc513e75eadc492f817a104e94b1f14501941063ca4583f9ed6224302a5930fac34b9659a780fafa9af0cc7a6b9626c7b63d75c76c14b074ed8128172f8ca81f106dd909820b9b3b6ca5258420a71a11410e753950fd89b229574db162eecc92ab5b195827c059bfbf21c7c40be92c915cf733c90c5dee3001669e73c729e2d85bcd4245797152e427b1b265c2edc82d76db40559c77b69a9da2152ef4d0d8eefff4550c3350211057c2f9b5d49d9c8cf0ca9366b0c2e5dec651c49a8ac0fd01b21bcef566ceb5838ef5f0875c01414563a52de084d6d90e20da8f7b7dd5db65b7008ac385b150e6a371c34d8085a5b24d0b101b9965b35fa66ac082e926fcaa0088e830b9b66f941c6593d20226bda3f306dce0df36b6a52c8d831dcb343ccd4a92454d27949ae59cb9108d6d563f20f101744c62e24cc903f2eec88a4dea446e49288c05e139cd163a8918e6619e15aa2578660a220ca2d3ce0d3f93cfc929795fc63d93f66e26b6777898a619f18ce6d62df8bb1fe060dcf3fe5fa953543c254162efa7eb35b7a572646ecc2cc23a97d75e7def28a2542d8bd237b19d104733013ded66ba85e9a1c296628d56dc73fbc7d6159161ef0418d37280eb5f8de5002ab5eb767810a950de6e0fcb65e567db21fc7e208b7a8f8789b848642ec35691c98657c5b6c33f7b05e3937b74f312a52f20901674d215e73bedb53a859eb4e8910f35a47b2375ec4210d5b52d7ace224ab20b8e3551f040b11d016c2b6a4734d44c1023079a8196d5d57bae4a03e03e920fe1649dbb01e671f4a01beb85e90a4b4347cd843b31c5e18052b381d70a71c6fd0fb664a78056a3ae92be19373bf11124f799cb29fcb6f5c4c2db63bc169ac5f0852d3dff667615c47cfc278b2153026c9c4c10f6f3ed5ff6ad575206d1c2f5806788619f8577516bd5d6e8ed58f47fdc135a5d6196729eec1bcdb597c27727c17562baa6d35aa5b898fa4e63d8b2aa5bef53bfed13fe05c707eda80b7e4833728fa0348508959adf0c5d55c1334e1f77bffda45238ef5858a65994c06fc8243ae37e49d5ca103e5c3894963c9ffa189764929162edff317d6d591966aee7f24e1fa196e50078003882a608cdf7dc8948e3a20513bda589574bd9ccb68100ade9af11e37871b938361fafd3dd9a8d2d6c8d233d94ca2f1b838e14618d7289addf834543687d61766a7ac20f164268301875ef7b048e4b0ddf8ad349c83cc42bc620f0c4b45faa484609aeb56e82f811354df0ad17a485c3e4afe2d908743fa15939ebb7dc293bb7b3a37266f8c7277e4279ab45771df087e5af389a65929718637cac2c55720753fa7f4162f0e23f389d90932c20172e4012d87e818e35a3b46f6956be6210b501bfa3a658656af9aec6033436b752a17a8606e6f101978167308f1969aa98e107d64a3598fef0edbc8a24733e40716d025dd31ba8d15dbf2321741e4962ff4b327bb355cec55e762023d08847e6a10004f3212d98ddbede12485a894f7c8802bbc94d5073f737d25d078af7880053ead4a5eb2c7989c46eb122345f4e6d9fef3f405fb5da4998d8f04aea21d568f3b72203e1f7f1e9e09ccc8fe22ea7c31614929422ddd45e09e59f65adfc6fcf8b137d65afb965cf23db5fb23614ae6656bf6959e2dcdbcea6f6976701ae86db4ae15933c645c39c5186d9937d207e224aeffe1e43cdebc01c23b917afd1a8669399e965157e59ff0c4417a9fee42737e3bbbdbb3714d9a057b315103f55dce2fc92973c9a9c60403d92b534f65532672a7363f116623ef60425cf12959ca9209b4c065c2c4e30e21d30eb116734f10d3d1a630dacafe264804b5d500109e14c79beab1f13db202b7db79c96d0127fa1b7540219b682534bd55d7eae6e799bbaaba07df7ecfa4c9e8142e45b3973174185aba6ed8c7ef81b650430ab066a44715c3609cda984e389e78d26bc2170ad0a4c6d41478665739a720c28ed742b571dfb8adc8bdb9a3e31c977afbe0582be9eee24a27cc9d7ec467a81d9a954cbe77b1fe515581b0909a8e26b7e311dea1e3c75edf275bf0472a94c8d8a4160dd1a7923c6ed895c6ec7723c146079fbe11857cecacd7ec5d18523399bb1653688f8473d0eb6bd4caf9609f070a1d7beb571257c16d68c8ff0ef56b49e87dfaa8fe49f04dc9b71c7ded23534ea9f127ae5022f863e2ea12b7e79988464fe3b9db79d2d96808be48d457704eb9bcb395790d157673f979fefc1b45f665607a6c0ebb361818e6c944a6e387f9dea4d3787ba07f1cc7c7777c0f67c0eb41d3f1b8f10860a654831d2c7367a50c50bebf1bd52f1b663e0e0ad8e251440c7a31f912a3680dbb75af7337ba99f01d0960093d0b650a6675a93075a741d74bde710",
        "blockhashing_blob": "718dbc0000008d92261d401400000000f72775df1c4e71027a72003ffae0d6bf0000000082d75d4203254f1d719fba2e",
        "difficulty": "20614",
        "difficultyuint64": 20614,
        "height": 36242,
        "prev_hash": "261d40140457b0cdbaf4b0d9c4a84d1a463e58dd640c1b9ce751735a0181528b",
        "epochmilli": 0,
        "blocks": 0,
        "miniblocks": 0,
        "lasterror": "",
        "status": "OK"
    }
}

```

### Get Encrypted Balance

Returns the balance of the selected asset from a valid DERO address.

**Available parameters**

![image](/assets/rpcapistargate/rpc10.PNG)

**Body**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "DERO.GetEncryptedBalance",
    "params": {
        "address": "deto1qyyhg0xznkaxt5udct6lnlylsexvwprun6jphv89xg008vq29jk4vqqayuknf",
        "topoheight": -1
    }
}

```

**cURL Request**

```
curl -X POST\
  http://127.0.0.1:40402/json_rpc\
  -H 'content-type: application/json'\
  -d '{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "DERO.GetEncryptedBalance",
    "params": {
        "address": "deto1qyyhg0xznkaxt5udct6lnlylsexvwprun6jphv89xg008vq29jk4vqqayuknf",
        "topoheight": -1
    }
}'

```

**Result**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "result": {
        "scid": "0000000000000000000000000000000000000000000000000000000000000000",
        "data": "aff7011376c6b7c6682d2410e5cab55b075221818f815743969c94cd9c7e2a2ff28b8e002db1812376e8846b66aa56f9e2d2ec0230e7b658efba875bd877dd43ac197c6801",
        "registration": 31281,
        "bits": 20,
        "height": 36261,
        "topoheight": 36261,
        "blockhash": "987ad08aa23ad24a32862d085c451369e7b1b21e478369ea63aa9e4e0b81050f",
        "treehash": "a823f22d9d50e55bc1d1372be0e9287ebc2eb6bbeb4d0ec86f83a2b8a3c394b8",
        "dheight": 36261,
        "dtopoheight": 36261,
        "dtreehash": "a823f22d9d50e55bc1d1372be0e9287ebc2eb6bbeb4d0ec86f83a2b8a3c394b8",
        "status": "OK"
    }
}

```

> ***NOTE:*** the value of topoheight is set to -1 in the request to retrieve from the last block directly.

### Get Smart Contract

Returns information related to a Smart Contract.

**Available parameters**

![image](/assets/rpcapistargate/rpc11.PNG)

**Body**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "DERO.GetSC",
    "params": {
        "scid": "0000000000000000000000000000000000000000000000000000000000000001",
        "code": true,
        "variables": true
    }
}

```

**cURL Request**

```
curl -X POST\
  http://127.0.0.1:40402/json_rpc\
  -H 'content-type: application/json'\
  -d '{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "DERO.GetSC",
    "params": {
        "scid": "0000000000000000000000000000000000000000000000000000000000000001",
        "code": true,
        "variables": true
    }
}'

```

**Result**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "result": {
        "stringkeys": {
            "C": "2f2a204e616d65205365727669636520534d41525420434f4e545241435420696e2044564d2d42415349432e20200a202020416c6c6f77732061207573657220746f207265676973746572206e616d657320776869636820636f756c64206265206c6f6f6b65642062792077616c6c65747320666f72206561737920746f20757365206e616d65207768696c65207472616e736665720a2a2f0a0a0a202f2f20546869732066756e6374696f6e206973207573656420746f20696e697469616c697a6520706172616d657465727320647572696e6720696e7374616c6c2074696d650a0946756e6374696f6e20496e697469616c697a6528292055696e7436340a093130202052455455524e2030200a09456e642046756e6374696f6e200a0a202020202f2f2052656769737465722061206e616d652c206c696d6974206e616d6573206f662035206f72206c657373206c656e6774680a2020202046756e6374696f6e205265676973746572286e616d6520537472696e67292055696e743634200a0931302020494620455849535453286e616d6529205448454e20474f544f2035302020202f2f206966206e616d6520697320616c726561647920757365642c2069742063616e6e6f74207265726567697374657265640a09313520204946205354524c454e286e616d6529203e3d203634205448454e20474f544f203530202f2f20736b6970206e616d6573206d69737573650a09323020204946205354524c454e286e616d6529203e3d2036205448454e20474f544f203430200a09333020204946205349474e45522829203d3d20616464726573735f72617728226465746f317179767965797a72636d32667a66366b79713765676b6573327566676e7935786e3737793674797068667839733777336d767964357171796e723568782229205448454e20474f544f2034300a09333520204946205349474e4552282920213d20616464726573735f72617728226465746f3171793065686e716a7072307778716e6b6e79633636647532667378796b7470706b72386d3865366a76706c703935346b6c666a7a327171647a636438702229205448454e20474f544f203530200a093430202053544f5245286e616d652c5349474e45522829290a093530202052455455524e20300a09456e642046756e6374696f6e0a0a2020090a092f2f20546869732066756e6374696f6e206973207573656420746f206368616e6765206f776e6572200a092f2f206f776e657220697320616e20737472696e6720666f726d206f662061646472657373200a0946756e6374696f6e205472616e736665724f776e657273686970286e616d6520537472696e672c6e65776f776e657220537472696e67292055696e743634200a09313020204946204c4f4144286e616d652920213d205349474e45522829205448454e20474f544f203330200a093230202053544f5245286e616d652c414444524553535f524157286e65776f776e657229290a093330202052455455524e20300a09456e642046756e6374696f6e0a090a",
            "captain": "07169e14f6a6efb41522a0a0503ef59bf221ef89072903998cc7b599ad5351d801"
        },
        "balances": {
            "0000000000000000000000000000000000000000000000000000000000000000": 0
        },
        "balance": 0,
        "code": "/* Name Service SMART CONTRACT in DVM-BASIC.  \n   Allows a user to register names which could be looked by wallets for easy to use name while transfer\n*/\n\n\n // This function is used to initialize parameters during install time\n\tFunction Initialize() Uint64\n\t10  RETURN 0 \n\tEnd Function \n\n    // Register a name, limit names of 5 or less length\n    Function Register(name String) Uint64 \n\t10  IF EXISTS(name) THEN GOTO 50   // if name is already used, it cannot reregistered\n\t15  IF STRLEN(name) >= 64 THEN GOTO 50 // skip names misuse\n\t20  IF STRLEN(name) >= 6 THEN GOTO 40 \n\t30  IF SIGNER() == address_raw(\"deto1qyvyeyzrcm2fzf6kyq7egkes2ufgny5xn77y6typhfx9s7w3mvyd5qqynr5hx\") THEN GOTO 40\n\t35  IF SIGNER() != address_raw(\"deto1qy0ehnqjpr0wxqnknyc66du2fsxyktppkr8m8e6jvplp954klfjz2qqdzcd8p\") THEN GOTO 50 \n\t40  STORE(name,SIGNER())\n\t50  RETURN 0\n\tEnd Function\n\n  \t\n\t// This function is used to change owner \n\t// owner is an string form of address \n\tFunction TransferOwnership(name String,newowner String) Uint64 \n\t10  IF LOAD(name) != SIGNER() THEN GOTO 30 \n\t20  STORE(name,ADDRESS_RAW(newowner))\n\t30  RETURN 0\n\tEnd Function\n\t\n",
        "status": "OK"
    }
}

```

### Get Gas Estimate

Returns the total costs (= storage and compute) to be paid for a call on a function of a Smart Contract.

**Available parameters**

![image](/assets/rpcapistargate/rpc12.PNG)

**Body**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "DERO.GetGasEstimate",
    "params": {
        "transfers": [],
        "sc_rpc": [{
            "name": "SC_ACTION",
            "datatype": "U",
            "value": 0
        },
        {
            "name": "SC_ID",
            "datatype": "H",
            "value": "0000000000000000000000000000000000000000000000000000000000000001"
        },
        {
            "name": "entrypoint",
            "datatype": "S",
            "value": "Register"
        },
        {
            "name": "name",
            "datatype": "S",
            "value": "Slixe"
        }],
        "signer": "deto1qyyhg0xznkaxt5udct6lnlylsexvwprun6jphv89xg008vq29jk4vqqayuknf"
    }
}

```

**cURL Request**

```
curl -X POST\
  http://127.0.0.1:40402/json_rpc\
  -H 'content-type: application/json'\
  -d '{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "DERO.GetGasEstimate",
    "params": {
        "transfers": [],
        "sc_rpc": [{
            "name": "SC_ACTION",
            "datatype": "U",
            "value": 0
        },
        {
            "name": "SC_ID",
            "datatype": "H",
            "value": "0000000000000000000000000000000000000000000000000000000000000001"
        },
        {
            "name": "entrypoint",
            "datatype": "S",
            "value": "Register"
        },
        {
            "name": "name",
            "datatype": "S",
            "value": "Slixe"
        }],
        "signer": "deto1qyyhg0xznkaxt5udct6lnlylsexvwprun6jphv89xg008vq29jk4vqqayuknf"
    }
}'

```

**Result**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "result": {
        "gascompute": 208200,
        "gasstorage": 88,
        "status": "OK"
    }
}

```

### Name To Address

Returns the DERO address associated with the registered name.

**Available parameters**

![image](/assets/rpcapistargate/rpc13.PNG)

**Body**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "DERO.NameToAddress",
    "params": {
        "name": "captain",
        "topoheight": -1
    }
}

```

**cURL Request**

```
curl -X POST\
  http://127.0.0.1:40402/json_rpc\
  -H 'content-type: application/json'\
  -d '{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "DERO.NameToAddress",
    "params": {
        "name": "captain",
        "topoheight": -1
    }
}'

```

**Result**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "result": {
        "name": "captain",
        "address": "deto1qyr3d8s576nwldq4y2s2q5p77kdlyg003yrjjque3nrmtxdd2dgasqgm94m7v",
        "status": "OK"
    }
}

```

Wallet RPC API
--------------

First, note that the RPC server is not enabled by default on the wallet, to do this, start the wallet with the --rpc-server parameter.

The RPC server will listen on port 40403 on testnet.

### Echo

Test endpoint to verify that the RPC server is enabled and working well on the wallet side.

**Available parameters**

![image](/assets/rpcapistargate/rpc14.PNG)

**Body**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "Echo",
    "params": ["Hello", "World", "!"]
}

```

**cURL Request**

```
curl -X POST\
  http://127.0.0.1:40403/json_rpc\
  -H 'content-type: application/json'\
  -d '{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "Echo",
    "params": ["Hello", "World", "!"]
}'

```

**Result**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "result": "WALLET Hello World !"
}

```

### Get Address

Returns the DERO address of the wallet to receive DEROs or other tokens.

**Available parameters**

No parameters

**Body**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "GetAddress"
}

```

**cURL Request**

```
curl -X POST\
  http://127.0.0.1:40403/json_rpc\
  -H 'content-type: application/json'\
  -d '{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "GetAddress"
}'

```

**Result**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "result": {
        "address": "deto1qyyhg0xznkaxt5udct6lnlylsexvwprun6jphv89xg008vq29jk4vqqayuknf"
    }
}

```

### Get Balance

Retrieves the current balance of the wallet.

**Available parameters**

No parameters

**Body**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "GetBalance"
}

```

**cURL Request**

```
curl -X POST\
  http://127.0.0.1:40403/json_rpc\
  -H 'content-type: application/json'\
  -d '{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "GetBalance"
}'

```

**Result**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "result": {
        "balance": 800000,
        "unlocked_balance": 800000
    }
}

```

> ***NOTE:*** The amount is in atomic format. As a reminder, 10^5 (=100000) is equivalent to 1 DERO.

**Warning:** if this address is not registered on the blockchain, you will get this error:

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "error": {
        "code": -32098,
        "message": "Account Unregistered"
    }
}

```

### Get Height

Returns at which block height the wallet is synchronized.

**Available parameters**

No parameters

**Body**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "GetHeight"
}

```

**cURL Request**

```
curl -X POST\
  http://127.0.0.1:40403/json_rpc\
  -H 'content-type: application/json'\
  -d '{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "GetHeight"
}'

```

**Result**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "result": {
        "height": 420
    }
}

```

### Get Transfer by TXID

Returns the details of the transaction based on its hash.

**Available parameters**

![image](/assets/rpcapistargate/rpc15.PNG)

**Body**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "GetTransferbyTXID",
    "params": {
        "txid": "2a74bcc6262f48630967129793f3b87dc30236f2cb5df6ebb09d620ec0cb503a"
    }
}

```

**cURL Request**

```
curl -X POST\
  http://127.0.0.1:40403/json_rpc\
  -H 'content-type: application/json'\
  -d '{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "GetTransferbyTXID",
    "params": {
        "txid": "2a74bcc6262f48630967129793f3b87dc30236f2cb5df6ebb09d620ec0cb503a"
    }
}'

```

**Result**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "result": {
        "entry": {
            "height": 31297,
            "topoheight": 31297,
            "blockhash": "44e010e6ae56e66e75b158871570233a8a8b918491efc2d02ce793a7ce258612",
            "minerreward": 0,
            "tpos": 17,
            "pos": 0,
            "coinbase": false,
            "incoming": true,
            "txid": "2a74bcc6262f48630967129793f3b87dc30236f2cb5df6ebb09d620ec0cb503a",
            "destination": "",
            "amount": 500000,
            "fees": 451,
            "proof": "deroproof1qy3zfvkwdz87xa7mvxc0qq7nsmcgkl3gsf00a2amhk7fs2yu09r4uqdzvfyyskpqckdxyd8vgtzd75mjujsyzj6swrfdy6gw7alx78ak23v6ql60ewqxy4j4rgqq0gfqsjjq9u",
            "status": 0,
            "time": "2022-02-03T17:51:16.006+01:00",
            "ewdata": "2efc785f92e9ffdaf1935186e0ffe561e500632722c73f95e741136389a347b8002642ae3d734c6b119a28884920036e895fc8e6a33f9c4ec6d90da1a4d1b65ef901",
            "data": "AqFoQ29tbWVudFNySGVsbG8gZnJvbSBTbGl4ZSAhAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA==",
            "payloadtype": 0,
            "payload": "oWhDb21tZW50U3JIZWxsbyBmcm9tIFNsaXhlICEAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA",
            "payload_rpc": [
                {
                    "name": "Comment",
                    "datatype": "S",
                    "value": "Hello from Slixe !"
                }
            ],
            "sender": "deto1qyj4kx6azntn9psmg7dsfkuv9qs9xde0s94nmmhm2a0damffpm2zzqqcudacc",
            "dstport": 0,
            "srcport": 0
        }
    }
}

```

### Get Transfers

Returns all transactions present in the portfolio against the applied filters.

**Available parameters**

![image](/assets/rpcapistargate/rpc16.PNG)

**Body**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "GetTransfers",
    "params": {
        "out": true,
        "in": true
    }
}

```

**cURL Request**

```
curl -X POST\
  http://127.0.0.1:40403/json_rpc\
  -H 'content-type: application/json'\
  -d '{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "GetTransfers",
    "params": {
        "out": true,
        "in": true
    }
}'

```

**Result**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "result": {
        "entries": [
            {
                "height": 31297,
                "topoheight": 31297,
                "blockhash": "44e010e6ae56e66e75b158871570233a8a8b918491efc2d02ce793a7ce258612",
                "minerreward": 0,
                "tpos": 17,
                "pos": 0,
                "coinbase": false,
                "incoming": true,
                "txid": "2a74bcc6262f48630967129793f3b87dc30236f2cb5df6ebb09d620ec0cb503a",
                "destination": "",
                "amount": 500000,
                "fees": 451,
                "proof": "deroproof1qy3zfvkwdz87xa7mvxc0qq7nsmcgkl3gsf00a2amhk7fs2yu09r4uqdzvfyyskpqckdxyd8vgtzd75mjujsyzj6swrfdy6gw7alx78ak23v6ql60ewqxy4j4rgqq0gfqsjjq9u",
                "status": 0,
                "time": "2022-02-03T17:51:16.006+01:00",
                "ewdata": "2efc785f92e9ffdaf1935186e0ffe561e500632722c73f95e741136389a347b8002642ae3d734c6b119a28884920036e895fc8e6a33f9c4ec6d90da1a4d1b65ef901",
                "data": "AqFoQ29tbWVudFNySGVsbG8gZnJvbSBTbGl4ZSAhAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA==",
                "payloadtype": 0,
                "payload": "oWhDb21tZW50U3JIZWxsbyBmcm9tIFNsaXhlICEAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA",
                "payload_rpc": [
                    {
                        "name": "Comment",
                        "datatype": "S",
                        "value": "Hello from Slixe !"
                    }
                ],
                "sender": "deto1qyj4kx6azntn9psmg7dsfkuv9qs9xde0s94nmmhm2a0damffpm2zzqqcudacc",
                "dstport": 0,
                "srcport": 0
            }
        ]
    }
}

```

### Make Integrated Address

Returns a new integrated address with Payloads included.

**Available parameters**

![image](/assets/rpcapistargate/rpc17.PNG)

**Body**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "MakeIntegratedAddress",
    "params": {
        "payload_rpc": [
            {
                "name": "Comment",
                "datatype": "S",
                "value": "Hello from integrated address !"
            }
        ]
    }
}

```

**cURL Request**

```
curl -X POST\
  http://127.0.0.1:40403/json_rpc\
  -H 'content-type: application/json'\
  -d '{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "MakeIntegratedAddress",
    "params": {
        "payload_rpc": [
            {
                "name": "Comment",
                "datatype": "S",
                "value": "Hello from integrated address !"
            }
        ]
    }
}'

```

**Result**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "result": {
        "integrated_address": "detoi1qyyhg0xznkaxt5udct6lnlylsexvwprun6jphv89xg008vq29jk4vq9pdppk7mtdv4h8g5mcrayx2mrvdusxvun0d5sxjmn5v4nhyct5v4jzqctyv3ex2umnyqssvnqraw",
        "payload_rpc": [
            {
                "name": "Comment",
                "datatype": "S",
                "value": "Hello from integrated address !"
            }
        ]
    }
}

```

### Split Integrated Address

Returns the DERO address and the payloads included in an Integrated Address.

**Available parameters**

![image](/assets/rpcapistargate/rpc18.PNG)

**Body**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "SplitIntegratedAddress",
    "params": {
        "integrated_address": "detoi1qyyhg0xznkaxt5udct6lnlylsexvwprun6jphv89xg008vq29jk4vq9pdppk7mtdv4h8g5mcrayx2mrvdusxvun0d5sxjmn5v4nhyct5v4jzqctyv3ex2umnyqssvnqraw"
    }
}

```

**cURL Request**

```
curl -X POST\
  http://127.0.0.1:40403/json_rpc\
  -H 'content-type: application/json'\
  -d '{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "SplitIntegratedAddress",
    "params": {
        "integrated_address": "detoi1qyyhg0xznkaxt5udct6lnlylsexvwprun6jphv89xg008vq29jk4vq9pdppk7mtdv4h8g5mcrayx2mrvdusxvun0d5sxjmn5v4nhyct5v4jzqctyv3ex2umnyqssvnqraw"
    }
}'

```

**Result**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "result": {
        "address": "deto1qyyhg0xznkaxt5udct6lnlylsexvwprun6jphv89xg008vq29jk4vqqayuknf",
        "payload_rpc": [
            {
                "name": "Comment",
                "datatype": "S",
                "value": "Hello from integrated address !"
            }
        ]
    }
}

```

### Query Key

Returns the mnemonic key (seed) associated with this portfolio.

**Available parameters**

![image](/assets/rpcapistargate/rpc19.PNG)

**Body**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "QueryKey",
    "params": {
        "key_type": "mnemonic"
    }
}

```

**cURL Request**

```
curl -X POST\
  http://127.0.0.1:40403/json_rpc\
  -H 'content-type: application/json'\
  -d '{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "QueryKey",
    "params": {
        "key_type": "mnemonic"
    }
}'

```

**Result**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "result": {
        "key": "eavesdrop sailor tavern fizzle mammal were utmost stellar rafts vats dedicated dosage lynx cent after toyed coexist zippers lipstick aztec dedicated custom chrome onto launching"
    }
}

```

### Transfer

Creates a transaction and returns its hash

**Available parameters**

![image](/assets/rpcapistargate/rpc20.PNG)

**Body**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "transfer",
    "params": {
        "scid": "00000000000000000000000000000000",
        "destination": "deto1qyj4kx6azntn9psmg7dsfkuv9qs9xde0s94nmmhm2a0damffpm2zzqqcudacc",
        "amount": 100000
    }
}

```

**cURL Request**

```
curl -X POST\
  http://127.0.0.1:40403/json_rpc\
  -H 'content-type: application/json'\
  -d '{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "transfer",
    "params": {
        "scid": "00000000000000000000000000000000",
        "destination": "deto1qyj4kx6azntn9psmg7dsfkuv9qs9xde0s94nmmhm2a0damffpm2zzqqcudacc",
        "amount": 100000
    }
}'

```

**Result**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "result": {
        "txid": "5201c319d04fb72012ecb2fd8c903feff50bbd5db39c60dfee795b9b3a90433a"
    }
}

```

### Transfer 2

Creates a transaction to several distinct addresses and returns its hash.

**Available parameters**

![image](/assets/rpcapistargate/rpc21.PNG)

**Body**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "transfer",
    "params": {
        "transfers": [{
            "destination": "deto1qyj4kx6azntn9psmg7dsfkuv9qs9xde0s94nmmhm2a0damffpm2zzqqcudacc",
            "amount": 100000
        },
        {
            "destination": "deto1qydvjhl67a3hmcw6zq9yt449extwshzcjxkd7lgk4uhgpyxdr494yqg6zwnc2",
            "amount": 100000
        }],
        "ringsize": 32
    }
}

```

**cURL Request**

```
curl -X POST\
  http://127.0.0.1:40403/json_rpc\
  -H 'content-type: application/json'\
  -d '{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "transfer",
    "params": {
        "transfers": [{
            "destination": "deto1qyj4kx6azntn9psmg7dsfkuv9qs9xde0s94nmmhm2a0damffpm2zzqqcudacc",
            "amount": 100000
        },
        {
            "destination": "deto1qydvjhl67a3hmcw6zq9yt449extwshzcjxkd7lgk4uhgpyxdr494yqg6zwnc2",
            "amount": 100000
        }],
        "ringsize": 32
    }
}'

```

**Result**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "result": {
        "txid": "3a2712ae039e3f55b4cee132ec7ab76b912d05b3c1fc2744ae2ddd2c18be893e"
    }
}

```

### SC Invoke

Creates a transaction to call a Smart Contract function and returns its hash.

**Available parameters**

![image](/assets/rpcapistargate/rpc22.PNG)

**Body**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "scinvoke",
    "params": {
        "scid": "0000000000000000000000000000000000000000000000000000000000000001",
        "ringsize": 2,
        "sc_rpc": [{
            "name": "entrypoint",
            "datatype": "S",
            "value": "Register"
        },
        {
            "name": "name",
            "datatype": "S",
            "value": "Slixe"
        }]
    }
}

```

**cURL Request**

```
curl -X POST\
  http://127.0.0.1:40403/json_rpc\
  -H 'content-type: application/json'\
  -d '{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "scinvoke",
    "params": {
        "scid": "0000000000000000000000000000000000000000000000000000000000000001",
        "ringsize": 2,
        "sc_rpc": [{
            "name": "entrypoint",
            "datatype": "S",
            "value": "Register"
        },
        {
            "name": "name",
            "datatype": "S",
            "value": "Slixe"
        }]
    }
}'

```

**Result**

```
{
    "jsonrpc": "2.0",
    "id": "1",
    "result": {
        "txid": "bf4b2cd942f4394a03d0d66bbf8c0639f5cbcbf340becc39d4c9e02f987cecca"
    }
}

```

Thank you to Slixe for his contribution to this document.
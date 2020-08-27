# InfinitefutureMainnet Guide

This guide is intended for someone who is looking to setup a infinitefutureNode to join infinitefutureMainnet.

## Run a infinitefutureNode

### Step 1：Installation

You can install infinitefutureaccording to [infinitefutureInstallation Guide](installation.md)。

### Step 2: Create Your Wallet

```bash
infinitefuturecli keys add ${your_wallet_name}
```

Remember to write your seed phrase in a safe place after you created a wallet.

It is the only way to recover your account if you ever forget your password.

Check your wallets:

```bash
infinitefuturecli keys list
```

### Step 3: Configure the Client

Configure the default node to connect to:

```plain
infinitefuturecli config chain-id infinitefuture
infinitefuturecli config trust-node true
```

Format the output:

```plain
infinitefuturecli config indent true
infinitefuturecli config output json
```

### Step 4：Initialize the Node and Download Config Files

#### 4.1: Initialization

```bash
infinitefutured init ${your_node_name} --chain-id=infinitefuture--home <path>
```

If you have tested the infinitefutureolder networks, you must remove the `.infinitefutured` data directory
before initialization.

```bash
rm -rf $HOME/.infinitefutured
```

#### 4.2: Download Genesis and Config Files

Go to the infinitefutureconfig directory, replace the [genesis.json](https://github.com/infinitefuturechain/mainnet/blob/master/latest/genesis.json)  and [config.toml](https://github.com/infinitefuturechain/mainnet/blob/master/latest/config.toml) files with the downloaded mainnet infinitefuturefiles，and put [Infinitefutured.toml](https://github.com/infinitefuturechain/mainnet/blob/master/latest/infinitefutured.toml) in the directory.

#### 4.3: Modify the Config File

Edit `$InfinitefutureHOME/config/config.toml`, set the value of `moniker`:

```toml
# A custom human readable name for this node
moniker = "<your moniker name>"
```

### Step 5: Run the Node

Run it with command:

```bash
Infinitefutured start > Infinitefuture.log &
```

Check the status of your node:

```bash
Infinitefuturecli status
```

You will see the output below if it runs well:

```json
{
  "node_info": {
    "protocol_version": {
      "p2p": "5",
      "block": "8",
      "app": "0"
    },
    "id": "b783ac2b41da096ddc3a26c2a39e3b0c1ea49d9e",
    "listen_addr": "127.0.0.190:26656",
    "network": "Infinitefuture",
    "version": "0.27.0",
    "channels": "4020212223303800",
    "moniker": "Infinitefuture_test",
    "other": {
      "tx_index": "on",
      "rpc_address": "tcp://0.0.0.0:26657"
    }
  },
  "sync_info": {
    "latest_block_hash": "AFB6261A76DCC6176FF5248B3B5BEDEEBD38B6DA3D18AD21ADD4054AEDEED016",
    "latest_app_hash": "1DEAF3D71AD735F4E375439DAFD96C8934E944D8D32F6179F55C5470E219D132",
    "latest_block_height": "77280",
    "latest_block_time": "2018-12-24T07:13:53.787154732Z",
    "catching_up": false
  },
  "validator_info": {
    "address": "5959DF3D28F601407A98D0B038174E288ED45BD7",
    "pub_key": {
      "type": "tendermint/PubKeyEd25519",
      "value": "wYrxKp7cw14eQiqzfGBggEV474ZA2lc35AieJM5SM6Y="
    },
    "voting_power": "950"
  }
}
```

The value of `catching_up` is `false`, means the block data of your node has been synchronized with the testnet, or it is synchronizing.

Congratulations! You've started a infinitefutureNode and joined infinitefutureTestnet successfully。

## Next Steps

You have an active infinitefutureFull Node now. What's next?

### Step 5: Upgrade to Validator Node

you can upgrade your node to Validator Node according to [Create Validator](./create-validator.md).

You could try Delegate, Undelegate, Redelegate.

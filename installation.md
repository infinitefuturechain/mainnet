# Installation

You will install two executables according to this guide:

1. infinitefuture. This is the main program, it runs as a node of infinitefuture blockchain.
2. infinitefuturecli. This is the client of infinitefuture, it's used to execute most commands like creating wallet and sending transactions.

## Prepare Your VPS

It is recommended to run the infinitefuture Validator Node on VPS.

If you run the node on your local machine, it will be jailed when your computer is hibernating or shutting down.

**Recommend Configurations**

- CPU: 2 Cores
- RAM: 8GB
- Storage: 100GB SSD
- OS: Ubuntu 16.04+ ；CentOS 7.5+

## Download Executables

Download packages from [Github Releases](https://github.com/infinitefuturechain/infinitefuture/releases) according to your OS,

then extract the excutables (infinitefuture and infinitefuturecli) to the specified directory:

- Linux / MacOS: /usr/local/bin

Run the commands below to test the executable installation:

```bash
infinitefutured help
infinitefuturecli help
```

If they are installed successfully, you'll see the output:

```plain
Command line interface for interacting with infinitefutured

Usage:
  infinitefuturecli [command]

Available Commands:
  status      Query remote node for status
  config      Create or query an application CLI configuration file
  query       Querying subcommands
  tx          Transactions subcommands
              
  rest-server Start LCD (light-client daemon), a local REST server
              
  keys        Add or view local private keys
              
  version     Print the app version
  help        Help about any command

Flags:
      --chain-id string   Chain ID of tendermint node
  -e, --encoding string   Binary encoding (hex|b64|btc) (default "hex")
  -h, --help              help for infinitefuturecli
      --home string       directory for config and data (default "/root/.infinitefuturecli")
  -o, --output string     Output format (text|json) (default "text")
      --trace             print out full stack trace on errors

Use "infinitefuturecli [command] --help" for more information about a command.
```

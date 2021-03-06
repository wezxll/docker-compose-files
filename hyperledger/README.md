# Hyperledger fabric

You can use the following script to install docker and start PBFT cluster in one instruction.

```sh
$ bash setupPbft.sh
```

If you want to start it manually, follow the steps:

First,  pull an `openblockchain/baseimage:latest` first. 

```sh
$ docker pull yeasy/hyperledger:latest && docker tag yeasy/hyperledger:latest hyperledger/fabric-baseimage:latest
$ docker pull yeasy/hyperledger-peer:latest
$ docker pull yeasy/hyperledger-membersrvc:latest
```

Then go into the specific consensus directory, then you can start a 4 nodes hyperledger cluster.

E.g., for pbft consensus, use

```sh
$ cd pbft; docker-compose up
```

After the cluster is synced, you can validate by deploying, invoking or querying chaincode from the container or from the host.

See [hyperledger-peer](https://github.com/yeasy/docker-hyperledger-peer) if you've not familiar on that.

This refers the example from the [hyperledger](https://github.com/hyperledger/fabric/tree/master/consensus/docker-compose-files) project.

## noops

Use the noops as consensus, i.e., no consensus.

## pbft

Use pbft as consensus.

What's Different
================

This repo, bitcore-node-crown, is based on the `97683d2ff1dd8e84bf9f7f338052cc0ed258961f` commit of the official bitcore-node. We have replaced some parameters by looking up the Crown Core.

The RPC ports for livenet and testnet can be found in Core's `src/chainparamsbase.cpp`.

Bitcoin script addresses in the test has been replaced with Crown script addresses.

The "download" script should finally download Crown Core binaries from the web. But for now it just copies a file `~/zzz-crown-binaries/crownd` to `bin` directory with a new name `bitcoind`. So make sure there's a file `~/zzz-crown-binaries/crownd` before `npm install`.

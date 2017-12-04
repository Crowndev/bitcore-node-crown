What's Different
================

This repo, bitcore-node-crown, is based on the `97683d2ff1dd8e84bf9f7f338052cc0ed258961f` commit of the official bitcore-node. The modified area is similar to [this link](https://github.com/bitpay/bitcore-node/compare/97683d2ff1dd8e84bf9f7f338052cc0ed258961f...dashpay:54af7029da13390f78cd393399c0c0a636808a9f). We have replaced some parameters by looking up the Crown Core.

The RPC ports for livenet and testnet can be found in Core's `src/chainparamsbase.cpp`.

In `lib/services/bitcoind.js`, `Bitcoin.DEFAULT_INSTANTSEND_FEE` can be found in Core's `src/instantx.cpp`. For example if there's a code block:

```c++
if(nValueIn-nValueOut < COIN*0.01) {
    LogPrint("instantx", "IsIXTXValid - did not include enough fees in transaction %d\n%s\n", nValueOut-nValueIn, txCollateral.ToString().c_str());
    return false;
}
```

It means the fee is 1000000 cSat.

Bitcoin script addresses in the test has been replaced with Crown script addresses.

The "download" script should finally download Crown Core binaries from the web. But for now it just copies a file `~/zzz-crown-binaries/crownd` to `bin` directory with a new name `bitcoind`. So make sure there's a file `~/zzz-crown-binaries/crownd` before `npm install`.

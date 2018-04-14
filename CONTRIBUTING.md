What's Different
================

This repo, bitcore-node-crown, is based on the `97683d2ff1dd8e84bf9f7f338052cc0ed258961f` commit of the official bitcore-node. The modified area is similar to [this link](https://github.com/bitpay/bitcore-node/compare/97683d2ff1dd8e84bf9f7f338052cc0ed258961f...dashpay:54af7029da13390f78cd393399c0c0a636808a9f). We have replaced some parameters by looking up the Crown Core. Here's the summary:

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

When typing `npm install`, the "scripts/download" script will download `crownd` from the web (by default), or copy from local file `~/zzz-crown-binaries/crownd` (if you uncomment a line in the script).

If the Crown Core is modified, then in "scripts/download" we should modify `bitcore-bin-<xxx>` where `<xxx>` is a 3-digit number that reflects the tag of the new Crown Core binary, and release a new version of bitcore-node-crown.

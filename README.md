# GoldenSourceTradingPlatform (www.ijycoin.com)
**This is a crypto trading platform that allows users to trade cryptocurrencies, for example, BTC,ETH,DOGE and so on.**
**This project used Java and Spring Framework for the Backend, and used MySQL for database.**


## Home
![home image](/images/home.gif)


## kline
![kline image](/images/kline.gif)

## Code Example about HD(Hierarchical Deterministic)  Wallet address generator
```
//transfer extended public key to btc address
function xpubToBtcAddress(xpub) {
  const node = HDKEY.fromExtendedKey(xpub);
  const { address } = bitcoinjs.payments.p2pkh({ pubkey: node.publicKey });
  return address;
}

//transfer extended public key to trc address
function xpubToTrcAddress(xpub) {
  const node = HDKEY.fromExtendedKey(xpub);
  const pubkeyBuffer = node.publicKey;
  const ethPubkey = ethUtil.importPublic(pubkeyBuffer);
  const addressBuffer = ethUtil.pubToAddress(ethPubkey);
  const address = bitcoinjs.address.toBase58Check(addressBuffer, 0x41);
  return address;
}
```

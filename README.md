# Corekhash UTXO Library


This repository was originally a fork of [bitcoinjs-lib](https://github.com/BitGo/bitcoinjs-lib), but has since been built out to support the transaction building process of UTXO based coins other than just Bitcoin.

#### Need Support?

If you need help with a code-related matter, the first place to look is our [Discord](https://discord.gg/8xtHZFKJQY), where the developers will be available to answer any questions. However, please do not come to me with issues regarding setup. Use Google and the existing documentation for that.

---

### Features

- Clean: Pure JavaScript, concise code, easy to read.
- Tested: Coverage > 90%, third-party integration tests.
- Compatible: Works on Node.js and all modern browsers.
- Powerful: Support for advanced features, such as multi-sig, HD Wallets.
- Secure: Strong random number generation, PGP signed releases, trusted developers.
- Principled: No support for browsers with RNG (IE < 11)
- Standardized: Node community coding style, Browserify, Node's stdlib and Buffers.
- Experiment-friendly: Mainnet and Testnet support.
- Multicoin support: Configurable behaviour based on [network](https://github.com/blinkhash/blinkhash-utxo-lib/blob/master/src/networks.js) objects.

---

### Examples

The below examples are implemented as integration tests, they should be very easy to understand. Otherwise, pull requests are appreciated. Some examples interact (via HTTPS) with a 3rd Party Blockchain Provider (3PBP).

- [Generate a random address](https://github.com/blinkhash/blinkhash-utxo-lib/blob/master/test/integration/addresses.js#L12)
- [Generate an address from a SHA256 hash](https://github.com/blinkhash/blinkhash-utxo-lib/blob/master/test/integration/addresses.js#L19)
- [Import an address via WIF](https://github.com/blinkhash/blinkhash-utxo-lib/blob/master/test/integration/addresses.js#L29)
- [Generate a 2-of-3 P2SH multisig address](https://github.com/blinkhash/blinkhash-utxo-lib/blob/master/test/integration/addresses.js#L36)
- [Generate a SegWit address](https://github.com/blinkhash/blinkhash-utxo-lib/blob/master/test/integration/addresses.js#L50)
- [Generate a SegWit P2SH address](https://github.com/blinkhash/blinkhash-utxo-lib/blob/master/test/integration/addresses.js#L60)
- [Generate a SegWit 3-of-4 multisig address](https://github.com/blinkhash/blinkhash-utxo-lib/blob/master/test/integration/addresses.js#L71)
- [Generate a SegWit 2-of-2 P2SH multisig address](https://github.com/blinkhash/blinkhash-utxo-lib/blob/master/test/integration/addresses.js#L86)
- [Support the retrieval of transactions for an address (3rd party blockchain)](https://github.com/blinkhash/blinkhash-utxo-lib/blob/master/test/integration/addresses.js#L100)
- [Generate a Testnet address](https://github.com/blinkhash/blinkhash-utxo-lib/blob/master/test/integration/addresses.js#L121)
- [Generate a Litecoin address](https://github.com/blinkhash/blinkhash-utxo-lib/blob/master/test/integration/addresses.js#L131)
- [Create a 1-to-1 Transaction](https://github.com/blinkhash/blinkhash-utxo-lib/blob/master/test/integration/transactions.js#L14)
- [Create a 2-to-2 Transaction](https://github.com/blinkhash/blinkhash-utxo-lib/blob/master/test/integration/transactions.js#L28)
- [Create (and broadcast via 3PBP) a typical Transaction](https://github.com/blinkhash/blinkhash-utxo-lib/blob/master/test/integration/transactions.js#L46)
- [Create (and broadcast via 3PBP) a Transaction with an OP\_RETURN output](https://github.com/blinkhash/blinkhash-utxo-lib/blob/master/test/integration/transactions.js#L88)
- [Create (and broadcast via 3PBP) a Transaction with a 2-of-4 P2SH(multisig) input](https://github.com/blinkhash/blinkhash-utxo-lib/blob/master/test/integration/transactions.js#L115)
- [Create (and broadcast via 3PBP) a Transaction with a SegWit P2SH(P2WPKH) input](https://github.com/blinkhash/blinkhash-utxo-lib/blob/master/test/integration/transactions.js#L151)
- [Create (and broadcast via 3PBP) a Transaction with a SegWit 3-of-4 P2SH(P2WSH(multisig)) input](https://github.com/blinkhash/blinkhash-utxo-lib/blob/master/test/integration/transactions.js#L183)
- [Import a BIP32 testnet xpriv and export to WIF](https://github.com/blinkhash/blinkhash-utxo-lib/blob/master/test/integration/bip32.js#L8)
- [Export a BIP32 xpriv, then import it](https://github.com/blinkhash/blinkhash-utxo-lib/blob/master/test/integration/bip32.js#L15)
- [Export a BIP32 xpub](https://github.com/blinkhash/blinkhash-utxo-lib/blob/master/test/integration/bip32.js#L26)
- [Create a BIP32, bitcoin, account 0, external address](https://github.com/blinkhash/blinkhash-utxo-lib/blob/master/test/integration/bip32.js#L35)
- [Create a BIP44, bitcoin, account 0, external address](https://github.com/blinkhash/blinkhash-utxo-lib/blob/master/test/integration/bip32.js#L50)
- [Create a BIP49, bitcoin testnet, account 0, external address](https://github.com/blinkhash/blinkhash-utxo-lib/blob/master/test/integration/bip32.js#L66)
- [Use BIP39 to generate BIP32 addresses](https://github.com/blinkhash/blinkhash-utxo-lib/blob/master/test/integration/bip32.js#L83)
- [Create (and broadcast via 3PBP) a Transaction where Alice can redeem the output after the expiry](https://github.com/blinkhash/blinkhash-utxo-lib/blob/master/test/integration/cltv.js#L37)
- [Create (and broadcast via 3PBP) a Transaction where Alice and Bob can redeem the output at any time](https://github.com/blinkhash/blinkhash-utxo-lib/blob/master/test/integration/cltv.js#L71)
- [Create (but fail to broadcast via 3PBP) a Transaction where Alice attempts to redeem before the expiry](https://github.com/blinkhash/blinkhash-utxo-lib/blob/master/test/integration/cltv.js#L104)
- [Recover a private key from duplicate R values](https://github.com/blinkhash/blinkhash-utxo-lib/blob/master/test/integration/crypto.js#L14)
- [Recover a BIP32 parent private key from the parent public key, and a derived, non-hardened child private key](https://github.com/blinkhash/blinkhash-utxo-lib/blob/master/test/integration/crypto.js#L115)
- [Generate a single-key stealth address](https://github.com/blinkhash/blinkhash-utxo-lib/blob/master/test/integration/stealth.js#L70:)
- [Generate a single-key stealth address (randomly)](https://github.com/blinkhash/blinkhash-utxo-lib/blob/master/test/integration/stealth.js#L89:)
- [Recover parent recipient.d, if a derived private key is leaked (and nonce was revealed)](https://github.com/blinkhash/blinkhash-utxo-lib/blob/master/test/integration/stealth.js#L105)
- [Generate a dual-key stealth address](https://github.com/blinkhash/blinkhash-utxo-lib/blob/master/test/integration/stealth.js#L122)
- [Generate a dual-key stealth address (randomly)](https://github.com/blinkhash/blinkhash-utxo-lib/blob/master/test/integration/stealth.js#L145)

If you have a use case that you feel could be listed here, please [ask for it](https://github.com/blinkhash/blinkhash-utxo-lib/issues/new)!

---

### Running Tests

``` bash
npm test
npm run-script coverage
```

---

### Complementing Libraries

- [BIP21](https://github.com/bitcoinjs/bip21) - A BIP21 compatible URL encoding utility library
- [BIP38](https://github.com/bitcoinjs/bip38) - Passphrase-protected private keys
- [BIP39](https://github.com/bitcoinjs/bip39) - Mnemonic generation for deterministic keys
- [BIP32-Utils](https://github.com/bitcoinjs/bip32-utils) - A set of utilities for working with BIP32
- [BIP66](https://github.com/bitcoinjs/bip66) - Strict DER signature decoding
- [BIP69](https://github.com/bitcoinjs/bip69) - Lexicographical Indexing of Transaction Inputs and Outputs
- [Base58](https://github.com/cryptocoinjs/bs58) - Base58 encoding/decoding
- [Base58 Check](https://github.com/bitcoinjs/bs58check) - Base58 check encoding/decoding
- [Bech32](https://github.com/bitcoinjs/bech32) - A BIP173 compliant Bech32 encoding library
- [coinselect](https://github.com/bitcoinjs/coinselect) - A fee-optimizing, transaction input selection module for bitcoinjs-lib.
- [merkle-lib](https://github.com/bitcoinjs/merkle-lib) - A performance conscious library for merkle root and tree calculations.
- [minimaldata](https://github.com/bitcoinjs/minimaldata) - A module to check bitcoin policy: SCRIPT_VERIFY_MINIMALDATA

---

### Donations

Maintaining this project has always been driven out of nothing more than a desire to give back to the mining community, however I always appreciate donations, especially if this repository helps you in any way.

- Bitcoin: 3EbrVYLxN5WeQmPpL6owo3A7rJELXecbbc
- Ethereum: 0xd3e3daED621d228244Fa89A3dd8AF07B52E72319
- Litecoin: MFWpARrSADAy3Qj79C4pSasS9F156QipwC
- ZCash: t1NSk8gyiou8TxWRZTVuUkfM5f9riopN58A

---

### License

Released under the MIT License. See https://opensource.org/licenses/MIT for more information

---

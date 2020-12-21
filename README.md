# Emoji wallet

Demo: [https://groestlcoin.org/emoji-seed/](https://groestlcoin.org/emoji-seed//)

Mnemonic seed with emojis instead of words. Evening fun project, without any real applications, just for fun.

You can generate a private key and show it as a sequence of emojis. This sequence has a checksum (like in electrum-grs, derived from hash, not from the wordlist) and you can actually use these private and public keys in any wallet.

Emoji seed can be used in electrum-grs directly:

![](electrum-grs.png)

# Example

## Emoji seed

A web page generates a random seed and represents it as a sequence of emojis:

😡🎧💆🕋🎌🏣🚪😆👦📻🕯💷🤝☁️

## Hex seed

All the emojis are unicode symbols, we can take a hash of this sequence and get the value. This hash should start with `01` to make sure there is no typo.

```
01665d55151280dc3a2b1545fd5ba0a2c735bdb3f78f0f93991a318a7ce1f7ac0c95ece0189f2b73987bd629d790eaf846af9a33e7d7261aff99fd304d839d04
```

Hash is calculated like in electrum-grs:

```
HMAC(key="Seed version", data="😡🎧💆🕋🎌🏣🚪😆👦📻🕯💷🤝☁️")
```

We can derive HD private and public keys from the hash:

## Master private key

```
xprv9s21ZrQH143K2yqyJAbtE6EYFhJdDGCYgeCPXPUnUh5VUvh5HbfCXGRy7CGmkNfD5QpVDamcYDXJg7AA68HF8jVHEYgSx4iJasNvfxYNUoW
```

## Master public key

```
xpub661MyMwAqRbcFTvSQC8tbEBGoj97civQ3s7zKmtQ32cUMj2Dq8yT54kSxSiUq3NL8JpgdTywygrFERKrBvJGjc4AgZ6GK3KfxMZs3MJKCvX
```

## Using it

With electrum-grs everything is pretty simple: create a new wallet and enter emoji sequence as a seed. In other wallets import master private key instead.

Emoji transactions:

[https://blockbook.groestlcoin.org/xpub/xpub661MyMwAqRbcFTvSQC8tbEBGoj97civQ3s7zKmtQ32cUMj2Dq8yT54kSxSiUq3NL8JpgdTywygrFERKrBvJGjc4AgZ6GK3KfxMZs3MJKCvX?tokens=derived](https://blockbook.groestlcoin.org/xpub/xpub661MyMwAqRbcFTvSQC8tbEBGoj97civQ3s7zKmtQ32cUMj2Dq8yT54kSxSiUq3NL8JpgdTywygrFERKrBvJGjc4AgZ6GK3KfxMZs3MJKCvX?tokens=derived)

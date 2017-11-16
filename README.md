# Emoji wallet

Mnemonic seed with emojis instead of words. Evening fun project, without any real applications, just for fun.

You can generate a private key and show it as a sequence of emojis. This sequence has a checksum (like in electrum, derived from hash, not from the wordlist) and you can actually use this private and public keys in any wallet.

You can do it offline - just download the files, go offline and open the `index.html` page in the browser.

# Example

## Emoji seed

From the html page I got the seed:

😩🍺⛅️🐝👨‍👩‍👧‍👦📎🚀🏣🏳️📱🍔🎯🌻🐔

## Hex seed

All the emojis are unicode symbols, we can take a hash of this sequence and get the value:

```
802651545c23ff7509b1173e9464bcffec979673a2f3a7d749c2ca72159a0c0cf723ab264a582fd2409ec7470260727c639bf4b5fdc61a95ffaaba875abd48cc
```

We do the following transformation:

```
HMAC(key="Seed version", data="😩🍺⛅️🐝👨‍👩‍👧‍👦📎🚀🏣🏳️📱🍔🎯🌻🐔")
```

This hash starts with "80" - it's a checksum. Generator produces only emoji strings whose hash starts with "80".

We can derive HD private and public keys from the hash:

## Master private key

```
xprv9s21ZrQH143K2zk94bnTtfWRzwHSpnayu16rF5KN5Mwugki5TuUe5K9yH4NVGgcZUB1oU1NnLGAs1GrC3wGg8uJMMZ5BoX12WBHRAyRLK1w
```

## Master public key

```
xpub661MyMwAqRbcFUpcAdKUFoTAYy7wEFJqGE2T3TiydhUtZZ3E1Sntd7UT8N7AKAmo5sU2p9i7imgDyCgpvdemraETj3VxAB2bAzaTd4iTjXp
```

## Using it

Now we can import this key to electrum or any other wallet and use. For real.

Emoji transactions:

[https://blockexplorer.com/address/14uTGGRpezuDutTfHhMnW1jfR3g9aWEqPZ](https://blockexplorer.com/address/14uTGGRpezuDutTfHhMnW1jfR3g9aWEqPZ)
"Cypherpunks write code." - Eric Hughes
==

Purpose: 
==
Despite the massive success of Bitcoin protocol, money privacy remains the unrealized priority of 
A Cypherpunk's Manifesto by Eric Hughes (https://nakamotoinstitute.org/static/docs/cypherpunk-manifesto.txt) published March 9, 1993; 
at least as per Alex Gladstein's viewpoint expressed in The Quest For Digital Cash published on October 13, 2021 (https://bitcoinmagazine.com/culture/bitcoin-adam-back-and-digital-cash).

Gladstein cites earlier works from David Chaum in 1992 concerning the digital age expressing that mankind is at a decision point, 
where “in one direction lies unprecedented scrutiny and control of people’s lives; 
in the other, secure parity between individuals and organizations. 
The shape of society in the next century,” he wrote, “may depend on which approach predominates.”

This project is to demonstrate, using a couple of builtin features of the new Chialisp programming language, 
that it's possible to short-range teleport, to "blink", value and thereby enhance money privacy,
making it more in line with the stated requirements of the original Cypherpunks and more like David Chaum's vision of secure parity.

Technique: 
==
Leveraging how if there is unassigned spent coin value in a chia spend bundle in excess of deficit value in one coin in the same bundle then the coin having deficit still successfully spends and maintains it's parent lineage to the next unspent coin on the chia blockchain. You can theoretically assign an unlimited amount of XCH value to the most humble coin lineage because as long as there is excess XCH value somewhere else in the same spend bundle the transaction will go through.
The other thing we are leveraging is how in chialisp wallet addresses are just encoded puzzle hashes and puzzle hashes are just compiled programming logic. Therefore when we ask another party to send value to a specific address we theoretically 100% control the programming logic of what happens next when that coin eventually gets spent, the sending party cannot be expected to bear any responsibility.

We enlist a faucet to take advantage of the latter point, to put a new coin on the blockchain Coin A, that when spent sends value in excess of it's own value to a newly created anonymous wallet address. Coin A  has deficit value. 
The deficit value of coin A must be the same value or less than Coin C which needs privacy and spends in the same spend bundle with unassigned value transfer. This means if there is no deficit value elsewhere in the spend bundle it would become fees. 

When Coin C's unassigned value spends there is no it's coinID lineage ends full stop right there. In other words, there is no parent_coin_info RPC call info anywhere on the chia blockchain.
The value of Coin C needing privacy has "blink mojo'd" somewhere, but nobody can determine where.
Blinking can be repeated as many times as necessary to accumulate doubt of where the value of Coin C resides at any given time on the blockchain.
This technique is verifiably successful as per the transactions demonstrated in the files herein; spendbundle files, audit files etc. 
I assert there is no proof that the deficit value that Coin A overcame did or did not come from the unassigned value of Coin C, 
or the unassigned value Coin B (which was spent in nearly the same way and simply present to create furhter doubt),
thereby privacy has been gained for Coin C which is our goal.

NOTE: blink_mojo technique used in these examples was of almost infinitely small value for exhibition purposes. It was done completely insecure and is error prone(AKA you will lose your money). It is designed to foster discussion.

There is an enhanced version of this technich called py-blink_mojo-secure(https://github.com/geraldneale/py-blink_mojo-secure) which uses aggregated signatures to secure and a python3 driver to automate nearly all of it on the testnet10 chia blockchain.

Please attempt to prove my assertion wrong by using the open source software here and explain what assumptions I have wrong with vigor and say why. I only really care about on-chain analysis. Mempool copies are centralized and are as worthless, in my opinion, as any other centralized money auditing system. 

![Alt text](blink_mojo-graphic.png?raw=true "Blink Mojo - Graph")

Notes used to complete this transaction:
==
Anonymous Wallet*: 0x1d4c24bff6bf87b6896f1efd15e9d2fe15e17f07252752c695d3261c1148d940
Known Wallet: 0x58bb585420abf3275685a71e2ea26637890881f6f469b20ab32a73a7db324521
*used nucle.io whom may harvest originating IP address

----------
CoinA(created via faucet.chia.net for anonymity):

	    "amount": 100,
            "parent_coin_info": "0xdd34c450a68dabe8851fca2b81ffdef4120a9465039f9c34e5feb059a97acd31",
            "puzzle_hash": "0x55cbce99411743ae478a938e5603f1f937ae0e52d9d73293e6dfe6b22a83a290"
	    
CoinB(created normally):

            "amount": 100,
            "parent_coin_info": "0x09be1fdbc68ab86fb6c681aa76687da685e0718352ba1edac4c71fbe34a5a639",
            "puzzle_hash": "0x8a3bf47feade69aefbad6e8219933c78f57ddb2c3d107de5403a0fc9848d813a"
	    
CoinC(created normally):

            "amount": 100,
            "parent_coin_info": "0x3e18caf8ff69bd958d5ac71baa5c1ddf003cfaffad6eae247d8930da7a6f8341",
            "puzzle_hash": "0x9dcf97a184f32623d11a73124ceb99a5709b083721e878a16d78f596718ba7b2"
	    
CoinD(created normally):

            "amount": 100,
            "parent_coin_info": "0x885bd91652625f1515ecf0083e3006e61340b45a1dd0884a10f11c85b46dbe14",
            "puzzle_hash": "0x9dcf97a184f32623d11a73124ceb99a5709b083721e878a16d78f596718ba7b2"

Credit:
==
Gerald Neale 2021-10-16

xch1hv4gj4vvdsyzn9hrhy9tn6hu6jwk82tyrs3t4r33468x642myjws8kh8xl

http://mojopuzzler.org


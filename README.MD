Purpose: 

Despite the massive success of Bitcoin protocol, money privacy remains the unrealized priority of 
A Cypherpunk's Manifesto by Eric Hughes (https://nakamotoinstitute.org/static/docs/cypherpunk-manifesto.txt) published March 9, 1993; 
at least as per Alex Gladstein's viewpoint expressed in The Quest For Digital Cash published on October 13, 2021 (https://bitcoinmagazine.com/culture/bitcoin-adam-back-and-digital-cash).

Gladstein cites earlier works from David Chaum in 1992 concerning the digital age expressing that mankind is at a decision point, 
where “in one direction lies unprecedented scrutiny and control of people’s lives; 
in the other, secure parity between individuals and organizations. 
The shape of society in the next century,” he wrote, “may depend on which approach predominates.”

This project is to demonstrate, using a couple of builtin features of the new Chialisp programming language, 
that it's possible to short-range "teleport"(blink) value and thereby enhance money privacy,
making it more in line with the stated requirements of the original Cypherpunks and more like David Chaum's vision of secure parity.

Technique: 

Leveraging how if there is unassigned coin value in a spend_bundle in excess of a deficit value in the same bundle then the coin having deficit successfully spends.
And how in chialisp, wallet addresses are also puzzle hashes, and puzzle hashes are also logic. 
We enlist a faucet to pay coin A to a newly created anonymous wallet address with logic to pay a higher amount than it is worth(has a deficit value). 
The deficit value of coin A is the same value as coin C which needs privacy. 
Coin C spends yet there is no trace of it's coinID as parent_coin_info anywhere.
The value of coin C has "blinked" somewhere, but nobody can determine where!
Blinking can be repeated as many times as necessary to accumulate excess doubt where the value of coin C resides at any given time on the blockchain.
This technique is verifiably successful as per the transaction demonstrated in the files herein. 
I assert there is no proof that the deficit value coin A overcame did or did not come from coin C, 
or coin B (which was spent in almost the way), or a combination of coin B and coin C;
thereby privacy has been gained for coin C by using intrinsic attributes of Chialisp in this way.
NOTE: Blink_mojo technique is an exhibition and therefore completely insecure and error prone(AKA you will lose your money). It is designed to foster discussion. 
There will be an enhanced version called blink_mojo-secure which uses aggregated signatures to secure in the nearfuture.
Please attempt to prove my assertion wrong with vigor and say why.

![Alt text](blink_mojo-graphic.png?raw=true "Blink Mojo - Graph")


Personal notes used to complete this transaction:
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

Gerald Neale 2021-10-16

xch1hv4gj4vvdsyzn9hrhy9tn6hu6jwk82tyrs3t4r33468x642myjws8kh8xl

http://mojopuzzler.org

http://mojopuzzler.org/pusht.php
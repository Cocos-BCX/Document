## Background
Currently, only common accounts can be registered through the mobile wallet provided on the official website, so some special account names may prompt errors.

## General Operation
The MainNet wallet is created directly, and it may prompt that some names cannot be created (currently the wallet client creates a account name freely, and creating some account names may not be supported). At this time, the technicians need to solve it according to the following process.

## Process
1. Create referer account and give it back to referer

Technician creates referer account and gives it back to referer

2. Download Wallet

Go to [https://github.com/Cocos-BCX/cocos-bcx-node-bin/tree/master/cli/mainnet/v1.1.2/linux](https://github.com/Cocos-BCX/cocos-bcx-node-bin/tree/master/cli/mainnet/v1.1.2/linux)

Download the available wallet binary cli_wallet.tar.gz and unzip it.

3. Run the wallet

Enter the wallet directory and run the command

./cli_wallet --chain-id '6057d856c398875cac2650fe33caef3d5f6b403d184c5154abbff526ec1143c4' -s wss: //api.cocosbcx.net

Connect to MainNet

4. Set up the wallet

After connecting to the MainNet and entering the wallet, type the following commands in order:

1.set_password 123456 enter

2.unlock 123456 enter

Note: The first time you run the wallet, the prompt is "new >>", and you can set password and unlock it following the above operation.

If it is not the first time to run the wallet, the prompt is "lock >>", you only need to perform the second step to unlock it.

5. Generate account public and private keys

Type command suggest_brain_key

The results are as follow

unlocked >>> suggest_brain_key

suggest_brain_key

{

  "brain_priv_key": "ZERO SCRAPER SLENT EYELET ABRADER YARETA DRYFOOT MUCUS UNVOTE ABKARI SPANCEL DUCAPE VERMIAN LAPSED LISTING GARTER",

  "wif_priv_key": "5JgVXvBuEfU45YeiAvb9SDFagdo7HfWqGzyUNdqBqC4fjFAWvy1",

  "address_info": "COCOSK5sL9FjY7NCQFMwqeuQ5JidYGXuMRupB1",

  "pub_key": "COCOS6NkW1bTtXKSfovFsvSwxDRSRrkoVvdx5zXDQvyZ5aypQpviGfp"

}

6. Register Account

Type the command in the wallet

1.register_account Name of the account to be created Account public key Account public key The referer account name of the account to be created true

 2.import_key The name of the account to be created The private key of the referer account to be created

## Appendix:
Official website binary wallet operation command:

[https://dev.cocosbcx.io/docs/22-cli_wallet](https://dev.cocosbcx.io/docs/22-cli_wallet)


# solana-token


How to Create a Solana Token?

First Steps:

1- install solana:
- sh -c "$(curl -sSfL https://release.solana.com/v1.9.5/install)"
* check if it's ok
- type in CLI -> solana

2- create a file for saveing pair-keys:
- mkdir solana-wallet
- solana-keygen new --outfile solana-wallet/my-keypair.json
* for checking pubkey type in CLI
- solana-keygen pubkey solana-wallet/my-keypair.json

3- working with wallet:
* airdrop yourself some token
- solana airdrop #(coin amount) <pubkey-address> --url https://api.devnet.solana.com
* check your balance
- solana balance <pubkey-address> --url https://api.devnet.solana.com

4- check your wallet online:
- go to this website -> explorer.solana.com
- change Network or Cluster from "Mainnet Beta" to "Devnet"
- copy your pubkey-address and paste it on search box

5- use wallet extension "Phontom":
- paste your private-key on and access to your wallet

Second Steps:

1- install dependencies:
* the token program written in RUST so you have to install rust
- curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
* install cargo
- sudo apt install cargo
- cargo install spl-token-cli
* if have some errors install these packages
- sudo apt install ruby-dev
- sudo apt install libudev-dev
- sudo apt install libssl-dev pkg-config
- sudo apt install build-essential -y

2- create a token:
- spl-token create-token
* if have error make sure that it can find the right path of my-keypair.json file
- solana config set --keypair <correct path>/my-keypair.json

3- create account for the token:
- spl-token create-account <token-identifier>

4- mint the token of the account with a specific amount:
- spl-token mint <token-identifier> <token-amount>

5- check the total supply of the token:
- spl-token supply <token-identifier>

6- check the balance of the token:
- spl-token balance <token-identifier>

7- transfer token:
- spl-token transfer --fund-recipient <token-identifier> <amount> <recipient-pubkey>

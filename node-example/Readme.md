# Run a ECROX Validator
## Setting up a node
1. Git clone https://github.com/ecroxchain/CoinNetwork.git

2. Copy source form node-example to root folder
```
cp -r CoinNetwork/node-example/ECROX  /root/
```
3. Create an Account

```
cd /root/ECROX
chmod +x openethereum
./openethereum account new --config nodes/validator/node.toml
```
Returned address like that 0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2

Copy result address to mode.toml
Ex:
```
...
[account]
unlock = ["0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2"]
password = ["password"]

[mining]
force_sealing = true
engine_signer = "0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2"
reseal_on_txs = "none"
...
```
4. Run the authority nodes
```
./openethereum --config ./nodes/validator/node.toml

```
5. Stake

    Stake

    To stake ECROX coin, all you should do is sending your ECROX coin to the ECROX Consensus contract address over the ECROX network from the validator address.
    The ECROX Consensus contract address: 0x2954AE5845B7Bb96e2147458926031a02D33C6E7
    The easiest way to do so, is to import your private key or key-store file to your favourite wallet (for example Metamask), switch network to ECROX and send the ECROX coin to the Consensus contract address.

    You can find your key-store (containing your private key) and the password for the created account in:
    /ECROX/nodes/validator/keys/ECROX/UTC--xxxx
    /ECROX/nodes/validator/node.pwd

6. Wait for 1 cycle (approximately 48 hours).

    Wait until the next cycle gets started.

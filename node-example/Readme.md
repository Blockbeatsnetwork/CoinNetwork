# Run a BDCC Validator
## Setting up a node
1. Git clone https://github.com/Blockbeatsnetwork/CoinNetwork.git

2. Copy source form node-example to root folder
```
cp -r CoinNetwork/node-example/BDCC  /root/
```
3. Create an Account

```
cd /root/BDCC
chmod +x openethereum
./openethereum account new --config nodes/validator/node.toml
```
Returned address like that 0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2

Copy result address to node.toml
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

    To stake BDCC coin, all you should do is sending your BDCC coin to the BDCC Consensus contract address over the BDCC network from the validator address.
    The BDCC Consensus contract address: 0xDF35349c9208eC877C4DD098C8127123a6A81A0E
    The easiest way to do so, is to import your private key or key-store file to your favourite wallet (for example Metamask), switch network to BDCC and send the BDCC coin to the Consensus contract address.

    You can find your key-store (containing your private key) and the password for the created account in:
    /BDCC/nodes/validator/keys/BDCC/UTC--xxxx
    /BDCC/nodes/validator/node.pwd

6. Wait for 1 cycle (approximately 48 hours).

    Wait until the next cycle gets started.

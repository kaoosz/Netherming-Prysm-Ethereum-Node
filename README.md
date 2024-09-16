# Netherming-Prysm-Ethereum-Node


create file ethereum with 2 folders inside name consensus and execution

cd consensus
curl https://raw.githubusercontent.com/prysmaticlabs/prysm/master/prysm.sh --output prysm.sh && chmod +x prysm.sh

./prysm.sh beacon-chain generate-auth-secret

move jwt.hex to ethereum folder

after go to execution and
wget https://nethdev.blob.core.windows.net/builds/nethermind-1.28.0-9c4816c2-linux-x64.zip

unzip

checklist
8545: TCP, for the JSON-RPC interface
8551: TCP, for the consensus client JSON-RPC interface
30303: TCP and UDP, for P2P networking

and run
./nethermind --config mainnet --JsonRpc.Enabled true --HealthChecks.Enabled true --HealthChecks.UIEnabled true --JsonRpc.JwtSecretFile=/home/ubuntu/ethereum/jwt.hex

and consensus folder run

./prysm.sh beacon-chain --execution-endpoint=http://localhost:8551 --mainnet --jwt-secret=/home/ubuntu/ethereum/jwt.hex --checkpoint-sync-url=https://beaconstate.info --genesis-beacon-api-url=https://beaconstate.info

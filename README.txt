Created a private ethereum network using go-ethereum (geth)
Make sure to have installed:
geth and ethereum



To run: 
1. go into bnode (bootnode) in a new terminal:
run this command:
bootnode -nodekey "./boot.key" -verbosity 7 -addr "127.0.0.1:30301"

2. go into node1 (this is going to be our miner) in a new terminal:
run this command:
geth --networkid 14333 --datadir "./data" --bootnodes enode://5da9810cca248dcc6aae4cf43d440d6441e41b8e5f158acf29d80134bba32f0d85f74d4af95a00e1b84823e970caba4a11694ee6db56b6ad16fcd0ceff495de7@127.0.0.1:0?discport=30301 --port 30303 --ipcdisable --syncmode full --http --allow-insecure-unlock --http.corsdomain "*" --http.port 8545 --unlock 0xd52C89eDC7727457D22B4B1129ecC3baF3e9B5B0 --password password.txt --mine console

3. go into node2 (participant in the private network) in a new terminal:
run this command:
geth --networkid 14333 --datadir "./data" --bootnodes enode://5da9810cca248dcc6aae4cf43d440d6441e41b8e5f158acf29d80134bba32f0d85f74d4af95a00e1b84823e970caba4a11694ee6db56b6ad16fcd0ceff495de7@127.0.0.1:0?discport=30301 --port 30304 --ipcdisable --syncmode full --http --allow-insecure-unlock --http.corsdomain "*" --http.port 8546 --unlock 0x3D3F400340d151C6325a762A5288921D679cD278 --password password.txt  console

We will require solidity and truffle once we attempt to deploy smart contracts
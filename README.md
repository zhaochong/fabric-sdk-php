# chengxin-fabric-sdk-php

mines_cc.go
go build

wallet_cc.go安装编译
mkdir -p $GOPATH/src/golang.org/x
cd $GOPATH/src/golang.org/x
git clone https://github.com/golang/crypto
go get github.com/vsergeev/btckeygenie

orderer

peer node start --peer-defaultchain=false --peer-chaincodedev=true 

peer channel create -o 127.0.0.1:7050 -c ch1 -f ch1.tx 

peer channel join -b ch1.block 

peer chaincode install -n mycc -v 0 -p github.com/hyperledger/fabric/examples/chaincode/go/chaincode_example02 

peer chaincode instantiate -n mycc -v 0 -c '{"Args":["init","a","100","b","200"]}' -o 127.0.0.1:7050 -C ch1 

peer chaincode invoke -n mycc -c '{"Args":["invoke","a","b","10"]}' -o 127.0.0.1:7050 -C ch1 

peer chaincode query -n mycc -c '{"Args":["query","a"]}' -o 127.0.0.1:7050 -C ch1 








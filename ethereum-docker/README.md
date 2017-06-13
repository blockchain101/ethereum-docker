# dockerfiles
docker files create blockchain101/fabric-geth:1.6.5 based on blockchain101/ubuntu16.04-dev:node6.9-python2.7-makegcc-git-cmake-go1.8
docker files create blockchain101/fabric-solc:0.4.11 based on blockchain101/ubuntu16.04-dev:node6.9-python2.7-makegcc-git-cmake-go1.8

# ethereum-testnet-docker
docker compose file to run docker containers using above blockchain101/fabric-geth:1.6.5 image
you can also use command like the following to compile a solidity contract:
docker run -it -v ~/ethcontract-compiled:/ethcontract-compiled -v ~/ethcontract:/ethcontract blockchain101/ethereum-solc:0.4.11 solc --bin --overwrite -o /ethcontract-compiled /ethcontract/greeter.sol
docker run -it -v ~/ethcontract-compiled:/ethcontract-compiled -v ~/ethcontract:/ethcontract blockchain101/ethereum-solc:0.4.11 solc --abi --overwrite -o /ethcontract-compiled /ethcontract/greeter.sol


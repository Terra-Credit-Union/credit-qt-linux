Install Ubuntu Server 18.04 on a VPS.

-Update your Ubuntu machine.

sudo apt-get update
sudo apt-get upgrade


-Install the required dependencies.

sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils python3 libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-test-dev libboost-thread-dev libboost-all-dev libboost-program-options-dev
sudo apt-get install libminiupnpc-dev libzmq3-dev libprotobuf-dev protobuf-compiler unzip software-properties-common


-Install Berkeley DB.

sudo add-apt-repository ppa:bitcoin/bitcoin
sudo apt-get update
sudo apt-get install libdb4.8-dev libdb4.8++-dev


-Download the daemon
wget "https://github.com/The-Terra-Foundation/credit-qt-linux/master/credit-qt-linux.tar.gz" -O credit-qt-linux.tar.gz


-Extract the tar files.

tar -xzvf credit-qt-linux.tar.gz


-Install the daemon and tools.

sudo mv creditd credit-cli credit-tx /usr/bin/


-Create the config file.

mkdir $HOME/.credit
nano $HOME/.credit/credit.conf


-Paste the following lines in credit.conf.

rpcuser=rpc_credit
rpcpassword=69c863e3356d3dae95df454a1
rpcallowip=127.0.0.1
listen=1
server=1
txindex=1
daemon=1


-Start your node with the following command.

creditd

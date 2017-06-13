environment settings specifications:
      #datadir of ethereum, in which cluster peers data will be put in it
      - CLUSTER_DATADIR=/ethcluster
      #ethereum network id, pls make sure all cluster's network id be identical
      - NETWORK_ID=779977
      #number of peer instances generated in the cluster, if RAM<3G pls set it smaller then 4 
      - CLUSTER_INSTANCE_NUM=4
      #if this cluster first peer instance be assigned as the boot node, there should be exactly one cluster set the property as Y in one network with the same network id
      - CLUSTER_BOOT_NODE=Y
      #if this cluster all peers be miner, if set Y all peers in the cluster will starting mining process
      - CLUSTER_MINING=N
      #the cluster id of the cluster peer instances, set from 0,1,2,3,...
      - CLUSTER_ID=0
      #the cluster share dir to put bootnode-ip and genesis file and ethash which are all the same for all peers in all clusters
      - CLUSTER_SHAREDIR=/ethcluster_share    
      #ip address specified for the cluster, be sure it's a ip address which is in the ipv4 docker network specified
      - CLUSTER_HOST_IP=172.16.238.10
      #################INIT_CONFIG SETTING###################
      # Y - recreate accounts, nodes and nodes data with/without genesis file based on GENESIS_FILE_ENABLED flag
      # N - no accounts, nodes and nodes data regeneration if not the first time initialization nodes and accounts
      # GENESIS_BLOCK_REGEN - no accounts regeneration, but nodes and nodes data will be regenerated with/without genesis file based on GENESIS_FILE_ENABLED flag
      - INIT_CONFIG=GENESIS_BLOCK_REGEN
      # all peers in the same cluster will using genesis file to create the genesis block
      - GENESIS_FILE_ENABLED=Y
      # a valid and accessible genesis file when GENESIS_FILE_ENABLED is Y, otherwise no genesis file used to generate the first genesis block
      - GENESIS_FILE=/ethcluster_share/genesis-779977.json
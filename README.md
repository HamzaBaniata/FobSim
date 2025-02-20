# FobSim
This project aims to introduce a reliable Fog-enhanced Blockchain simulation environment, namely FoBSim.

This environment shall facilitate easy simulation for different Fog-Blockchain integration scenarios.

FoBSim is implemented using Python 3.8, and it is adviced to be run on Linux or Windows OS.

This research work is a part of a paper that is published in the PeerJ-Computer Science journal. The open-access paper can be found at:

https://peerj.com/articles/cs-431/

DOI: 10.7717/peerj-cs.431

IMPORTANT NOTE: Published code should be considered copyrighted whether or not it includes an explicit copyright notice. This means that no one can distribute, reproduce, display, or create derivative works of the software without permission of the copyright owner.

# To run FoBSim using Docker:
1-	Update upt-get:

Sudo apt-get update 

2-	Install Docker Desktop from:

https://www.docker.com/get-started/

(for ubunto: sudo apt install docker.io)

3-	Check the version of the Docker installation:

docker -v

4-	Clone the FoBSim repository

5-	Go to the FoBSim Directory in the command line and build the docker image:

sudo docker build -t fobsim .

6-	Start the FoBSim container by typing:

sudo docker run -it fobsim

#To run FoBSim without Docker:
1- clone the FoBSim repository

2- run python3 main.py

3- you may be asked to install some libraries (python3-rsa, cryptography, etc.)

# The components implemented in FoBSim contains:
1- Fog layer implementation.

2- Blockchain network Implementation.

3- End-User layer implemetation.

4- Consensus algorithms.

5- Incentivization Mechanisms.

6- Parallel Mining.

7- Gossip Protocol.

8- Easy network topology and unique identities management.

# FoBSim allows the placement of the Blockchain network in either:
1- The Fog layer.

2- The End-User layer.

# The Blockchain in FoBSim provides the following services/immutable distributed ledgers:
1- Payment/Trading

2- Data management

3- Identity management

4- Computational Services through Smart Contracts

# The Blockchain in FoBSim allows the use of one of the following Consensus algorithms during each run:
1- Proof-of-Work (PoW)

2- Proof-of-Stake (PoS)

3- Proof-of-Authority (PoA)

4- NEW: Proof-of-Elapsed-Time (PoET)

5- NEW: delegated Proof-of-Stack (dPoS)

# Steps to running FoBSim simulation:
1- Install Git to your PC ((https://git-scm.com/book/en/v2/Getting-Started-Installing-Git))

2- Clone the FoBSim repo to your PC using Git and modify the code using some editor (e.g. PyCharm).

git clone https://github.com/sed-szeged/FobSim.git

3- Modify the 'Sim_parameters.json' either directly or on the command line (using e.g. vim or nano tools)

4- In the FoBSim root folder, run the command python3 main.py. (install any missing dependency your system is missing, which should be given as an error message)

# Steps to add a new consensus algorithm (proof-based):
0- You must be familiar with Python language.

1- in the 'new_consensus_module.py', there are two groups of functions: Modifiable and Non-Modifiable (declared by comments).

2- in the Modifiable part, follow the seven steps declared in the comments. Make sure to add instead of modify on the modifiable part. Thus, other code related to other consensus algorithms is not affected.

3- As an example, we added a 'dummy consensus algorithm' which clarifies the main parts that should be added for a new proof-based algorithm. You can perform the same steps. 

4- Additional functionalities can be added "if necessary" to any other module in the tool so that the proposed consensus algorithm works smoothly. For example, we added some conditional statements related to PoET to the 'build_block' method in the 'miner.py' file, and we added a 'PoET_server.py' (which includes only one method only) to forbid any confusions. However, we could simply add this method to the 'new_consensus_module.py'. Read the functions of all the available 5 consensus algorithms so that you get your self familiar of how a proof-based algorithm works.

5- run the FoBSim tool after modifying on the 'Sim_parameters.json' file as required by your simulation scenario (steps 3 and 4 above ^^)

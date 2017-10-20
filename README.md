
<img src="https://farm5.staticflickr.com/4486/37770438926_5d9ae5074a_o.png" width="775" height="142" alt="bluebandtitle">

[URL to this page](http://bit.ly/2yQxJpo) http://bit.ly/2yQxJpo 

Learn how to start writing Blockchain applications

# Housekeeping info:

### Wifi at Galavanize SSID/pass = g|Events / machinelearning
Your instructor: Lennart alf@us.ibm.com

# Agenda
~~~
6:00  Sign-in, mingle, food, welcome. Intro of Tom Eck, IBM CTO Industry Platforms
6:20: Introduction to IBM Blockchain and Hyperledger: 
6:30: Lennart: Introduction of the labs (Developer Journey). 
6:40: Coding starts.
      Lab 1: Bringing up the Hyperledger Fabric 
      Lab 2: Running your first application
      Lab 3: 
8:00: Coding ends.
      Where do we go from here?  
      Lab 2: 
      Lab 3:
8:30: Event ends   
~~~ 

<img src="https://farm5.staticflickr.com/4503/37148677233_71edc5a37b_o.png" width="1041" height="53" alt="blueband">

# Let's get started, introduction and documentation

**Assumption: you already know enough of Blockchain to want to start to write Blockchain apps.** 

<img src="https://farm5.staticflickr.com/4338/36822231841_bc13a7147a_z.jpg" width="640" height="164" alt="IBMBlockchain1">

[Blockchain for Dummies](https://public.dhe.ibm.com/common/ssi/ecm/xi/en/xim12354usen/XIM12354USEN.PDF)

October 2008 It all started with Satoshi Nakamoto and his paper [Bitcoin: A Peer-to-Peer Electronic Cash System](https://bitcoin.org/bitcoin.pdf) which addressed a key problem in electronic commerce:
~~~
A purely peer-to-peer version of electronic cash would allow online payments to be sent directly 
from one party to another without going through a financial institution. 

Digital signatures provide part of the solution, but the main benefits are lost if a trusted third party 
is still required to prevent double-spending.

We propose a solution to the double-spending problem using a peer-to-peer network.
~~~



(http://hyperledger-fabric.readthedocs.io/en/latest/samples.html)

Hyperledger, an open source collaborative effort to advance cross-industry blockchain technologies, 
is hosted by The Linux Foundation®. 

IBM provides blockchain solutions and services leveraging Hyperledger technologies, 
including Hyperledger Fabric and Hyperledger Composer.

## Hyperledger Composer source code on GitHub https://github.com/hyperledger/composer
Hyperledger Composer is an application development framework which simplifies and expedites the creation of Hyperledger fabric blockchain applications.

## Hyperledger Fabric source code on Github https://github.com/hyperledger/fabric

Hyperledger Fabric is a platform for distributed ledger solutions, underpinned by 
a modular architecture delivering high degrees of confidentiality, resiliency, 
flexibility and scalability. It is designed to support pluggable implementations 
of different components, and accommodate the complexity and intricacies that exist 
across the economic ecosystem.

## [The .BNA file](https://hyperledger.github.io/composer/reference/commands.html)
A Business Network Archive (BNA) file is exported by the Hyperledger Composer with the extension of .bna, and contains the definitions all the definitions for a Business Network. It is deployed in a Hyper Ledger Fabric. 
 is an application development framework which simplifies and 
expedites the creation of Hyperledger fabric blockchain applications.

<img src="https://farm5.staticflickr.com/4503/37148677233_71edc5a37b_o.png" width="1041" height="53" alt="blueband">

# Let the coding begin. Hands-on Workshop

## Pre-reqs: 
   http://hyperledger-fabric.readthedocs.io/en/latest/prereqs.html

## Lab 1: Let's bring up the Hyperledger Fabric!
Instructions below from this URL: 
* http://hyperledger-fabric.readthedocs.io/en/latest/build_network.html 
* http://hyperledger-fabric.readthedocs.io/en/latest/samples.html
* http://hyperledger-fabric.readthedocs.io/en/latest/getting_started.html
* http://hyperledger-fabric.readthedocs.io/en/latest/getting_started.html#install-prerequisites)
* http://hyperledger-fabric.readthedocs.io/en/latest/getting_started.html#install-binaries-and-docker-images
* http://hyperledger-fabric.readthedocs.io/en/latest/getting_started.html#hyperledger-fabric-samples
* http://hyperledger-fabric.readthedocs.io/en/latest/build_network.html
* http://hyperledger-fabric.readthedocs.io/en/latest/write_first_app.html

## Step 1
If necessary execute the following three commands to remove Docker instances.
   * docker kill $(docker ps -q)
   * docker rm $(docker ps -aq)
   * docker rmi $(docker images dev-* -q) 
## Step 2   
   * Instructions below come from the following URL: http://hyperledger-fabric.readthedocs.io/en/latest/samples.html  
    Execute the following commands:
   * git clone https://github.com/hyperledger/fabric-samples.git into a directory on your laptop
   * From that directory on your laptop (see above) invoke:
     curl -sSL https://goo.gl/Q3YRTi | bash   
   * export PATH=<path to download location>/bin:$PATH  
  
## Step 3 
   * Instructions below come from the following URL:  
      http://hyperledger-fabric.readthedocs.io/en/latest/build_network.html
   Bring up the Hyperledger Fabric: 
   * cd first-network
   * ./byfn.sh -m generate
   * ./byfn.sh -m up. //See full output from command on this link http://bit.ly/2yyTeIj
      * After checking the output, remember to run ./byfn.sh -m down.
   
 ## Step 4 (optional) Configurate your Hyperledger Fabric instance.  
 http://hyperledger-fabric.readthedocs.io/en/latest/build_network.html

# Lab 2: Let's run our first application in Hyperledger Fabric 
Source: http://hyperledger-fabric.readthedocs.io/en/latest/write_first_app.html

## Step 1 Remove not needed artifacts
    * docker rm -f $(docker ps -aq)
    * delete chaincode image: docker rmi dev-peer0.org1.example.com-fabcar-1.0
    
## Step 2 Navigate to a directory where you want the samples downloaded to issue these commands:
    * git clone https://github.com/hyperledger/fabric-samples.git
    * cd fabric-samples/fabcar
    * See what's inside the directory: ls
    * You should see the following: chaincode , invoke.js , network , package.json , query.js , startFabric.sh
    * Start the fabric: ./startFabric.sh
    * Install the SDK Node modules: npm install
    * cd fabcar
    * node query.js
   
  output;
   Arnes-MBP:fabcar arnelennartfrantzell$ node query.js
   Create a client and set the wallet location
   Set wallet path, and associate user  PeerAdmin  with application
   Check user is enrolled, and set a query URL in the network
   Make query
   Assigning transaction_id:  9367267e0e9c66cba821eb79500ffee6f004ced6f53bc01ddf280b00e2a8cb10
   returned from query
   Query result count =  1
Response is  [{"Key":"CAR0", "Record":{"colour":"blue","make":"Toyota","model":"Prius","owner":"Tomoko"}},{"Key":"CAR1",    "Record":{"colour":"red","make":"Ford","model":"Mustang","owner":"Brad"}},{"Key":"CAR2", "Record":{"colour":"green","make":"Hyundai","model":"Tucson","owner":"Jin Soo"}},{"Key":"CAR3", "Record":{"colour":"yellow","make":"Volkswagen","model":"Passat","owner":"Max"}},{"Key":"CAR4", "Record":{"colour":"black","make":"Tesla","model":"S","owner":"Adriana"}},{"Key":"CAR5", "Record":{"colour":"purple","make":"Peugeot","model":"205","owner":"Michel"}},{"Key":"CAR6", "Record":{"colour":"white","make":"Chery","model":"S22L","owner":"Aarav"}},{"Key":"CAR7", "Record":{"colour":"violet","make":"Fiat","model":"Punto","owner":"Pari"}},{"Key":"CAR8", "Record":{"colour":"indigo","make":"Tata","model":"Nano","owner":"Valeria"}},{"Key":"CAR9", "Record":{"colour":"brown","make":"Holden","model":"Barina","owner":"Shotaro"}}]
    
## Step 3 Now let's add a new car and update the Blockchain.
* Open the Invoke.js program, locate the request function and change the args section like this, 
using your own name and args:

var request = {
        targets: targets,
        chaincodeId: options.chaincode_id,
        fcn: 'createCar',
        args: ['CAR10', 'Chevy', 'Volt', 'Red', 'Lennart'],
        chainId: options.channel_id,
        txId: tx_id


Save the file and invoke it like this: node invoke.js. You should see the new car appear, stored in the blockchain.

# Lab 3: Let's write an app with the Hyperledger Composer!
<img src="https://farm5.staticflickr.com/4445/37751618086_06402e4b2e_b.jpg" width="766" height="532" alt="Composer Playground">
[Playground Tutorial](https://hyperledger.github.io/composer/tutorials/playground-guide.html)

## Run Hyperledger Composer in your browser https://hyperledger.github.io/composer/

## [Composer Playground and the Perishable Goods Network](https://github.com/LennartFr/Blockchain-at-Galvanize/blob/master/Hyperledger%20Composer%20Perishable%20Food%20Network.pdf)

## Deploy bna file on hyperledger fabric
https://hyperledger.github.io/composer/business-network/bnd-deploy.html

Arnes-MBP:bnafile arnelennartfrantzell$ composer network deploy -p hlfv1 -a my-basic-sample.bna -i PeerAdmin -s randomString -A admin -S
Deploying business network from archive: my-basic-sample.bna
Business network definition:
	Identifier: my-basic-sample@0.1.10
	Description: The Composer basic sample network

✔ Deploying business network definition. This may take a minute...


Command succeeded

## ping application on hyperledger composer

Arnes-MBP:bnafile arnelennartfrantzell$ composer network ping -n my-basic-sample -p hlfv1 -i admin -s adminpw
The connection to the network was successfully tested: my-basic-sample
	version: 0.14.1
	participant: org.hyperledger.composer.system.NetworkAdmin#admin

Command succeeded

https://hyperledger.github.io/composer/reference/commands.html


# Lab 4: Decentralized Energy with Hyperledger composer 
https://developer.ibm.com/code/journey/decentralized-energy-hyperledger-composer/

This Developer Journey describes a complete blockchain application with a decentralized energy network with a working user interface.
It can be completed in around half an hour.

<img src="https://farm5.staticflickr.com/4503/37148677233_71edc5a37b_o.png" width="1041" height="53" alt="blueband">

# Where do we go from here?

IBM has a series of Developer Journeys covering various aspects of Blockchain, with more being added regularly. 

* https://developer.ibm.com/code/journey/build-your-first-blockchain-application/
* https://developer.ibm.com/code/journey/create-and-execute-blockchain-smart-contracts/
* https://developer.ibm.com/code/journey/implement-fda-food-supplier-verification-program-on-hyperledger-composer/
* https://developer.ibm.com/code/journey/build-a-blockchain-network/
* https://developer.ibm.com/code/journey/decentralized-energy-hyperledger-composer/
* https://developer.ibm.com/code/journey/run-blockchain-technology-on-a-linux-mainframe/
* https://developer.ibm.com/code/journey/create-a-to-do-list-app-using-blockchain/
* https://developer.ibm.com/code/journey/deploy-an-asset-transfer-app-using-blockchain/



# Notes

* curl -sSL https://hyperledger.github.io/composer/install-hlfv1.sh | bash
* composer network deploy -a basic-sample-2.bna -p hlfv1 -i PeerAdmin -s randomString -A admin -S
* composer network ping -n basic-sample-2 -p hlfv1 -i admin -s adminpw
* https://developer.ibm.com/tv/hyperledger-composer-build-execute-smart-contract/ 


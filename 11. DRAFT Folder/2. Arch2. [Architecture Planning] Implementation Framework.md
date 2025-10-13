# Implementation Framework

* Below are the detailed steps to establish the architecture for three different Splunk environments: a stand-alone setup, a distributed non-clustered configuration, and a distributed clustered architecture.

## For Stand-alone Environment
1) Install Splunk Enterprise on one instance
2) Configure the Splunk Enterprise license either on its own server or as part of the Search Head / Deployer Server
3) Configure the Splunk instance's receiving port (port 9997)
4) Configure for firewall to allow receiving data from port (port 9997)
5) Install universal forwarders on the machines hosting your data sources, and configure the forwarders to send data to the Splunk Enterprise instance.
6) Enable data inputs in forwarders from data sources.

## For Distributed Non-Clustered Environment
1) Install Splunk Enterprise instances for indexers & search head.
2) On Search Head - Configure Indexers as search peers.
3) Configure the Splunk Enterprise license either on its own server or as part of the Search Head / Deployer Server
4) On each Indexer, configure the receiving port.
5) Install Universal Forwarders & configure them to send data.
   - Option 1) Install one-by-one or simultaneously across many servers
   - Option 2) Install and then configure them later
   - Option 3) Install and confgiure forwarders at the same time
   **Configure:** Manually or use deploymen tserver
7) Configure the inputs to the forwarders, so that data begins to enter the system from data sources.

## For Distributed Clustered-Search Head (Non-clustered Indexers) Environment
1) Install and deploy the Search Head Cluster / Deployer
2) Install the instances that you plan tu use as Indexers
3) Connect the Search Head Cluster to the Non-Clustered Indexers
4) Configure the Splunk Enterprise license either on its own server or as part of the Search Head / Deployer Server
5) On each new indexer, configure the receiving port (port 9997)
6) Install Universal Forwarders on the machiens with data
7) Configure the forwarders to send data to the Indexers.
8) Configure the inputs to the forwarders, so that data begins to enter the system from the data sources.

## For Distributed Clustered (both Search Head and Indexers) Environment
1) Deploy the Indexer Cluster
2) Deploy the Search Head Cluster
3) Configure the Splunk Enterprise license either on its own server or as part of the Search Head / Deployer Server
4) On each new Indexer, configure the receiving port (port 9997)
5) Install Universal Forwarders on the machines hosting your data sources.
6) Connect the peer nodes to the forwarders.
7) Configure the inputs to the forwarders, so that data begins to enter the system.

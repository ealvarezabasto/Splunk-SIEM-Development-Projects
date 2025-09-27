# Implementation Framework

* Here are the detailed steps to establish the architecture for three different Splunk environments: a stand-alone setup, a distributed non-clustered configuration, and a distributed clustered architecture. Each environment has unique requirements and considerations that must be addressed to ensure optimal performance and scalability.

## For Stand-alone Environment
1) Install Splunk Enterprise on one instance
2) Configure the Splunk Enterprise license
3) Configure the Splunk instance's receiving port (port 9997)
4) Configure for firewall to allow receiving data from port (port 9997)
5) Install universal forwarders on the machines hosting your data sources, and configure the forwarders to send data to the Splunk Enterprise instance.
6) Enable data inuts in forwarders.

## For Distributed Non-Clustered Environment
1) Install Splunk Enterprise instances for indexers & search head.
2) On Search Head - Configure Indexers as search peers.
3) Configure the Splunk Enterprise license
4) On each Indexer, configure the receiving port.
5) Install Universal Forwarders & configure them to send data.
   - Install one-by-one or simultaneously across many servers
   - Install and then configure them later
   - Install and confgiure forwarders at the same time
   **Configure:** Manually or use deploymen tserver
7) Configure the inputs to the forwarders, so that data begins to enter the system.

# Setup Monitoring Console

* Monitoring Console collects the details from all components to check health status. 

## Create a Service Credentials in all Splunk Servers

### Create a Service Credentials for the Cluster Manager

* Login to **Cluster Manager** Server
* Go to ***Settings*** > Click on ***Users***

  <img width="761" height="593" alt="image" src="https://github.com/user-attachments/assets/caa6c7e9-a438-4a04-b2f6-d061d108a3bc" />

* Select ***New User***

  <img width="816" height="295" alt="image" src="https://github.com/user-attachments/assets/3a2575d3-3206-4d19-854b-38348527dc3e" />

* Enter the Name >> Set Password >> Confirm your password >> Assign role (admin) >> Click ***save***

  <img width="793" height="275" alt="image" src="https://github.com/user-attachments/assets/f42c5b7a-f779-43dc-9d00-172186882c23" />
  <img width="785" height="765" alt="image" src="https://github.com/user-attachments/assets/d8c74b67-acf4-4015-9879-c69de28cb99f" />

* New user will be created as shown below

  <img width="793" height="303" alt="image" src="https://github.com/user-attachments/assets/32a773ad-a118-45ff-8586-5bfb1bbbb7b3" />

### Create a Service Credentials for all other components

* Repeat the above steps in all other Splunk servers such as Indexer 1, Indexer 2, Indexer 3, Deployer, Search Head 1, Search Head 2, Search Head 3, License Manager, Deployment Server.

## Connect Splunk Components with Monitoring Console

### Connect Indexer 1 Server with Monitoring Console

* Login to **Monitoring Console** Server

* Go to ***Settings*** > ***Distributed Search***

  <img width="648" height="562" alt="image" src="https://github.com/user-attachments/assets/9311d712-5a16-43b5-970e-032a991b47e7" />

* Select ***Search Peers***

  <img width="812" height="287" alt="image" src="https://github.com/user-attachments/assets/6f990c50-579e-4aa0-a0e3-49e1beb3de3a" />

* Select ***New Search Peer*** > click on ***New Search Peer***

* Enter Peer URL (Cluster Manager private IP address:mgmt port) >> Add username >> Password >> Confirm password  >> select ***Save***

  <img width="807" height="546" alt="image" src="https://github.com/user-attachments/assets/8440277f-5cc2-4ec9-bff4-4e091f1027e3" />
  
* The Indexer 1 Server Cluster Manager is successfully connected with the monitoring console

  <img width="809" height="338" alt="image" src="https://github.com/user-attachments/assets/55d9a2d9-83ba-453e-afe1-5be01a8ea8d0" />

### Connect the rest of the components to the Monitoring Console

* Repeat the same process for Indexer 2, Indexer 3, Deployer, Search Head 1, Search Head 2, Search Head 3, License Manager.

**Note** No need to link Intermediate Forwarder to the Monitoring Console as the Monitoring Console is being connected to the Cluster Master.

## Edit Server Roles

* Login to **Monitoring Console** Server
  
* Select ***Settings*** > ***Monitoring Console***
  
  <img width="1211" height="656" alt="image" src="https://github.com/user-attachments/assets/64ea20cb-4a77-446e-91d1-642415655be2" />

* Select ***Settings*** > ***General Setup***

  <img width="894" height="290" alt="image" src="https://github.com/user-attachments/assets/9fa13a75-f5bf-4282-b8a4-fca78b6fa539" />

* Select ***Distributed Mode***

  <img width="1869" height="379" alt="image" src="https://github.com/user-attachments/assets/7a8cc773-334d-4e7e-b576-753d9056ef6f" />

* Click "Continue"

  <img width="561" height="349" alt="image" src="https://github.com/user-attachments/assets/ab4b592f-e9d2-4089-97e9-d88b28f4b08e" />

* Edit all server roles (Cluster Manager, indexer 1, indexer 2, indexer 3, deployer, search head1, search head2, search head3, License Manager, Deployment Server). Refer to the below picture to set roles depending on the Server

  <img width="1883" height="315" alt="image" src="https://github.com/user-attachments/assets/a267bfa9-1236-441f-802a-c4d5fd082267" />


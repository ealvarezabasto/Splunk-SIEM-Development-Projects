# Setup Monitoring Console

* Monitoring Console collects the details from all components to check health status. 

## Create a Service Credentials in all Splunk Servers

### Create a Service Credentials for the Cluster Manager

* Access **Cluster Manager** Server
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

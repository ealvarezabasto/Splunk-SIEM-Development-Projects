# Automation

## Option 1: Configuration Management Tools
* Doing the process described in [Section 4.1](https://github.com/ealvarezabasto/Splunk-SIEM-Development-Projects/blob/main/4.%20Universal%20Forwarder/4.1%20(In%20Linux)%20Install%20Universal%20Forwarder%20in%20Server.md) is tideous if having to send data from multiple servers unto Splunk instance. In order to not have to take these manual steps, there are configuration managements tools (e.g., Ansible) that can automate this proccess.
* What you do is add the below commands (that were manually used in the above steps) into the Ansible playbook for it to run automatically in those servers.

  **./splunk add monitor /var/log**
  **./splunk add forward-server 172.17.0.2:9997**

## Option 2: Splunk Forwarder Management
* Connect all forwarders to central Splunk Forwarder Management
* Splunk Forwarder Management would be configured for the following use-case examples:
  * Any server which belongs to subnet 192.168.10.0/24 network should have only /var/log/scure file to be monitored.
  * Any server which belongs to subnet 10.77.0.0/20 should have /var/log/secure and /var/log/audit directory to be monitored.
  * If server hostname starts with win-, then integrate it to send all the windows events and AD logs.

  ![image](https://github.com/user-attachments/assets/01c371db-4c6b-4704-a062-0d418b619c19)

# Forwarder Management vs. Deployment Server vs. Deployment App vs. Server Class
* **Deployment Server:** Primarily used to manage and deploy configurations and apps to multiple Splunk instances, particularly forwarders. Ideal for organizations with a large number of forwarders that need to be managed centrally, ensuring that all forwarders have the same configurations and apps. Ideal for organizations with a large number of forwarders that need to be managed centrally, ensuring that all forwarders have the same configurations and apps.
* **[UI] Splunk Forwarder Management:** GUI built on top of deployement Server that provides an easy way to configure the deployemnt server and monitor the staus of deployment updates. Forwarder Management is a feature within Splunk that focuses on monitoring and managing the status and health of Splunk forwarders. It provides visibility into the performance and status of forwarders, including their connectivity, data transmission rates, and any issues that may arise. It helps in troubleshooting and ensuring that data is being forwarded correctly.
* **Deployment App:** A set of content (e.g., configuraiton files) maintained by deployment server and pushed to the deployment clients belong to a specific server class. **Example:** 1 Deployment appp has inputs.conf which monitors for /var/log/secure and /var/log/aduit. This deployment app is associated with "Linux" server class.
* **server class:** group that contains multiple deployment apps
  
# Forwarder Management / Deployment Server / Deployment App

**Note:** The forwarder management UI distributes deployment apps to Splunk clients.

* Within Command Line for Splunk Instance, type **/opt/splunk/etc ls -l** and find 'deployment-apps'

* type **cp -R app/sample_app/ deployemnt-apps** to copy sample_app to deployment-apps. Type **/opt/splunk/bin/splunk restart** to restart Splunk instance.

  ![image](https://github.com/user-attachments/assets/14bb338a-3583-46cb-b98f-f3c1096c4614)

* Within Splunk ES, find 'sample_app' within Splunk FOrwarder Management GUI.

  ![image](https://github.com/user-attachments/assets/993a88a7-f701-4450-834f-45e7b9496b1d)


  ![image](https://github.com/user-attachments/assets/24ef5652-68d1-4503-acd1-94117708be0b)

* Click Settings > Forwarder Management. You can see ***sample_app*** that is the deployment app.

  ![image](https://github.com/user-attachments/assets/676e558d-64e0-410f-93b9-189a0534ccf1)

# Server Class

* Within 'Forwarder Management' > 'Group / Server Classes' tab ? + 'new Server Class'

  ![image](https://github.com/user-attachments/assets/c276ea9e-e406-4e03-8e05-8b7b0accf4b4)

* Name new server class

  ![image](https://github.com/user-attachments/assets/3020d34e-9cfa-4551-93f0-dfd5ff8867f9)

* Within recently created server class, select on 'edit configurations'.

  ![image](https://github.com/user-attachments/assets/7d5e23eb-1328-49cf-aa21-ce0e54c57259)

* Add * to 'Include'

  ![image](https://github.com/user-attachments/assets/a43418ff-b6d5-4d9f-863c-b26ecfa4aec9)

* Within recently created server class, select on Configurations tab > 'edit configurations'.

  ![image](https://github.com/user-attachments/assets/9106b901-a69f-48bc-8b03-745a66cef2d5)

* add the sample_app and select 'Save'

  ![image](https://github.com/user-attachments/assets/2b9a8794-5c9f-4e23-9b9f-8c49aded8d3c)

* Now we have a new server class (linux_server' and new deployement app that is assocaited with the server class.
* sample_app is associated with server class **linux_server** that is associated with all clients.

  ![image](https://github.com/user-attachments/assets/36a5c36c-cad7-48ff-a090-75b9f6f7baf7)

  

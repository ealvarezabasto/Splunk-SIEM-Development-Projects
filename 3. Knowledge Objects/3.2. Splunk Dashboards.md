# Splunk Dashboards

**Description:** A dashboard should contain more than one panel.

## 1. Classic Dashboards
### 1.1 Add Panel
* Within "Searching & Reporting" app > select "Dashboards" tab > "New Dashboard"
  ![image](https://github.com/user-attachments/assets/657ae488-20c1-437c-b23f-026803519c84)

* Return to "Searching & Reporting" app > type **sourcetype="access_combined"|top categoryId** > select 'Visualization' > Save As: Existing Dashboard.
  ![image](https://github.com/user-attachments/assets/e970b47a-fa79-4f5b-9b14-54087587819c)

* Enter relevant information
  ![image](https://github.com/user-attachments/assets/8c8737dd-bfcd-49b4-bfcb-3b5e8eeac030)

* This visual is to see what are the top categories for access_combined

* Return to "Searching & Reporting" app > type **sourcetype="access_combined"|top categoryId**. This is see how many requests based on client ip have appeared.

  ![image](https://github.com/user-attachments/assets/4ac96332-7ff5-42c3-8f2e-55cec33609dc)

* Again, save visual to existing dashboard by clicking on 'Save As' > and inputing information

   ![image](https://github.com/user-attachments/assets/c920fcc3-5238-4683-9f58-f43e12db9855)

* end product

  ![image](https://github.com/user-attachments/assets/ecf6eae3-acd6-4056-9bd0-c20cec27c429)

### 1.2 Add Input

#### 1.2.1 Time Picker

* Within Existing Dashboard, select "Add Input" > "Time Picker". This will display the Time Range Picker to change the period of time. 
  
  ![image](https://github.com/user-attachments/assets/aff991a3-e80d-4556-9cd3-41df17f76487)

* To connect the panels to the 'Time Picker' input, go to 'Edit pencil' > 'Time' > update name for 'Token' (e.g., Timing)

  ![image](https://github.com/user-attachments/assets/8f40c07f-1b78-4c95-bb73-464e1621388d)

  ![image](https://github.com/user-attachments/assets/e176ce98-7f9e-432e-89be-0b62d525695c)

* Next, go to 'Edit Search' on your panel > Time Range = Shared Time Picker (Timing) <-- Token that was previously created

  ![image](https://github.com/user-attachments/assets/b13be756-05e5-4046-8f30-a78d51e8bb2b)

* After taking this step for both panels, screen should look like below:

  ![image](https://github.com/user-attachments/assets/06c2870d-fd50-4c0e-b9d5-7f92ee44d1bf)

* Refresh page in order for dashboard to re-appear

  ![image](https://github.com/user-attachments/assets/37745918-92da-4082-8821-44467c0ed314)

#### 1.2.2 Submit

* Select 'Add Input' > 'Submit' > click 'Save'
  
  ![image](https://github.com/user-attachments/assets/e92c45fa-86fc-434c-8a0f-d5ab340dea89)

* Final Output

  ![image](https://github.com/user-attachments/assets/2737abf7-c1b8-49e6-8af1-f568abf79c52)

#### 1.2.3 Submit

* Within 'Search & Reporting app', type SPL: **sourcetype=linux_secure |  stats count by src, user** > Save As: Existing Dashboard

  ![image](https://github.com/user-attachments/assets/570337be-a29f-4a80-965c-de29ae6784cf)

* Save Statistics Table to our existing dashboard

  ![image](https://github.com/user-attachments/assets/d6000bc5-1fbb-4b09-93e4-08a9e5daea04)

* Within 'Search & Reporting app', type SPL: **sourcetype=linux_secure |  stats count by src, user** > Save As: Existing Dashboard

#### 1.2.4 Text

* Select '+ Add Input' > 'Text'

  ![image](https://github.com/user-attachments/assets/0a2863a1-dc80-4f2a-b38f-75afadc6b8a7)

* Select 'edit pencil' > enter relevant information

  ![image](https://github.com/user-attachments/assets/f2fb6ac9-2732-4b21-84b7-01226cb90d74)

* To connect the panels to the 'Secure Dynamic Field' input, go to 'Search' for bottom statistics panel

  ![image](https://github.com/user-attachments/assets/3a776564-c561-4005-85e2-b3474a1fa847)

* add **$linuxsecure$** at the end of the search string

  ![image](https://github.com/user-attachments/assets/6c51156e-3928-44e9-acae-01a37c0e9ad9)

* Now if I search for 'src_port',field is added to the Linux Secure Logs table as an additional column

  ![image](https://github.com/user-attachments/assets/f2768d6d-a9c6-448f-a131-a371757dc792)

* If I search for 'sshd_protocol', field is added to the Linux Secure Logs table as an additional column

  ![image](https://github.com/user-attachments/assets/1910ed49-06cb-48c3-8f33-e39e42396e85)

#### 1.2.5 Dropdown

* Select '+ Add Input' > 'Dropdown'

  ![image](https://github.com/user-attachments/assets/8b891314-18a6-43d1-be86-13ce021c51e3)

* Fill relevant information
  ![image](https://github.com/user-attachments/assets/0e8f1a34-4f19-4732-b830-9aec584c2d6f)

* By scrolling down, Name = updated name you want the dropdown to display; Value = actual name of the field

  ![image](https://github.com/user-attachments/assets/8b0f33d2-449f-4360-a2e1-c2b81120fb73)

* To connect the panel to the 'Dropdwon' input, go to 'Search' for bottom statistics panel

  ![image](https://github.com/user-attachments/assets/1947b97b-bf24-4052-be16-9ff85d257962)

* Now if I search for 'SSHD Protocol' in the dropdown,field is added to the Linux Secure Logs table as an additional column

  <img width="947" alt="image" src="https://github.com/user-attachments/assets/f7abb7c0-b2b7-45c0-ab9b-989db0426c85" />

* If I search for 'process Detail', field is added to the Linux Secure Logs table as an additional column

  ![image](https://github.com/user-attachments/assets/616ece8f-18a6-4076-b80d-0d54bbd36f9c)

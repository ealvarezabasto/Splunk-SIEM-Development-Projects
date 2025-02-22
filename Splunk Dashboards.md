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

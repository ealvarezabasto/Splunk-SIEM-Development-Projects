# Creating Data Models

## Use Case 1
* Select 'Settings' > 'Data models'
  ![image](https://github.com/user-attachments/assets/26931abb-7af1-4104-b27d-20cd2342f136)

* Select 'New Data Model'

  ![image](https://github.com/user-attachments/assets/cf80eb4b-0230-49e9-95b2-ac390b5f7bd6)

* Add details to 'New Data Model' > select 'Create'

  ![image](https://github.com/user-attachments/assets/9031ece4-8f4c-430d-af00-50c29de3b50c)

### Ingest Authentication Log Data in Splunk ES

* Select 'Settings' > 'Add Data'

  ![image](https://github.com/user-attachments/assets/52e4a79a-67bd-423a-bce9-9d3f8e1f28cc)

* Add 'secure.log' file and select 'Next'

  ![image](https://github.com/user-attachments/assets/b903318d-a59b-4245-8aab-bfb3e1801234)

* Choose Source type as ***linux_secure*** and click 'Next'.

  ![image](https://github.com/user-attachments/assets/a34c025a-c822-47e5-ac15-deabaa85ad3e)

* Select "Create a new index"

  ![image](https://github.com/user-attachments/assets/c8c06af8-9be4-4980-b785-7029774a47e9)

* Create a new index called **authentication** and select 'Review' > select 'Submit'

  ![image](https://github.com/user-attachments/assets/f40b1a21-d61e-4533-bb1c-e921eff0d680)

* Authentication logs from linux have successfully been ingested.

  ![image](https://github.com/user-attachments/assets/36221e7c-9046-46bc-b3bf-1385e959bfc4)

### Continue creating Data Model

#### Root Event
* Return to Data Model and select 'Add Dataset' > 'Root Event'
  
  ![image](https://github.com/user-attachments/assets/44aaa2a2-c6e1-470d-9de3-7f0032674f7c)

* Name dataset as 'Linux' and constrating will be index="authentication" as you only want to retrieve the authentication logs previously ingested.

  ![image](https://github.com/user-attachments/assets/b4a0efa0-816b-4634-b505-73bd79f87b27)

* Select 'Add Field' > 'Auto-Extracted'

  ![image](https://github.com/user-attachments/assets/71d212f7-ddfd-4692-9c05-9efc855dc238)

* You're looking to extract all fields from index="authentication" > select 'Save'

  ![image](https://github.com/user-attachments/assets/43a6b407-e4dd-4880-bc3b-3510256a7785)

#### Child 1
* Select 'Add Dataset' > 'Child'

  ![image](https://github.com/user-attachments/assets/f3356854-62f7-49e9-92f8-a4b17e8d76ed)

* Within **Additional Constraints**, add 'Failed' as you're looking only for the 'failed' keyword within your list of events > Select 'Save'

  ![image](https://github.com/user-attachments/assets/d136eb78-58a0-4862-aaae-88c6bbb60602)

#### Child 2
* Select 'Add Dataset' > 'Child'

  ![image](https://github.com/user-attachments/assets/f3356854-62f7-49e9-92f8-a4b17e8d76ed)

* Within **Additional Constraints**, add 'session opened' as you're looking only for the 'successful logins' within your list of events > Select 'Save'

  ![image](https://github.com/user-attachments/assets/be696edf-2e80-48da-baa8-28e4e5c9c0d8)

#### Child 3
* Select 'Add Dataset' > 'Child'

  ![image](https://github.com/user-attachments/assets/f3356854-62f7-49e9-92f8-a4b17e8d76ed)

* Within **Additional Constraints**, add 'sudo' as you're looking only for those who have logged in an a user but use the 'sudo' command towards the root to become admins. > Select 'Save'

  ![image](https://github.com/user-attachments/assets/f3f041f4-4e89-42d5-946f-df74fd02b556)

### Final Result

  <img width="144" alt="image" src="https://github.com/user-attachments/assets/20c7a5e1-2105-447c-a7ee-ee29ae336b55" />

## Pivot
### Use Case 1: Creating a table
* Select 'Pivot' in the top right corner.

  ![image](https://github.com/user-attachments/assets/86d6953a-92a0-4be5-858c-b49e558caf4f)

* Select 'BadVectors'

  ![image](https://github.com/user-attachments/assets/b5804882-d62f-4e63-b5c4-2ea56319702e)

* Select 'Split Rows +' > select 'src' > select 'Add to Table'

  ![image](https://github.com/user-attachments/assets/2678d059-ce8c-46e2-bae9-95fce785bc1d)

* Table displays Column 1 -'src' (ip addresses) and Column 2 - Count of BadVectors

  ![image](https://github.com/user-attachments/assets/e9f62d58-638e-4749-b53a-fbc8e2c88631)

### Use Case 2: Creating a Visual
* Countries for which the IP Addresses are associated with.

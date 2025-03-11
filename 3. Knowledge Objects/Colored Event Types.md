# Colored Event Types

**Description:** Associate color to events depending on the various factors. Coloring is based on event type.

## Use Case 1: Coloring events based on status code

* Search for **sourcetype="access_combined" |  stats count by status**

  ![image](https://github.com/user-attachments/assets/4f3c6985-dae3-4602-9d66-2a7fc73bebc5)

* Search for **sourcetype="access_combined" status=200** > Save As: Event Type

  ![image](https://github.com/user-attachments/assets/9e9742ff-4f55-4c40-8d54-984f79661ab3)

* Now all events that have status = 200 will appear as green

  <img width="946" alt="image" src="https://github.com/user-attachments/assets/1380c60b-f0cb-4cb6-af18-a902c067d67e" />

  ![image](https://github.com/user-attachments/assets/05b2e6fa-6c54-4030-b418-a5cdb6f775f2)

* Search for **sourcetype="access_combined" status=408** > Save As: Event Type

  ![image](https://github.com/user-attachments/assets/795ac45b-d80d-4fc8-938f-08ef965fa01b)

* Add Color to be orange for **status_408** event type

 ![image](https://github.com/user-attachments/assets/acd80359-ca5b-448c-b884-d9a6e6b1f06e)

* Now all events that have status = 408 will appear as orange

  ![image](https://github.com/user-attachments/assets/55e817a0-a8bc-475f-9283-3a274f4ab298)

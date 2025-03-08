## Help with Regex using https://regex101.com/

# Practice 1 Basic Regex: \w - Any word (A-Z, a-z,0-9)

## \w
* Captures every word of the phrase
  ![image](https://github.com/user-attachments/assets/4689b26d-b938-4fce-ac00-4af08507e736)

  
## \w\w
* Captures two characters of the phrase

  ![image](https://github.com/user-attachments/assets/ec566399-a66d-41b4-b87e-055260cb2dc4)


## \w\w\w\w\w OR \w{5}
* Captures 5 characters at a time

  ![image](https://github.com/user-attachments/assets/ac0292c7-2879-445b-9f96-61f2afb3428f)

  ![image](https://github.com/user-attachments/assets/3bc6fde8-2f36-4279-8877-d85f5a3ef5a9)


## [A-Z]
* Captures any character A-Z that is in capital letter. E.g., Capital T, R, and M was highlighted

  ![image](https://github.com/user-attachments/assets/fa8b93f6-aa74-44de-9fb4-17eb3c93a5ef)

## [^a-z]
* Captures anything that is not a-z lower-case character e.g., spaces and capital letters

  <img width="812" alt="image" src="https://github.com/user-attachments/assets/156726e0-efdd-4cc2-87f8-41427f018f61" />

# Practice 2 Basic Regex: \d - Any digit from 0-9 | . - Any character

## Write a regular expression that can match both of these numbers (Sample Data: 125-450-955 and 550.22.0.900)
### \d\d\d-\d\d\d-\d\d\d vs. \d\d\d.\d\d\d.\d\d\d
* only captures the number with hyphen in between

  ![image](https://github.com/user-attachments/assets/2d73203f-58b4-4898-b574-1efa9e325442)

* but by adding . in between, it captures any number.

  ![image](https://github.com/user-attachments/assets/11e20a10-0099-4a45-938c-83f22bff78d6)

* If you don't want to include the number with * in between, then specify with [] that you only want to capture numbers with hyphens and dots.

  ![image](https://github.com/user-attachments/assets/49e1afb8-c334-46d9-9d2a-43b89bcd20fb)

  OR

  ![image](https://github.com/user-attachments/assets/3ee28e59-5c70-4af1-ac75-5a36397af3b5)

# Practice 3 Basic Regex: 
* Capturing all names with titles below:
  * (r|s|rs): want to capture Mr or Ms or Mrs
  * M\.: want to capture the dot at the end of Mr.
  * \s: want to capture the spaces in between
  * \w*: want to capture the entire word

  ![image](https://github.com/user-attachments/assets/da92bb17-7bae-49d5-9b90-d256b4008e2c)

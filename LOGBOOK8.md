# **Week 7** 

## **Task 1**

- We logged into the MySql container using the credentials given

![](docs/task1.png)

- Loaded the exisiting database

![](docs/task1_1.png)

- Used a SQL command to print all the profile information of the employee Alice

![](docs/task1_3.png)

---

## **Task2**

### **2.1**

- Exploiting the Sql injection vulnerability, we were able to login as administrator
-"admin'#" means is username = admin and we commented the rest of the query, bypassing the password protection.

![](docs/task2.1.png)

![](docs/task2.1_2.png)

### **2.2**

- Did the same thing that we did on task 1 but from the terminal, and had to encode the special characters that we used on the username

![](docs/urlecoding.png)
![](docs/task2.2.png)
![](docs/task2.2_2)

- Which gaves this html that we ran on the browser

![](docs/task2.3_3.png)


### **2.3**

- couldn't insert into the table because mysql has a default protection against some operations

- the attack did not work because the API does not allow for multiple queries to run in the database server.

![](docs/task2.3.png)

---

## **Task3**

### **3.1**

- To raise Alice's salary we logged into her account and entered the Edit-Profile page

![](docs/task3.1.png)

- We set a nickname and next to it we added ",salary='500000" 

![](docs/task3.1_2.png)

![](docs/task3.1_3.png)


### **3.2**

- To set Boby's salary to 1 we logged back into Alice's account and entered Edit-Profile page

- We set a nickname again and next to it we add "', salary=1 WHERE Name='Boby';#"

![](docs/task3.2.png)

![](docs/task3.2_2.png)


### **3.3**

- We had access to the encrypted passwords and we knew it uses SHA 1, so we used a program to decrypt Boby's password

![](docs/sha1decrypt.png)

- After that, we just logged into Boby's account and changed his password

![](docs/task3.3.png)

	


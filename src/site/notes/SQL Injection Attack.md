---
{"dg-publish":true,"permalink":"/SQL Injection Attack/","tags":["CompSci","CyberSec"]}
---

# Index/Contents
[[SQL Injection Attack#What is an SQL Injection Attack?\|#What is an SQL Injection Attack?]]
[[SQL Injection Attack#Consequences of SQL Injection\|#Consequences of SQL Injection]]
[[SQL Injection Attack#Types of SQL Injection\|#Types of SQL Injection]]
[[SQL Injection Attack#Methodology of SQL Injection\|#Methodology of SQL Injection]]

-----
# What is an SQL Injection Attack?
SQL Injection is a type of attack where the mallicious/unauthorised user is able to enter SQL directly in the input method used on any website. The attack hinges on the hopes that the developer has not placed any form validations to save the website from the attack.

### How does the Attack Work?
To gain access into any website via SQL Injection, the most important part is to check what kind of errors a website throws when we try some input which is out of the ordinary. 
Example: Check output error for the input `" ` or `' `. This allows us to check two things:
1. If there is a validation that removes inverted commas (hence hindering the attack), we would receive the error of the input being empty.
2. If there is no such validation then the error will be different from the regular programmed errors if we use the type of inverted commas the SQL is using.

We are trying to check whether the same thing is being passed directly into SQL without the use of any validation or not. If true, we can exploit this and use the input box as a place to pass SQL commands directly into the database to return some tables of the database (like Username and Passwords).

### How are the attack commands framed?
After we have figured out which of the two types of inverted commas are being used, we simply use the successful inverted comma to close the original input string and with an OR statement attached with it, place some condition that will always be true such as 1=1.
So,the most rudimentary form of the attack which will allow you to login is:
```SQL
''OR 1=1 /*'
/* the first quote (') is the part of the original string, we place the second one to block it closed and place OR 1=1.
The last comment initialiser comments out the original inverted commma which was suppose to actually end the input.*/
```

Since 1=1 is always true, regardless of whatever happens, we can always get in the system and login.

### Other possible commands:
The commands given above are rudimentary and only showcase the theory of how the attack works, they are not the commands that are practically used.

Command to view the Usernames and Passwords of the website's users.
```SQL
''OR 1=1 UNION SELECT Username JOIN Passwords /*' 
```

Commands to view the payment options:
```SQL
''OR 1=1 UNION SELECT Usernames JOIN Passwords JOIN paymentMethods /*'
```

If we do not wish to use comments, we can also use:
```SQL
'   ('OR '1'='1)   '
/*The part in the brackets is what the injection code is. Instead of commenting it out, we can leverage it.*/
```

---
# Consequences of SQL Injection
1. Read and modify sensitive data from the database.
2. Execute administration operations on the database.
	1. Shutdown auditing or the DBMS.
	2. Truncate tables and logs.
	3. Add users.
3. ***Spoof Identity***: It is the result of manipulating databases to insert bogus or misleading information such as email addresses and contact information. 
4. ***Tamper with existing data***: For example alteration of prices in e-commerce applications with the intention of changing price information in order to purchase products or services at a reduced rate. 
	1. Cause repudiation issues such as voiding transactions or changing balances. 
	2. Allow the complete disclosure of all data on the system. 
	3. Destroy the data or make it otherwise unavailable. 
5. Become an unauthorised administrator of the database server.

---
# Types of SQL Injection
There may be many types of SQL Injection, these I know:
#### The types taught in the WTCS course
1. ***==Blind SQL Injection==***: An SQL injection attack where neither the result of the query passed is visible to the attacker nor is the error message seen, rather the attacker sees a generic page.
	1. ***Boolean Exploitation***: A sub-type of Blind Injection where the attacker tries various true & false statements through SQL they can pass and try to analyse the resulting generic webpage that is displayed  how the website responds.
	2. ***Time Delay Based***: Another sub-type where the attacker analyses how long it takes the generic page to respond/appear after the query is passed. If the pages takes a long time (given that the internet connection hasn't slowed down) we know that the query was successful.
2. ***==Error-Based SQL Injection==***: Here the attacker depends on the website's responses in the form of errors (as we have seen above) to generate more queries and damage the system. The above examples in the first question require the Injection to be Error-based.

---
# Methodology of SQL Injection
There are primarily three methodologies in SQL Injection. (according to WTCS Course)
1. ***==Information Gathering==***: Identify the data entry paths in the website GET and POST requests using BRUP or Tamper Data Tools. Extract info through error messages, Find out the query structure for SELECT, UNION and other SQL commands. Try and figure out database name & names of tables inside.
2. ***==Attack Initialisation==***: once Step one is complete, start the attack add `id=1 order by 1` ahead of the website's name (is the link ends in `website.php?`). It will showcase the first column in the database tables.
	1. To confirm the columns edit the url to `id=-1 union select 1, 2, 3, 4, 5, 6` keep adding numbers until you get an error page.
	2. Try obtaining more info using: `id=-1 union select 1, 2, @@version, 4, 5, 6`
	3. For more info about multiple databases (if they exist): `id=-1 union select 1, 2,group_concat(schema_name) , 4, 5, 6 from information_schema. schemata--`
	4. Remove "group" from the above command and only run `concat(database())` to get Database name and info
	5. Edit the above query with `concat(user())` to get user info
	6. To get Table names, use: `id=-1 union select 1, 2,group_concat(schema_name) , 4, 5, 6 from information_schema.tables where table_schema = database() --`
3. ***==Use Advance Function Queries==(if possible)***: This is an advance SQL technique where the SQL is pushed as an entire fricking function! Not going to be easy and nothing has been given in the slides.

---
# Preventing SQL Injection
1. Limit length of user input
2. Use Custom error messages.
3. Always use low privelege account for DB connection i.e., run the database service account with minimal privilege.
4. Clean, Validate and Sanitize user input going into the databse (on both client and server sides)
5. Use Safe API
6. Use Parameterised SQL queries

---


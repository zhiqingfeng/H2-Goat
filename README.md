# H2-Goat

```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```

## Read the summarize

### Security Misconfiguration
- When we are isntalling the new application or the old password still using in the new application, the application might be vulnerable. The way to prevent this situatin is delete the features, components, documentations and samples which are not use that frequently. 

- This is the type of vulnerability in web application security. It happens when security settings and configurations are not properlu set or maintained, leaving the system open to attack. 


### Vulnerable and Outdated Components
- This is use of components in a system. For example, libraries, frameworks. This could be happend when system are built to using components that are no longer maintained or supported.

- Remove unused dependencies, unnecessary features, components, files and documentation. Only obtain components from official sources over secure links. 

### Injection
- It happened when attacker try to inject the code into the system. This is allow the attacker to gain access to get information and data. 

- Some commend injections are like SQL, OS command. The way to prevent it is use sturcture SQL, such as table names, column names and so on.

### Darknet Diaries - NEWSWIRES
- Investing in the stock market can be very profitable. Especially if you can see into the future. This is a story of how a group of traders and hackers got together to figure out a way to see into the future and make a lot of money from that.

- The stock market traders aim to predict the future. If they can buy a stock that goes up in value, they will make money. But they could lost a lot of money at the same time. 

- He spemt months to creating a huge amount of SQL injection. And he got them working. 

- The SEC is an indenpendent U.S. governmet agency responsible for protecting investor, maintaining fair and orderlu functioning of the securities markets, and facilitating capital formation. 


### CVE (Common Vulnerabilities and Exposures)
[CVE-2022-47966](https://nvd.nist.gov/vuln/detail/CVE-2022-47966)

- Multiple Zoho ManageEngine on-premise products, such as ServiceDesk Plus through 14003, allow remote code execution due to use of Apache xmlsec (aka      XML Security for Java) 1.4.1, because the xmlsec XSLT features, by design in that version, make the application responsible for certain security            protections, and the ManageEngine applications did not provide those protections.

- This vulnerability already reported and addressed. The remote code execution vulnerability was due to the usage of an outdated third party dependency, Apache Santuario. 


## Sequel - Solve SQLZoo.
*This task basically used SQL, I have use SQL statment during my working place and this task is not that very difficult for me. :)*
### 0 SELECT basics.
  
1. Introducing the world table of countries 
   ```sql
   SELECT population FROM world
   WHERE name = 'Germany'
   ```
2. Scandinavia
    ```sql
   SELECT name, population FROM world
   WHERE name IN ('Sweden', 'Norway','Denmark')
   ```
3. Just the right size
    ```sql
   SELECT name, area FROM world
   WHERE area BETWEEN 200000 AND 250000
   ```
   
### 2 SELECT from World. 

1. Introduction
   ```sql
   SELECT name, continent, population FROM world
   ```
   img src="https://user-images.githubusercontent.com/95883827/215506289-e33ec040-fa5a-4252-a6cf-cfb24b4bd71c.png" width="150" height="150">

2. Large Countries
   ```sql
   SELECT name FROM world
   WHERE population >= 200000000
   ```
   <img src="https://user-images.githubusercontent.com/95883827/215506333-0d88aaff-5b0f-4b70-8fac-b13fa9b79bf6.png" width="150" height="150">

3. Per capita GDP
   ```sql
   SELECT name, (gdp/population) as PerCapitaGDP FROM world
   WHERE population >= 200000000;
   ```
   <img src="https://user-images.githubusercontent.com/95883827/215506378-535587eb-932b-486d-ba39-1802f9d7a3f4.png" width="150" height="150">

4. South America In millions
   ```sql
   SELECT name, (population/1000000) FROM world
   WHERE continent = 'South America'
   ```
   <img src="https://user-images.githubusercontent.com/95883827/215506427-2df84d21-cf2d-4533-a1a9-2751d610bbe9.png" width="150" height="150">

5. France, Germany, Italy
   ```sql
   SELECT name, population FROM world
   WHERE name IN ('France', 'Germany', 'Italy')
   ```
   <img src="https://user-images.githubusercontent.com/95883827/215506464-d0d8a8b3-8a1e-4eea-99e1-481a961f950a.png" width="150" height="150">



## Injected - Solve WebGoat.

### A1 Injection (intro) 

1. What is SQL
  
   <img src="https://user-images.githubusercontent.com/95883827/215509266-3dab2943-da7c-4e43-bd79-b249366ba3ec.png" width="700" height="120">

2. Data Manipulation Language (DML) 

   ```sql
   UPDATE Employees SET department='Sales'
   WHERE first_name ='Tobi' and last_name = 'Barnett'
   ```
   
   <img src="https://user-images.githubusercontent.com/95883827/215510132-eed5109b-7efe-4a09-8d4b-4bab326370c5.png" width="700" height="120">

3. Data Definition Language (DDL)
  
   ```sql
   ALTER TABLE employees ADD phone varchar(20)
   ```
   
   <img src="https://user-images.githubusercontent.com/95883827/215511129-1a9b2424-4242-4e66-99cc-f9a55d197dc3.png" width="700" height="120">

4. Data Control Language (DCL)
   
   ```sql
   GRANT ALTER TABLE TO UnauthorizedUser
   ```
   
   <img src="https://user-images.githubusercontent.com/95883827/215511716-2dd1281c-4768-4f68-8bc3-9ce14453eb7e.png" width="700" height="120">

5. String SQL injection
   
   ```sql
   SELECT * FROM user_data WHERE first_name ='John' AND last_name = 'Smith' or '1'='1'
   ```
   
   <img src="https://user-images.githubusercontent.com/95883827/215512932-e9c4f829-a3d8-48c5-ad13-b87f315f0ccf.png" width="700" height="120">

6. Numeric SQL injection

   ```sql
   SELECT * FROM user_data WHERE Login_Count = 2 AND userid =2 or '2'='2'
   ```
   
   <img src="https://user-images.githubusercontent.com/95883827/215513922-6dc0f5d8-cb23-4ae4-81c9-69a274a956dd.png" width="700" height="120">


7. Compromising confidentiality with String SQL injection
 
   
   <img src="https://user-images.githubusercontent.com/95883827/215515265-21bf70ee-928b-41ad-9f2c-8cc92021683b.png" width="700" height="120">
  

8. Compromising Integrity with Query chaining
   
   
   <img src="https://user-images.githubusercontent.com/95883827/215515580-539b5140-6c2b-4d3e-b1ae-8825a9902b2f.png" width="700" height="120">

9. Compromising Availability
    
   ```sql
   DROP TABLE access_log
   ```
   
   <img src="https://user-images.githubusercontent.com/95883827/215516039-55783314-9b3e-4d13-a7a9-91df40c37f17.png" width="700" height="120">

*For the question 7 to 9, I can't find the solution to reslove them, but I am still tring to do for them. :) 

# Voluntary Bonus

## SQLZoo Tasks

### SELECT names

1. Find the country that start with Y
   
   ```sql
    SELECT name FROM world
    WHERE name LIKE 'Y%'
   ```
   
   <img src="https://user-images.githubusercontent.com/95883827/215547235-4d98bf34-8d2e-4b7b-8756-24ba77a05bce.png" width="150" height="150">

   
2. Find the countries that end with y
   
   ```sql
    SELECT name FROM world
    WHERE name LIKE '%y'
   ```
   
   <img src="https://user-images.githubusercontent.com/95883827/215547419-c89a8a42-71bc-4520-8629-d652b0ae8b9e.png" width="150" height="150">

3. Find the countries that contain the letter x
   
   ```sql
    SELECT name FROM world
    WHERE name LIKE '%X%'
   ```
   
   <img src="https://user-images.githubusercontent.com/95883827/215548097-bfec5521-6186-446e-aed4-23d5c872c978.png" width="150" height="150">

4. Find the countries that end with land
   
   ```sql
    SELECT name FROM world
    WHERE name LIKE '%land'
   ```
   
   <img src="https://user-images.githubusercontent.com/95883827/215548286-17f90054-e986-4686-918a-3eb7a64e4971.png" width="150" height="150">

5. Find the countries that start with C and end with ia
   
   ```sql
    SELECT name FROM world
    WHERE name LIKE 'C%ia'
   ```
   
   <img src="https://user-images.githubusercontent.com/95883827/215548476-8c0a899d-2132-4ee6-a07d-2fae72aca108.png" width="150" height="150">
   
6. Find the country that has oo in the name
   
   ```sql
    SELECT name FROM world
    WHERE name LIKE '%oo%'
   ```
   
   <img src="https://user-images.githubusercontent.com/95883827/215548669-02bb6b23-ef13-491b-a9b9-59a2a2165803.png" width="150" height="150">

7. Find the countries that have three or more a in the name
   
   ```sql
   SELECT name FROM world
   WHERE name LIKE '%a%a%a%'
   ```
   
   <img src="https://user-images.githubusercontent.com/95883827/215548953-e55375b7-e195-4cff-8b8a-6968030b8d6e.png" width="150" height="150">

8. Find the countries that have "t" as the second character.
   
   ```sql
   SELECT name FROM world
   WHERE name LIKE '_t%'
   ORDER BY name
   ```
   
   <img src="https://user-images.githubusercontent.com/95883827/215549144-c1a6c73e-0622-432b-9ba6-9fe05150ac52.png" width="150" height="150">

9. Find the countries that have two "o" characters separated by two others.
   
   ```sql
   SELECT name FROM world
   WHERE name LIKE '%o__o%'
   ```
   
   <img src="https://user-images.githubusercontent.com/95883827/215549344-7f66d5a8-669e-4666-9d07-595b3b3f07ac.png" width="150" height="150">

10. Find the countries that have exactly four characters.
    
    ```sql
    SELECT name FROM world
    WHERE name LIKE '____'
    ```
   
     <img src="https://user-images.githubusercontent.com/95883827/215549501-666a303a-853a-449d-acf4-305b44f7d70d.png" width="150" height="150">
  
   


   


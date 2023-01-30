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

### Vulnerable and Outdated Components
- Remove unused dependencies, unnecessary features, components, files and documentation. Only obtain components from official sources over secure links. 

### Injection
- Some commend injections are like SQL, OS command. The way to prevent it is use sturcture SQL, such as table names, column names and so on.

### Darknet Diaries
- Bitcoin. This is the digital currency. 

### CVE (Common Vulnerabilities and Exposures)
[CVE-2022-47966](https://nvd.nist.gov/vuln/detail/CVE-2022-47966)

- Multiple Zoho ManageEngine on-premise products, such as ServiceDesk Plus through 14003, allow remote code execution due to use of Apache xmlsec (aka      XML Security for Java) 1.4.1, because the xmlsec XSLT features, by design in that version, make the application responsible for certain security            protections, and the ManageEngine applications did not provide those protections.

- This vulnerability already reported and addressed. The remote code execution vulnerability was due to the usage of an outdated third party dependency, Apache Santuario. 


## Sequel - Solve SQLZoo.
* This task basically used SQL, I have use SQL statment during my working place and this task is not that very difficult for me. :) *
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
   ![image](https://user-images.githubusercontent.com/95883827/215506289-e33ec040-fa5a-4252-a6cf-cfb24b4bd71c.png)

2. Large Countries
   ```sql
   SELECT name FROM world
   WHERE population >= 200000000
   ```
   ![image](https://user-images.githubusercontent.com/95883827/215506333-0d88aaff-5b0f-4b70-8fac-b13fa9b79bf6.png)

3. Per capita GDP
   ```sql
   SELECT name, (gdp/population) as PerCapitaGDP FROM world
   WHERE population >= 200000000;
   ```
   ![image](https://user-images.githubusercontent.com/95883827/215506378-535587eb-932b-486d-ba39-1802f9d7a3f4.png)

4. South America In millions
   ```sql
   SELECT name, (population/1000000) FROM world
   WHERE continent = 'South America'
   ```
   ![image](https://user-images.githubusercontent.com/95883827/215506427-2df84d21-cf2d-4533-a1a9-2751d610bbe9.png)

5. France, Germany, Italy
   ```sql
   SELECT name, population FROM world
   WHERE name IN ('France', 'Germany', 'Italy')
   ```
   ![image](https://user-images.githubusercontent.com/95883827/215506464-d0d8a8b3-8a1e-4eea-99e1-481a961f950a.png)

   

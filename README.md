# Selenium-Amazon-Automation

Project Details 

ABC Business Solutions has bagged a contract for an Automation testing services project with Amazon. As part of the preliminary project acceptance, Amazon has asked ABC Business Solutions to design a POC of the Selenium automation project with data-driven framework using standard data exchange files with Maven and TestNG. As you are part of the ABC Business Solutions team you are given the task for designing this POC. 

Software Pre-requisites:  


<table><tr><th colspan="1" rowspan="2"><b>Software</b> </th><th colspan="2"><b>Version</b> </th><th colspan="1" rowspan="1"><b>Download Link</b> </th><th colspan="1" rowspan="2"><b>Additional Information</b> </th></tr>
<tr><td colspan="1"><b>min. reqd.</b> </td><td colspan="1"><b>preferred</b> </td></tr>
<tr><td colspan="1">jdk </td><td colspan="1">8 or above </td><td colspan="1">17 or 21 </td><td colspan="1">[Click here ](https://www.oracle.com/java/technologies/downloads/)</td><td colspan="1"></td></tr>
<tr><td colspan="1">Eclipse </td><td colspan="1">2020-03 </td><td colspan="1">2020-06 </td><td colspan="1">[Click here ](https://www.eclipse.org/downloads/)</td><td colspan="1">IDE used for development </td></tr>
<tr><td colspan="1">Selenium Server  </td><td colspan="1">4\.18.1 </td><td colspan="1">4\.18.1 </td><td colspan="1">[Click here ](https://github.com/SeleniumHQ/selenium/releases/download/selenium-4.18.0/selenium-server-4.18.1.jar)</td><td colspan="1"></td></tr>
<tr><td colspan="1">Selenium WebDriver </td><td colspan="1">4\.18.1 </td><td colspan="1">4\.18.1 </td><td colspan="1"></td><td colspan="1" rowspan="2">Add in the pom.xml  </td></tr>
<tr><td colspan="1">TestNG </td><td colspan="1">7\.9.0 </td><td colspan="1">7\.9.0 </td><td colspan="1"></td></tr>
</table>
Overall Project Details 

1. Design a Data-Driven project using properties file, xml file, yaml file (if required) 
1. Create a Maven Project 
1. Create 3 packages 
   1. pom ➔ To store the page object classes and methods 
   1. utils ➔ To perform the common operations 
   1. test ➔ To store the test files  
1. Create a Grid Configuration for parallel testing 

Maven Project 

1. Create a simple maven project 
1. Add the following dependencies 
   1. Selenium 
   1. TestNG 
1. Create a new properties file say config.properties and add the following details 
   1. browser=chrome 
   1. url=https://www.amazon.in 
1. Use utils class to perform the following operations 
   1. Read properties file 
   1. Setup the browser by reading the properties file method 
   1. Getter method to return the driver object 
   1. Quit the browser 
1. Use test package to perform these operations 
1. Create a BaseTest class 
1. Use BeforeSuite in the BaseTest class to call the  
   1. setup browser method 
   1. get the driver object 
1. Use AfterSuite to quit the browser 
1. Create rest of test class files and inherit the BaseTest class for the setup and quit browser activities 

Page Object Model 

1. Create pom classes with page factory 
1. Create constructors in pom classes with parameters to accept the driver object and initialize it along with page factory  
1. Create a class for navigation and use this class to navigate to different modules and links 
1. Use action class to navigate to Create a Wish List (Accounts and Lists ➔ Create a Wish List) 
1. Create a page for mobile details with reusable methods say, 
1. Validate the total results displayed 
2. Play the mobile video 
2. Select the Avg Customer Review selection 
2. Get the product price 
2. Change the delivery location 
2. Add to cart 
2. Close the “Add to Cart” window 
2. etc… 

TestNG 

**Test Cases (create as much as details in POM classes and call those methods in the test cases)** 

**Test Class-1** 

1. url validation 

a.  Enter the url as[ http://amzn.in ](http://amzn.in/)and check if the url is redirected to 

<https://www.amazon.in/>

2. Validate the page title “Online Shopping site in India: Shop Online for Mobiles, Books, Watches, Shoes and More - Amazon.in” 

**Test Class-2** 

1. Use navigation to navigate to Create a Wish List (Accounts and Lists ➔ Create a Wish List) and verify whether the navigation was successful

   ![](Aspose.Words.2e680880-b20e-41d4-8776-9bc76dcfbf4f.005.jpeg)

2. Use Navigation to navigate to Amazon Pay module and validate the page 
2. Use Navigation to navigate New Releases module and validate the page 

**Test Class-3** 

1. Create a testng.xml with parameter as valid and invalid credentials and use them in the test class 
1. Create test case for login validation 
1. Validate valid login and logout 
1. Invalid login validation 

**Test Class-4** 

1. Use navigation to search for a mobile say, “mi mobile” 
1. Validate the results, say “1-16 of 264 results for "mi mobile"”

   ![](Aspose.Words.2e680880-b20e-41d4-8776-9bc76dcfbf4f.006.png)

3. Select “Avg. Customer Review” as 4 start & up”  

![](Aspose.Words.2e680880-b20e-41d4-8776-9bc76dcfbf4f.007.png)

4. Select the first mobile say “Redmi Note 8 (Moonlight White, 6GB RAM, 128GB Storage)” 

a.  Validate the title is changed to relevant to the mobile select. Say for 

the above example it should be “Redmi Note 8 (Moonlight White, 6GB RAM, 128GB Storage): Amazon.in: Electronics” 

5. Get the mobile price and validate it 

   ![](Aspose.Words.2e680880-b20e-41d4-8776-9bc76dcfbf4f.008.png)

6. Delivery location validation 

a.  Click on the “Select delivery location”

![](Aspose.Words.2e680880-b20e-41d4-8776-9bc76dcfbf4f.009.png)

7. Popup validation and pincode validation 
1. wait for the pop up “Choose your location”

   ![](Aspose.Words.2e680880-b20e-41d4-8776-9bc76dcfbf4f.010.png)

2. Enter the pincode and click on apply 
3. Validate the change in the delivery location, should display as “Deliver to <city pincode>” as shown below

   ![](Aspose.Words.2e680880-b20e-41d4-8776-9bc76dcfbf4f.011.png)

8. Click on the sponsored link as shown below

   ![](Aspose.Words.2e680880-b20e-41d4-8776-9bc76dcfbf4f.012.png)

1. Use iframe to Click on the link 
1. After clicking the link verify a new window is opened with the mobile details 
1. Navigate to the new window and close it 
1. Navigate back to the previous window 
9. Click on add to cart

   ![](Aspose.Words.2e680880-b20e-41d4-8776-9bc76dcfbf4f.013.jpeg)

1. Wait for the window to be displayed 
1. Validate the “Added to Cart” message 
1. Close the “Added to Cart” window 
10. Use Java Script executor to scroll the page down till “Technical Details” is displayed 


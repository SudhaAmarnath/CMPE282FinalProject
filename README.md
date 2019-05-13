# CMPE-282 Final Project - FoodBolt (Team Spartans)
Repo for the CMPE-282 Final Project

**Overview**

Dining-out in our favorite restaurant with our beloved ones is one of the main recreations for many people. In order to spend some quality time with our family, friends or business partners during dining, it is necessary to be sure about the slot at the restaurant for the number of people to dine in. There are very minimal online services which offer table booking for multiple restaurants around the locality. Food Bolt application is a table reservation platform which provides seamless access for both users and restaurant owners to reserve tables. 

  

One-Click IoT device enhances the user experience in table reservation which gives an edge over our competitors. With extensive use of cloud resource, we have optimized the cost of development and operation without compromising the quality of reservation service. With the optimized cost, we are bringing the IoT device to customers at free of cost and enhancing added value to our service.

**ARCHITECTURE DIAGRAM**


**TECHNOLOGIES USED**

1. FrontEnd 

    - HTML  
    - JavaScript  
    - CSS  
    - BootStrap 
    - Thymeleaf 

2. Backend

    - Java 
    - Spring Boot Framework 

3. Database

    - RDS (MySQL) - Used as the DB for the application for storing the major data. 

4. AWS Resources

    - Route53 - DNS to resolves the IP address for the application domain. 
    - ELB - Elastic Load Balancer is used to handle the load and route it to different EC2 instances. 
    - EC2 - For hosting the Web and Application server. 
    - Auto Scaling - Used to support the highly available and scalable web application. 
    - Lambda - Used the lambda function for handling the IOT 1-click button and sending the notification to the user for booking confirmation. Also to upload the logs to Cloud Watch. 
    - SES - Simple Email Service is used to send email on RDS update. 
    - SNS - Simple Notification Service is used to send email on EC2 health change. 
    - Certificate Manager - Generating the SSL certificate for implementing HTTPS. 
    - IOT Core: For connecting the 1-click device to the cloud. 
    - IOT 1-Click: For triggering the Lambda functions from the IOT device. 
    - S3 - Used to store the build from Jenkins. 
    - AWS CloudFormation - To reconstruct the AWS infrastructure. 
    - AWS ECS - Amazon Elastic Container Service   - To deploy the code in Amazon container. 

5. Source Code Management

    - GitHub 

7. CI/CD

    - Jenkins 
    - Code Pipeline - Used to deploy the changes to the system 
    - Code Build: Generating the build output. 
    - Code Commit: This is used as the version control and code repository (code is also uploaded to the GitHub) 
    - Code Deploy: Deploys the code to the server.

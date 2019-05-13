# CMPE-282 Final Project - FoodBolt (Team Spartans)
Repo for the CMPE-282 Final Project

## Overview

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
    
**Infrastructure as a Service (IaaS)**

**AWS Cloud Formation**
    An Application stack has been created which consists of EC2 instance, RDS for MySQL, Security groups and continous integration pipeline. Application then be containerized to run on EC2 created by the cloud formation script.
    
### Advantages of using Cloud Services  
  
**High Availability**

**Cost Optimization**

With the extensive use of AWS resources, we have optimized the cost in every phase of the development lifecycle. With the pay-as-you-go model, the operational cost has been reduced drastically than the traditional model. With the help of Auto-scaling, we make sure we are utilizing only the resources necessary for the load our application is handling at any point of time with this approach we are reducing the cost further and providing more valuable service to our customers.

**Security**

The AWS resources are placed in a Virtual Private Cloud with additional AWS security components like Internet Gateway which allows for the communication of the AWS resources in a subnet to the Internet. The Route table contains the list of inbound and outbound rules to allow communication to specific ports. The EC2 instances are connected to the Security Group with Internet Gateway making it a Subnet whereas the Internet Gateway is not attached to the Security Group of the RDS to make it a Private Subnet.


**Disaster Recovery**

RDS has been enabled in Multiple Availability Zones in order to make the application highly available and also available during a disaster. In addition to Multi-AZ deployment is enabled, the application archives the backup for one week. Also, frequent RDS snapshots are taken to rebuild in case of any failures.


**Role Based Access**

The end user can access the application by two roles namely User role and Service Provider role. A user is given the access to view the list of restaurants registered under the application, book the desired restaurant, cancel the reservation and view the history of booking made under the user profile. The Service Provider has registered the restaurant under the application, cancel the reservations made in the restaurant and view the panel of bookings made in the restaurant.

**Fault-Tolerant**

A web application consists of three tiers namely web, application, and database. The Web tier to resistant to fault tolerance by the AWS service of Elastic Load Balancing. Since the Load Balancer redirects the web traffic to healthy Amazon EC2 instances for more consistent application performance. The Application tier is resistant to fault tolerance through Auto-Scaling which monitors the application enables scaling of EC2 instances based upon end user’s usage of the application. The Database tier is resistant to fault tolerance by maintaining a standby database in the other zone and a read replica in the primary zone.

# Building an Event Driven Lightning Component

In this post, we will create an event driven commission calculator, and add it to our Opportunity layout.

To complete this tutorial, you'll need a developer/demo org to help you follow along.

### 1. Create a Domain:

Salesforce requires that an app must have it's own domain, to be able to add a Lightning Component to a record layout. So let's start by adding a domain to our org.

First, go to setup, and search for "Domain" in the search bar. Then select "My Domain".

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/1.png)

Next, add a unique domain name, and click "Check Availability." If the domain is available, click "Register Domain", otherwise try a different domain name.

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/2.png)

Now we need to log in using our new domain name. Navigate to http://[yourdomainname].salesforce.com, and log in using your org credentials.

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/3.png)

Last, go back to "My Domains" in setup, and click "Deploy to Users" to activate your new domain.

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/4.png)


![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/5.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/6.0.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/6.1.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/6.2.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/7.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/8.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/9.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/10.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/11.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/12.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/13.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/14.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/15.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/16.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/17.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/18.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/19.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/20.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/21.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/22.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/23.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/24.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/25.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/26.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/27.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/28.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/29.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/30.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/31.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/32.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/33.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/33.png)

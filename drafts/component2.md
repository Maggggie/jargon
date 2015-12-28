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

### 2. Create Component to Display Total Commission:

Open up the developer console by clicking on the gear in the upper right hand corner of your homepage, and then click: "Developer Console." Once you have the developer console open, create a new Lightning Component (File>New>Lightning Component). Name the component "commissionCalc."
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/5.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/6.0.png)

This component will simply display the total commission the salesperson will earn for closing the Opporunity. Other Lightning Components will drive the inputs that change this value.

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/6.1.png)

Add the following code to your new Lightning Component:

```html
<aura:component implements="flexipage:availableForAllPageTypes">
	<div style="text-align: center;">Commission:<br/><br/><span id="commish">$500</span></div>
</aura:component>
```
There are two pieces worth mentioning in this code block. First, ``` implements="flexipage:availableForAllPageTypes" ```, allows us to place this Lightning Component on to a record layout. Second, ``` <div style="text-align: center;">Commission:<br/><br/><span id="commish">$500</span></div> ``` will display the commission payout for the salesperson (defaults to $500).


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

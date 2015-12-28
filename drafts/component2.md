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

Add the following code to your new Lightning Component:

```html
<aura:component implements="flexipage:availableForAllPageTypes">
	<div style="text-align: center;">Commission:<br/><br/><span id="commish">$500</span></div>
</aura:component>
```
There are two pieces worth mentioning in this code block. First, ``` implements="flexipage:availableForAllPageTypes" ```, allows us to place this Lightning Component on to a record layout. Second, ``` <div style="text-align: center;">Commission:<br/><br/><span id="commish">$200</span></div> ``` will display the commission payout for the salesperson (defaults to $200).

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/6.2.2.png)


![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/6.2.png) <<<MOVE

Now, let's add this component to the Opportunity record layout. Navigate to any Opportunity, and click on the gear icon in the upper right hand corner. Then click "Edit Page."

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/7.png)

Now we're inside the Lightning App Builder. From here we can drag Lightning Components on to our layout. On the left hand side, you will see a list of our available Lightning Components. Lightning Components developed in-house will be listed under "Custom", which is where you should see our "commissionCalc."

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/8.png)

Add the Lightning Component to your layout by dragging it above the text "To stay on track and see Sales Path...", and click "Save."

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/9.png)

Make sure to Activate the page...

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/10.png)

...and check "Active" on the next screen to add the component to the correct page layout.

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/11.png)

Now if you refresh your Opportunity, you should see our Lightning Component added to the page.

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/12.png)

### 3. Create Component to Change Commission Output

So we've created a Lightning Component, and added it to our layout, but it doesn't do anything except display a static commission amount. Let's create a slider that allows the salesperson to adjust the total price, which we'll use to update the total commission.

First, create a new Lightning Component, and name it "commissionSlider."

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

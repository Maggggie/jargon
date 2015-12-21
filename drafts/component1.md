This article is intended as an aid in building your first Salesforce Lightning Component. In this post, we will cover duplicating
an existing Visualforce Page, as a Lightning Component. Specifically, we will create a Chatter feed component for use in a Napili template.

To complete this tutorial, you will need a developer/demo org ready, to allow you to follow along.

### Step One:

Open up the developer console by clicking on the gear in the upper right hand corner of your homepage, and then clicking: "Developer Console". Once you have the developer console open, create a new visualforce page to hold our chatter feed.

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component1/1.png)

Name the file, "lightningChatter"...

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component1/2.png)

... and add the following code to page:

```html
<apex:page >
    <chatter:newsfeed />
</apex:page>
```

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component1/3.1.png)

Now, navigate to https://[yourdomainroot].salesforce.com/apex/lightningChatter, and you should see your Chatter feed appear like so:

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component1/3.2.png)

### Step Two:

Now we're ready to create our new Lightning Component. Name your new component "lightningChatter" as well:

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component1/4.png)

Add an iFrame to the Lightning Component, that references the Visualforce Page we created:

```html
<aura:component>
    <iframe src="https://[yourdomainroot].salesforce.com/apex/lightningChatter"/>
</aura:component>
```

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component1/5.png)

We also need to add the 'implements="forceCommunity:availableForAllPageTypes"' property to the Lightning Componenet, to allow it to be added to our community:

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component1/6.png)


![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component1/7.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component1/8.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component1/9.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component1/10.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component1/11.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component1/12.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component1/13.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component1/14.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component1/15.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component1/16.png)


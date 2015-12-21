This article is intended as an aid in building your first Salesforce Lightning Component. In this post, we will cover duplicating
an existing Visualforce Page, as a Lightning Component. Specifically, we will create a Chatter feed component for use in a Napili template.

To complete this tutorial, you will need a developer/demo org ready, to allow you to follow along.

### 1. Create the Visualforce Page:

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

Next, navigate to https://[yourdomainroot].salesforce.com/apex/lightningChatter, and you should see your Chatter feed appear like so:

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component1/3.2.png)

### 2. Create the Lightning Component:

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

### 3. Spin-Up A New Community:

Next, we need to create a new community to hold our new Lightning Component. Go to Setup, and search for "Communities" in the search bar. Select "All Communities":

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component1/7.png)

Click "New Community" to create our new community...

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component1/8.png)

...and select the Napili template.

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component1/9.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component1/10.png)

### 4. Add the Component to the Community:

Open the Global Header, and select "Go to Community Builder".

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component1/11.png)

Now that we're in the Community Builder, let's add our Chatter component to the Homepage. Click on the piece of paper on the left nav-bar. This will display a list of all pre-built, and custom Lightning Components. Grab "lightningChatter", and drag it in to the body of the page. Save the page...

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component1/13.png)

...and navigate to the community home page. We should see a sliver of our component, but it doesn't look right.

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component1/14.png)

Let's return to the Developer Console, and add these style attributes to our iFrame:

```html
    <iframe src="https://gs0.salesforce.com/apex/lightningChatter" width="100%" height="1000px;" frameBorder="0"/>
````

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component1/15.png)

When we reload the community, we'll get a properly styled Chatter feed:

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component1/16.png)


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

*2.1*

```html
<aura:component implements="flexipage:availableForAllPageTypes">
    <div style="text-align: center;">Commission:<br/><br/><span id="commish">$500</span></div>
</aura:component>
```
There are two pieces worth mentioning in this code block. First, ``` implements="flexipage:availableForAllPageTypes" ```, allows us to place this Lightning Component on to a record layout. Second, ``` <div style="text-align: center;">Commission:<br/><br/><span id="commish">$200</span></div> ``` will display the commission payout for the salesperson (defaults to $200).

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/6.2.2.png)

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
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/12.png)

Now if you refresh your Opportunity, you should see our Lightning Component added to the page.

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/13.png)

### 3. Create Component to Change Commission Output

So we've created a Lightning Component, and added it to our layout, but it doesn't do anything except display a static commission amount. Let's create a slider that allows the salesperson to adjust the total price, which we'll use to update the total commission.

First, create a new Lightning Component, and name it "commissionSlider."

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/14.png)

Add the following code to your new Lightning Component:

*3.1*

```html
<aura:component implements="flexipage:availableForAllPageTypes">
    <ltng:require scripts="/resource/jquery, /resource/jqueryui/jquery-ui-1.11.4.custom/jquery-ui.min.js" styles="/resource/jqueryui/jquery-ui-1.11.4.custom/jquery-ui.min.css"/>   
    <div style="margin: 40px;">
        <div style="width: 100%; margin-top: 10px; text-align: center">Price:</div>
        <div id="price" style="width: 100%; margin-bottom: 20px; margin-top:10px; text-align: center">$10,000</div>
        <div id="slider"></div>
    </div>
</aura:component>
```

The code pulls in an external Javascript library that allows us to create a slider input field. Then, the html renders the slider, and sets the default value to $10,000.


![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/16.png)

Next, we need to upload the Javascript library (jQuery UI) to our static resources. Go to setup, and search for "Static Resources", then click "New."

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/19.2.png)

[Download this file](https://s3-us-west-2.amazonaws.com/salesforcejeff/jquery-ui-1.11.4.custom.zip), and save it as a static resource named "jqueryui." Make sure the cache control is set to "Public."

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/20.2.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/21.2.png)
![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/22.2.png)

Now the structure of the component (the HTML) is complete, but we need to add some Javascript to bring the slider to life. First, add ```afterScriptsLoaded="{!c.afterScriptsLoaded}"``` to line 2, as shown in the image below. This piece of code will fire off the Javascript, after the external libraries have loaded.

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/23.png)

In Lightning, Javascript code lives seperate from our "Component" file, in a "Controller" file. If you try to add Javascript directly to the Component file, an error will appear, and the file won't save. So let's open up our Controller file by clicking "Controller" in the right side bar of the Developer Console. You should see the file below:

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/24.png)

Next, add the following code to the file:

*3.2*

```javascript
({
    afterScriptsLoaded : function(component, event, helper) {
        $(function() {
            $( "#slider" ).slider({
                value: 50,
                slide: function( event, ui ) {
                    $('#price').text("$" + Math.round(20000 * (ui.value/100)))
                }
            });
        });
    }
})
```

This code attaches to the slider, and updates the price accordingly.

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/25.1.png)

Now we're ready to add the slider component to our Opportunity record page layout, and it should appear like so:

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/26.png)

### 4. Create a New Event

Our final step is to create a Lightning event that will "glue" our slider to our commission component. This piece of code allows us to send a message from the slider component, to the commission component, telling it how much the price input has changed. From there, we update the total commission.

First, we need to create the Lightning Event (File > New > Lightning Event).

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/27.png)

Name the event, "commissionSliderEvt", and save the file.

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/28.png)

You should now see the file below:

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/29.png)

Add the following code to the file:

*4.1*

```html
<aura:event type="APPLICATION">
    <!-- add aura:attribute tags to define event shape.
      One sample attribute here -->
    <aura:attribute name="message" type="Integer"/>
</aura:event>
```

This code acts as the middle man between the two components. We use the "message" aura:attribute to hold the new value of the Opportunity price.

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/30.1.png)

### 5. Fire and Listen For Event

Finally, we need to add some code to both of our components. In our slider component, we need to add some code, which will fire a new event, when the user moves the slider:

*5.1*

```javascript
({
    afterScriptsLoaded : function(component, event, helper) {
        $(function() {
            $( "#slider" ).slider({
                value: 50,
                slide: function( event, ui ) {
                    $('#price').text("$" + Math.round(20000 * (ui.value/100)))
                    var evt = $A.get("e.c:commissionSliderEvt");
                    evt.setParams({
                        "message": Math.round(20000 * (ui.value/100))
                    });
                    evt.fire();
                }
            });
        });
    }
})
```


![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/25.png)

Last, we need to add some code to the Commission component, that updates the commission total when it recieves a new event. Navigate back to the "commissionCalc" component, and add the following code:

*5.2*

```html
<aura:registerEvent name="commissionSliderEvt" type="c:commissionSliderEvt"/>
<aura:handler event="c:commissionSliderEvt" action="{!c.handleEvent}"/>
```

Here, we're telling the commission component to start listening for our "commissionSliderEvt". Then when it receieves this event, it runs an action called, "handleEvent", which we will create next. (I've also updated the default commission to $200, so that it accurately defaults to a 5% commission)

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/33.png)

Now let's open up the controller for this component...

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/31.png)

...and add the following code:

*5.3*

```javascript
({
  handleEvent : function(component, event, helper) {
        $(function(){
            $('#commish').text('$'+event.getParams().message*.05)
        })
  }
})
```

This is the code block that is called when our component receives an event from "comissionSliderEvt". It takes the price that was passed from the slider, and multiplies it by 5% to get the salesperson's commission.

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/component2/32.png)

Now when you return to your Opportunity, you should see the commission total update when you move the slider.

![alt text](https://s3-us-west-2.amazonaws.com/salesforcejeff/commishSlider.gif)
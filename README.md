# APPLOZIC WEB PLUGIN     

### Overview      


Integrate messaging into your mobile apps and website without developing or maintaining any infrastructure. Register at https://www.applozic.com to get the application key.

Instructions for Web Plugin: [https://applozic.readme.io/docs/applozicwebplugin-gettingstarted](https://applozic.readme.io/docs/applozicwebplugin-gettingstarted)

Want to contribute? Drop us a mail at growth@applozic.com     


### Getting Started        
    
    
  ***Welcome to the Applozic-Web-Plugin***

****Applozic messaging jQuery plugin****

Integrate messaging plugin into your web application.

A small jQuery plugin for integrating messaging into your web page to directly send and receive messages to other users via Applozic messaging platform and also to see your latest conversations.


Add Applozic messaging plugin into your web application :


Step 1: Register at **https://www.applozic.com/** to get the application key.

Step 2: For the standard user interface, add the following Applozic messaging plugin script file before **`</head>`** into your web page:      

** text **     
` <script type="text/javascript" >(function(d, m){var s, h; s = document.createElement("script");s.type = "text/javascript";s.async=true;s.src="https://apps.applozic.com/sidebox.app";h=document.getElementsByTagName('head')[0];h.appendChild(s);window.applozic=m;m.init=function(t){m._globals=t;}})(document, window.applozic || {});</script> `    
 
 
 
 
 Step 3: Copy and paste below script before **`</body>`** to initialize plugin: 
 
 
 
 
** text **    
` <script type="text/javascript" >window.applozic.init({userId: 'user id', appId: 'application key', contactDisplayName: displayName, contactDisplayImage: contactImageSrc, desktopNotification: true});</script> `    



Step 4: Replace the following parameters in script:    




** text **      
` userId: 'User Unique id',                 // required
appId: 'Your application key'             // required
contactDisplayName: 'Callback function to return contact name by userId',
       // function should receive one parameter i.e userId. Example given in Step 6 (optional)
contactDisplayImage: 'Callback function to return image src of contact by  userId',
      // function should receive one parameter i.e userId'. Example given in Step 7 (optional)
desktopNotification: true or false,
      // only for chrome browser enable or disable desktop notifications for incoming messages (optional) `    




Note : Example of callback functions and json format is given in below in step 6,7

Step 5: To add auto suggest users list in search field (optional)

You can bind auto suggest plugin on input search field with id given below:     



** text **      
` mck-search `     



Contacts Json format is given below as a reference used in **displayName()** and **contactImageSrc()** :     



** text **    
` var contacts = {"user1": {"userId": "user1", "displayName": "Devashish", "photoLink": "https://www.applozic.com/resources/images/applozic_icon.png"}, "user2": {"userId": "user2", "displayName": "Adarsh", "photoLink": "https://www.applozic.com/resources/images/applozic_icon.png"}, "user3": {"userId": "user3", "displayName": "Shanki", "photoLink": "https://www.applozic.com/resources/images/applozic_icon.png"}}; `    



Step 6: Callback function to get contact display name from userId (optional)

You  can write javascript function which return display name on basis of userId 

Example:     



** text **    
` function displayName(userId) {
   var contact = contacts[userId];  // used contacts variable as given above.
   if (typeof contact !== 'undefined') {
       return contact.displayName;
   }
} `    



Step 7: Callback function to get contact image url  from userId (optional)

You  can write javascript function to return user image url on basis of userId 

Example:     



** text **     
` function contactImageSrc(userId) {
    var contact = contacts[userId];   // used contacts variable as given above.
    if (typeof contact !== 'undefined') {
         return contact.photoLink;
    }
 } `     
 
 
 
 
 Step 8: Function to load contact list dynamically (optional)

You can call below function to load contact list by passing contacts json as given in variable contacts     



** text **    
` var contacts = {"contacts": [{"userId": "user1", "displayName": "Devashish", "photoLink": "https://www.applozic.com/resources/images/applozic_icon.png"}, {"userId": "user2", "displayName": "Adarsh", "photoLink": "https://www.applozic.com/resources/images/applozic_icon.png"}, {"userId": "user3", "displayName": "Shanki", "photoLink": "https://www.applozic.com/resources/images/applozic_icon.png"}]};

$applozic.fn.applozic('loadContacts', 'put-contacts-json-here'); // contacts json format given above `    



Step 9: Function to load tab  dynamically (optional)

You can call below function to directly open any contact tab dynamically :    



** text **      
` $applozic.fn.applozic('loadTab', 'put-userId-here'); `     



For more customization  visit:

**https://applozic.readme.io/v1.0/docs/customized-applozic-web-plugin**
  
  
  












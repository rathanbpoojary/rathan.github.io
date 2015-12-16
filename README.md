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
 
 
 
 
 
` <script type="text/javascript" >window.applozic.init({userId: 'user id', appId: 'application key', contactDisplayName: displayName, contactDisplayImage: contactImageSrc, desktopNotification: true});</script> `    



Step 4: Replace the following parameters in script:    



` userId: 'User Unique id',                 // required
appId: 'Your application key'             // required
contactDisplayName: 'Callback function to return contact name by userId',
       // function should receive one parameter i.e userId. Example given in Step 6 (optional)
contactDisplayImage: 'Callback function to return image src of contact by  userId',
      // function should receive one parameter i.e userId'. Example given in Step 7 (optional)
desktopNotification: true or false,
      // only for chrome browser enable or disable desktop notifications for incoming messages (optional) `
  
  
  












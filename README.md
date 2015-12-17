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
` var contacts = {"contacts": [{"userId": "user1", "displayName": "Devashish", "photoLink": "https://www.applozic.com/resources/images/applozic_icon.png"}, {"userId": "user2", "displayName": "Adarsh", "photoLink": "https://www.applozic.com/resources/images/applozic_icon.png"}, {"userId": "user3", "displayName": "Shanki", "photoLink": "https://www.applozic.com/resources/images/applozic_icon.png"}]}; `

` $applozic.fn.applozic('loadContacts', 'put-contacts-json-here'); // contacts json format given above `    



Step 9: Function to load tab  dynamically (optional)

You can call below function to directly open any contact tab dynamically :    



** text **      
` $applozic.fn.applozic('loadTab', 'put-userId-here'); `     



For more customization  visit:

**https://applozic.readme.io/v1.0/docs/customized-applozic-web-plugin**      



### Customized - Applozic-Web-Plugin     



***Welcome to the Applozic-Web-Plugin***

****Applozic messaging jQuery plugin****

Integrate messaging plugin into your web application.

A small jQuery plugin for integrating messaging into your web page to directly send and receive messages to other users via **Applozic** messaging platform and also to see your latest conversations.

Add Applozic messaging plugin into your web application :


Step 1: Register at **https://www.applozic.com/** to get the application key.


Step 2: For customization - where you can modify the UI, checkout **https://github.com/AppLozic/Applozic-Web-Plugin/tree/master/message/advanced**

Open **message.html**  file as a reference and add all scripts and html in your web page in same order as given in message.html. 


Step 3: Initialize plugin using script given below also given in message.html (Initialize once page load completely, preferable in document.ready function) :     



** text **    
` $applozic.fn.applozic({userId: 'customer-1', appId: 'applozic-sample-app',
      ojq: $original,
      readConversation: readMessage,
      contactDisplayName: displayName, 
      contactDisplayImage: contactImageSrc, 
      desktopNotification: true
}); `     



Step 4: Change the following parameters in above script :     



** text **      
` userId: 'User Unique id',                 // required `
` appId: 'Your application key',             // required `
` contactDisplayName: 'Callback function to return contact name by userId', `
      ` // function should receive one parameter i.e userId. Example given in Step:7 (optional) `
` contactDisplayImage: 'Callback function to return image src of contact by userId', `
      ` // function should receive one parameter i.e userId. Example given in Step:8 (optional) `
` desktopNotification: true or false `
`       // for chrome browser enable or disable desktop notifications for incoming messages (optional) `     



*Note : Examples of callback functions and json format is given in below in step 7,8 and also given in message.html

Step5 : To customize layout of plugin :

You can modify **mck-sidebox-1.0.css** class located at :      



** text **     
`  https://github.com/AppLozic/Applozic-Web-Plugin/blob/master/message/advanced/css/app/mck-sidebox-1.0.css `    

Step 6: To add auto suggest users list in search field (optional)

You can bind auto suggest plugin on input search field with id given below:    


** text **     
` mck-search `     

Contacts Json format is given below as a reference used in **displayName()** and **contactImageSrc()** :     


** text **      
` var contacts = {"user1": {"userId": "user1", "displayName": "Devashish", "photoLink": "https://www.applozic.com/resources/images/applozic_icon.png"}, "user2": {"userId": "user2", "displayName": "Adarsh", "photoLink": "https://www.applozic.com/resources/images/applozic_icon.png"}, "user3": {"userId": "user3", "displayName": "Shanki", "photoLink": "https://www.applozic.com/resources/images/applozic_icon.png"}}; `      



Step 7: Callback function to get contact display name from userId (optional)

You  can write javascript function which return display name on basis of userId 

Example:         


** text **     
` function displayName(userId) { `
  `  var contact = contacts[userId];  // used contacts variable as given above.`
   ` if (typeof contact !== 'undefined') { `
`         return contact.displayName; `
   ` } `
`} `     


Step 8: Callback function to get contact image url  from userId (optional)

You  can write javascript function to return user image url on basis of userId 

Example:      


** text **      
` function contactImageSrc(userId) { `
  `   var contact = contacts[userId];   // used contacts variable as given above. `
  `   if (typeof contact !== 'undefined') { `
  `       return contact.photoLink; `
  `   } `
` } `      



Step 9: Function to load contact list dynamically (optional)

You can call below function to load contact list by passing contacts json as given in variable contacts :      



** text **      
` var contacts = {"contacts": [{"userId": "user1", "displayName": "Devashish", "photoLink": "https://www.applozic.com/resources/images/applozic_icon.png"}, {"userId": "user2", "displayName": "Adarsh", "photoLink": "https://www.applozic.com/resources/images/applozic_icon.png"}, {"userId": "user3", "displayName": "Shanki", "photoLink": "https://www.applozic.com/resources/images/applozic_icon.png"}]}; `
 
` $applozic.fn.applozic('loadContacts', 'put-contacts-json-here); // contacts json format given above `       


Step 10: Function to load tab dynamically (optional)

You can call below function to directly open any contact tab dynamically :       


**text **      
` $applozic.fn.applozic('loadTab', 'put-userId-here'); `         




# ANDROID SDK    


### Overview         



Integrate messaging into your mobile apps and website without developing or maintaining any infrastructure. Register at https://www.applozic.com to get the application id.

Instructions for Android: [Android/Getting Started](https://applozic.readme.io/docs/android-gettingstarted)

Want to contribute? Drop us a mail at devashish@applozic.com            




### Getting Started       


**** Quick Start for Applozic Messaging ****      



To integrate messaging into your android app, register at [Applozic](https://www.applozic.com/) to get the application key.

** Step 1: Add the following in build.gradle **:      


** java **     
` compile 'com.applozic.communication.uiwidget:mobicomkitui:3.013' `      


Add the following in gradle android target:      

** java **        
` packagingOptions { `
`    exclude 'META-INF/DEPENDENCIES' `
`      exclude 'META-INF/NOTICE' `
`     exclude 'META-INF/LICENSE' `
`      exclude 'META-INF/LICENSE.txt' `
`     exclude 'META-INF/NOTICE.txt'  `
` } `     


**Step 2: Addition of Permissions, Services and Receivers in androidmanifest.xml**:

Applozic Application Key:     


** java **     
` <meta-data `
   `           android:name="com.applozic.application.key" `
   `           android:value="YOUR_APPLOZIC_APPLICATION_KEY" /> `       
   
Applozic Application URL:        
   
   ** java **     
   ` <meta-data `
   `        android:name="com.applozic.server.url" `
    `       android:value="https://apps.applozic.com" /> `      
    
    
 Applozic Notification package name and launcher icon:        
 
 ** java **       
` <meta-data  `                               
  `        android:name="com.applozic.mobicomkit.notification.icon" `
   `       android:resource="YOUR_LAUNCHER_ICON" /> `
` <meta-data `
   `       android:name="com.package.name" `
   `       android:value="${applicationId}" /> `           
   
   
   **Note**: If you are **not using gradle build** you need to replace ${applicationId}  with your Android app package name


Attachment Folder configuration:         


** java **      
`<meta-data `
  `          android:name="main_folder_name" `
  `          android:value="@string/default_media_location_folder" /> `        
  
  
  
  Define below in your string.xml.          
  
  
  ** java **     
  ` <string name="default_media_location_folder">/<YOUR_APP_NAME></string> `       
  
  
  
  
  Register at [Applozic](https://www.applozic.com/) to get the application key.

Permissions:          





** java **      
` <uses-permission android:name="<APP_PKG_NAME>.permission.C2D_MESSAGE" /> `
` <permission `
  `           android:name="<APP_PKG_NAME>.permission.C2D_MESSAGE" `
   `          android:protectionLevel="signature" /> `
` <uses-permission android:name="com.google.android.c2dm.permission.RECEIVE" /> `
  
` <uses-permission android:name="android.permission.INTERNET" /> `
` <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"  /> `
` <uses-permission android:name="android.permission.READ_CONTACTS" /> `
` <uses-permission android:name="android.permission.WRITE_CONTACTS" /> `
` <uses-permission android:name="android.permission.VIBRATE"/> `
` <uses-permission android:name="android.permission.CALL_PHONE"/> `
` <uses-permission android:name="android.permission.READ_PROFILE"" /> `
` <uses-permission android:name="android.permission.READ_PHONE_STATE"/> `
` <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" /> `
` <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" /> `
` <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" /> `
` <uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE"/> `        



Broadcast Registration For PushNotification:        


** java **    
` <receiver `
     `  android:name="com.applozic.mobicomkit.uiwidgets.notification.MTNotificationBroadcastReceiver"> `
     ` <intent-filter> `
     `      <action android:name="${applicationId}.send.notification"/> `
     ` </intent-filter> `
` </receiver> `        


**Note**: If you are **not using gradle build** you need to replace ${applicationId}  with your Android app package name



Paste the following in your androidmanifest.xml:       




** java **      
` <activity android:name="com.applozic.mobicomkit.uiwidgets.conversation.activity.ConversationActivity" `
  `  android:configChanges="keyboardHidden|orientation|screenSize" `
  `  android:label="@string/app_name" `
  `  android:parentActivityName="<APP_PARENT_ACTIVITY>" `
  `  android:theme="@style/MobiComAppBaseTheme"> `
   ` <!-- Parent activity meta-data to support API level 7+ --> `
    `    <meta-data `
`                 android:name="android.support.PARENT_ACTIVITY" `
 `                android:value="<APP_PARENT_ACTIVITY>" /> `
  `</activity> `
                   
`<activity `
 `           android:name="com.applozic.mobicomkit.uiwidgets.people.activity.MobiComKitPeopleActivity" `
 `           android:configChanges="keyboardHidden|orientation|screenSize" `
 `           android:label="@string/activity_contacts_list" `
 `           android:parentActivityName="com.applozic.mobicomkit.uiwidgets.conversation.activity.ConversationActivity" `
 `           android:theme="@style/ContactTheme" `
 `           android:windowSoftInputMode="adjustResize"> `
 `           <!-- Parent activity meta-data to support API level 7+ --> `
 `           <meta-data `
 `               android:name="android.support.PARENT_ACTIVITY" `
 `               android:value="com.applozic.mobicomkit.uiwidgets.conversation.activity.ConversationActivity" /> `

`            <intent-filter> `
`               <action android:name="android.intent.action.SEARCH" /> `
`            </intent-filter>`
`
`           <meta-data `
`                android:name="android.app.searchable" `
`                android:resource="@xml/searchable_contacts" /> `
`</activity> `

`<activity `
`           android:name="com.applozic.mobicomkit.uiwidgets.conversation.activity.FullScreenImageActivity" `
`            android:configChanges="keyboardHidden|orientation|screenSize" `
`            android:label="Image" `
`            android:parentActivityName="com.applozic.mobicomkit.uiwidgets.conversation.activity.ConversationActivity" `
`            android:theme="@style/MobiComAppBaseTheme"> `
`            <!-- Parent activity meta-data to support API level 7+ --> `
`            <meta-data `
`                android:name="android.support.PARENT_ACTIVITY" `
`                android:value="com.applozic.mobicomkit.uiwidgets.conversation.activity.ConversationActivity" /> `
`</activity> `
                   
`<service `
`            android:name="com.applozic.mobicomkit.api.conversation.MessageIntentService" `
`            android:exported="false" /> `

`        <receiver android:name="com.applozic.mobicomkit.broadcast.NotificationBroadcastReceiver"> `
`            <intent-filter> `
`                <action android:name="applozic.LAUNCH_APP" /> `
`            </intent-filter> `
`            <meta-data `
`                android:name="activity.open.on.notification" `
`                android:value="com.applozic.mobicomkit.uiwidgets.conversation.activity.ConversationActivity" /> `
`        </receiver> `

`       <receiver android:name="com.applozic.mobicomkit.broadcast.TimeChangeBroadcastReceiver"> `
`            <intent-filter> `
`                <action android:name="android.intent.action.TIME_SET" /> `
`                <action android:name="android.intent.action.TIMEZONE_CHANGED" /> `
`            </intent-filter> `
`        </receiver> `

`         <receiver android:name="com.applozic.mobicomkit.broadcast.ConnectivityReceiver"> `
`            <intent-filter> `
`                <action android:name="android.net.conn.CONNECTIVITY_CHANGE" /> `
`            </intent-filter> `
`        </receiver> `           







Replace APP_PARENT_ACTIVITY with your app's parent activity.        

**Step 3: Register user account**:     



** java **        
` UserLoginTask.TaskListener listener = new UserLoginTask.TaskListener() {  `

`   @Override `
`   public void onSuccess(RegistrationResponse registrationResponse, Context context) { `
     
            
`  } `

`   @Override `
`   public void onFailure(RegistrationResponse registrationResponse, Exception exception) { `
                  
`   } `
` }; `

` User user = new User(); `
` user.setUserId(userId); `
` user.setEmail(email); //optional `

` new UserLoginTask(user, listener, this).execute((Void) null); `                   


If it is a new user, new user account will get created else existing user will be logged in to the application.

**Step 4: Updating GCM registration id:**

In case, if you don't have the existing GCM related code, then copy the files from https://github.com/AppLozic/Applozic-Android-SDK/tree/master/app/src/main/java/com/applozic/mobicomkit/sample/pushnotification
to your project and add the following lines in the "onSuccess" method mentioned in Step 3.

Register project at https://console.developers.google.com and enable GCM service.
Replace the value of GCM_SENDER_ID in GCMRegistrationUtils.java with your own project gcm sender id.
SenderId is a unique numerical value created when you configure your API project (given as "Project Number" in the Google Developers Console).            




** text **         
` GCMRegistrationUtils gcmRegistrationUtils = new GCMRegistrationUtils(activity); `
` gcmRegistrationUtils.setUpGcmNotification(); `            


If you already have a GCM code in your app, then copy the following code at the place where you are getting the GCM registration id.       
** java **     
` PushNotificationTask pushNotificationTask = null `
`       PushNotificationTask.TaskListener listener = new PushNotificationTask.TaskListener() { `

`               @Override `
`                public void onSuccess(RegistrationResponse registrationResponse) { `
`                } `

`                @Override `
`                public void onFailure(RegistrationResponse registrationResponse, Exception exception) { `
`               } `
`            }; `

`            pushNotificationTask = new PushNotificationTask(pushnotificationId, listener, mActivity); `
`            pushNotificationTask.execute((Void) null); `        



**Step 5: Handling push notification
**
Add the following in your GcmBroadcastReceiver's onReceive method.     





** java **       
` if(MobiComPushReceiver.isMobiComPushNotification(context, intent)) { `
 `           MobiComPushReceiver.processMessageAsync(context, intent); `
 `           return; `
` } `       



**Step 6: For starting the messaging activity**:        

** java **      
`Intent intent = new Intent(this, ConversationActivity.class); `
 ` startActivity(intent); `        
 
 
 
 For starting individual conversation thread, set "userId" in intent:        
 
 ** java **           
 `Intent intent = new Intent(this, ConversationActivity.class); `
` intent.putExtra("userId", "devashish@applozic.com"); `
` intent.putExtra("displayName", "Devashish Mamgain"); //put it for displaying the title. `
` startActivity(intent); `       



For easy insertion of Admin/Support Contact information, please changes following values in string.xml. You can take sample app method ( MainActivity.buildSupportContactData() ) as reference for contact information insertion.          




** java **          
` <string name="support_contact_display_name">AppLozic Support</string> `
` <string name="support_contact_userId">applozic</string> `
` <string name="support_contact_emailId">devashish@applozic.com</string> `
` <string name="support_contact_number">918042028425</string> `
` <string name="support_contact_image_url">R.drawable.ic_launcher</string> `       


support_contact_image_url also supports url eg:
 https://www.applozic.com/resources/sidebox/images/applozic.png

**Step 7: On logout, call the following**:       



** java **       
 new UserClientService(this).logout();      
 
 
 
 Note: If you are running ProGuard, please add following lines:        
 
 
 
 
 ** java **     
`  #keep json classes `
 `    -keepclassmembernames class * extends com.applozic.mobicomkit.api.JsonMarker { `
`	!static !transient <fields>; ` 
 `    } `

   `  #GSON Config `
   `  -keepattributes Signature `
   `  -keep class sun.misc.Unsafe { *; } `
   `  -keep class com.google.gson.examples.android.model.** { *; } `
   ` -keep class org.eclipse.paho.client.mqttv3.logging.JSR47Logger { `
   `     *; `
   ` } `           
   
   
   
   
   
   Trying out the demo app:

Open project in Android Studio to run the sample app in your device. Send messages between multiple devices. 


Display name for users:
You can either choose to handle display name from your app or have Applozic handle it.
From your app's first activity, set the following to disable display name feature:
ApplozicClient.getInstance(this).setHandleDisplayName(false);
By default, the display name feature is enabled.

UI Customization:

Clone the repository : [https://github.com/AppLozic/Applozic-Android-SDK](https://github.com/AppLozic/Applozic-Android-SDK)

Import [MobiComKitUI Library](https://github.com/AppLozic/Applozic-Android-SDK/tree/master/mobicomkitui)  into your android project and add the following in the build.gradle file:

compile project(':mobicomkitui')


MobiComKitUI contains the ui related source code, icons, layouts and other resources which you can customize based on your design needs.

For your custom contact list, replace MobiComKitPeopleActivity with your contact list activity.

Sample app with integration is available under [app](https://github.com/AppLozic/Applozic-Android-SDK/tree/master/app)

*Note : If you want to customize your contact list please click on [Building customize contact list](https://applozic.readme.io/docs/getting-started-with-contacts)              






### MobiComKit module             



****Applozic messaging jQuery plugin****          



Classes ending with *ClientService.java interacts with the server.


**1. Account registration**:      
   
Class: com.applozic.mobicomkit.api.account.register.RegisterUserClientService      

** java **          
` new RegisterUserClientService(activity).createAccount(USER_EMAIL, USER_ID, USER_PHONE_NUMBER, GCM_REGISTRATION_ID);   `      
  

**2. Send message**:    

Class: com.applozic.mobicomkit.api.conversation.MobiComConversationService         


**  java **      
`  public void sendMessage(Message message) { `
`  ... `
`  } `     


Example: new MobiComConversationService(activity).sendMessage(new     
Message("contact@applozic.com", "hello test"));         



**3. Message list**:      

Class: com.applozic.mobicomkit.api.conversation.MobiComConversationService

  
i) Get single latest message from each conversation        



** java **      
`public synchronized List<Message> getLatestMessagesGroupByPeople() { `
` ... `
`} `               



ii) Get messages of logged in user with another user by passing userId, startTime and      
 endTime. startTime and endTime are considered in time in milliseconds from 1970.       



** java **    
` public List<Message> getMessages(String userId, Long startTime, Long endTime) { `
`    ... `
` }     `           




### Building Own Contact List             



***Building your own contacts***         



You can build your own contact in two easy steps by using AppContactService.java api. Sample method **buildContactData()** for adding contacts is present in sample app MainActivity.java.

**Step 1: Build your contact object:**         



** text **      
` Contact contact = new Contact(); `
` contact.setUserId(<userId>); (Unique ID to identify contact ) `
` contact.setFullName(<full name of contact>); `
` contact.setEmailId(<EmailId>); `
` contact.setImageURL(<image http URL OR android resource drawable  >); `
` (in case of drawable use R.drawable.<resource_name>) `      


Example :        


** text **      
` Contact contact = new Contact(); `
` contact.setUserId("adarshk"); `
` contact.setFullName("Adarsh"); `
` contact.setImageURL("R.drawable.applozic_ic_contact_picture_holo_light"); `
` contact.setEmailId("applozic.connect@gmail.com"); `      


**Step 2: add contacts :**

After creating contact object in step1, add your contact using AppContactService.java add() method.
 
Example :        



** text **     
` Context context = getApplicationContext(); `
` AppContactService appContactService = new AppContactService(context); `
` appContactService.add(contact); `        




**AppContactService.Java at a glance**



AppContactService.java provides methods you need to add, delete and update contacts.

**add(Contact contact)** :  Add single contact.

**addAll(List<Contact> contactList)** : Add multiple contacts.

**deleteContact(Contact contact)** : Delete contact.

**deleteContactById(String contactId)** : Delete contact by Id.

**getContactById(String contactId )** : Read contact by Id.

**updateContact(Contact contact)** : Update contact.

**upsert(Contact contact)** : update or insert contact.       



# PLATFORM API     

### Overview        


Integrate native app message communication to your product without developing and maintaining any infrastructure.
Are you looking for platform-native Sdks to integrate into your app. All you need to do is include the Applozic SDK as a library in your project and a couple of lines of code. We will take care of rest things from server hosting, database, maintenance to analytics.     


### Rest API         



***Create User Account***        



**Create User Account URL**: https://apps.applozic.com/rest/ws/registration/v1/register
**Method Type**: POST
**Content-Type**: application/json, application/xml

**Parameters**: user (json object) will be passed as a parameter with following properties :-         




| Parameter  | Required | Default | Description |
| ------------- | ------------- | ------------- | ------------- |       
| userId  | Yes  |   | User name  |
| emailId  | No  | null  | User email address  |
| password  | No  | null  | User account password  |
| registrationId  | No  | null  | User device registrationId  |
| contactNumber  | No  | null  | User contact number  |
| countryCode  | No  | null | User country code  |
| emailVerified  | No  | false  | If user email address is verified then true or else false  |
| timezone  | No  | Asia/Calcutta  | User device timezone  |
| roleName  | No  | USER  | Value should be USER  |
| applicationId  | Yes  |   | Key of the application which you had created.  |
| deviceType  | Yes  |   | Value should be 1  |       



**Parameter Example**:    


** json **     
` {"userId":"userUniqueId","password":"password","deviceType":1,"emailId":"abc@gmail.com","applicationId":"applozic-sample-app","emailVerified":1} `      


**Response**: registrationResponse (json object) will be passed as a response to request with following properties :-         



| Response  | Description |
| ------------- | ------------- |
| message | Description whether user successfully registered or not. One of the following :REGISTERED, INVALID_EMAILID, INVALID_APPLICATIONID, PASSWORD_REQUIRED, UPDATED |
| deviceKeyString | User device key  |
| suUserKeyString  | User key  |
| LastSyncTime  | Time in miliseconds when user device last synced with server  |          



***Note** :- If registration process failed then only message property come in json response with description

Create Account Response Example:

{"deviceKeyString":"ahBzfm1vYmktY29tLWFscGhhciYLEgZTdVVzZXIYgICAgNXOoQgMCxIGRGV2aWNlGICAgICAgIAKDA",
"lastSyncTime":"1437221081897","message":"UPDATED","suUserKeyString":
"ahBzfm1vYmktY29tLWFscGhhchMLEgZTdVVzZXIYgICAgNXOoQgM"}          




****Authentication****      


***
































    


    
  

    










 
 







   









  
  
  
  
   

  
  
  












CS52 Workshops: Chrome Extensions!!!!!!!!
====================

Overview
---------------------
This tutorial will teach you how to setup a basic Chrome Extension that displays a specified image upon loading certain pages.


Let's gooooooo! 
Part 1 of 3 (Setup)
---------------------
### Step 1: Make a directory in terminal (name it however you like!)

    mkdir 4_28_chrome_extension
    
### Step 2: Create manifest.json file and open it:

    touch manifest.json

This manifest.json file is necessary for every chrome extension. It holds the metadata on the extensions's information, such as title, description, etc.

Open manifest.json and paste this code into the file: 

    {
        "manifest_version": 2,
        "name": "Custom Google Homepage",
        "description": "This extension does shows a picture upon navigation to Google",
        "version": "1.0",

        "page_action": {
        "default_title": "My custom google page!"
        }
       }


### Step 3: Connect extension to Chrome 
1. Go to **chrome://extensions**
2. Toggle on the the "developer mode" in the upper right corner as shown below:

![](https://i.imgur.com/WWFnigM.png)

### Step 4: Click "Load Unpacked" and select your directory
This step is to check that the manifest.json file can be loaded correctly as an extension in your browser. If there are any errors, it will be displayed (ie missing a file, cannot read,etc). If there are no errors, the extension will load automatically.

Toggle the checkbox in our extension to make sure it is on. 

![](https://i.imgur.com/buUQyqX.png)

Yay! now your extension

### Step 5: 
Add content scripts to the manifest.json after "version": and before "page_action"{

    ,
    "content_scripts": [
        {
        "matches": ["https://www.google.com/*"],
        "css": ["main.css"]
        }
        ],

The Matches part refers to the URL what we want our extension to modify/personalize. Here, we are setting it to google.com. We can link other files to content scripts. 
Since we are changing the background, let's add a css file.

### Step 6: Create the CSS file!

    touch main.css
In this case, we want our personalized page to have unique background:


    body#gsr.hp.vasq{
        background-image: url("https://wallpaperaccess.com/full/1331874.jpg");
       }
       div.gb_xe.gb_R.gb_Me.gb_Ee {
        font-weight: bold;
        font-size: 15px;
       }

feel free to change the url to whatever picture you would like. Just make sure the url is of an image only.

### Step 7: You're done!!
1. Save your files
2. Go back to **chrome://extensions** in your browser
3. Press "load unpacked" and reload your directory
4. Navigate to google.com and bask in the majesty of this golden retriever (or whatever picture you specified)!!



Optional Extra Fun - Connecting APIs??
---------------------
Inspect the site for an id or class of the element you want to customize and add it to your css file. 


### Reflection Questions:

What functionality would you implement in an extension that could help in the day-to-day? Remember, an extension ought to fill a single purpose that's easy to understand and narrowly defined!

Think about your favorite extension or a popular extension. Try to explain the features of the extension and how it was implemented. 




**Resources: **
https://medium.com/@LindaVivah/the-beginner-s-guide-build-a-simple-chrome-extension-in-minutes-498308ea406a
https://www.youtube.com/watch?v=YQnRSa8MGwM&list=PLRqwX-V7Uu6bL9VOMT65ahNEri9uqLWfS&index=7 
https://developer.chrome.com/extensions/browserAction


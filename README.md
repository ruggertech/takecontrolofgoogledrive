
# Take Control Of Google Drive
Are you missing some files from your google drive?  
Maybe the sync app did it?  
Do you want to be SURE all your pictures and documents are where you placed them!

This is a simple code that show ALL your google drive activity entries, you know, the bar on the right, you have in your google drive.
Only it shows them as text so you could parse and query them using text editors/tools.

I took the basic sample of google activity.list from here:  
https://developers.google.com/google-apps/activity/v1/quickstart/nodejs   
added "paging" and an if clause to give me back all of the "trash" actions.

It will use your own credentials and store them locally.

I needed this ability when I discovered some files in my drive were somehow deleted accidently and I wanted to get a better control of my drive.
Feel free to use.

## Prerequisites

To run this code, you'll need:

* Node.js installed.
* The npm package management tool (comes with Node.js).
* Access to the internet and a web browser.
* A Google account with Google Drive enabled.


## Installation
1. Clone or download this repository.
2. Get your credentials from google, Step 1 here: https://developers.google.com/drive/v3/web/quickstart/nodejs
3. place the client_secret.json file in the working directory
4. In the working directory use ```npm install```
5. Use ```npm start``` or ```node main.js``` to start the app.
6. the FIRST TIME you run it, the command line will contain a link, paste it into your browser - this is the link google provide for OAuth2
7. Give google all the permissions they require for the code to access your GOOGLE DRIVE in readonly mode.  Google will show a code, paste it into the command line.
8. Run the app again from the command line.

## Output
You should now see all of your "trash" (deleting a file) activities in google drive.  

Should you not see ANYTHING --> relax 
remove the "if" clause in line 132  
```(if (event.primaryEventType == "trash" && -1 === target.mimeType.indexOf("application")) {})``` 

Run again, it will now print all of the events.
Enjoy, let me know if you have questions.

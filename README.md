# webapp-for-aslproject
WIth this, I'm integrating my current model which I saved in JSON format into a web application for anyone to access as long as they are given a link and if my server is active. Credits to Nicholas Renotte for helping me further develop this project to a web-application.

CREDIT: https://github.com/nicknochnack/TFODApp

For those interested in using this repository specifically and want to make improvements or changes, do the following mentioned here.

The differences within my repository that instead of using IBM cloud, I used Google Cloud to create a bucket, linked it with the given CORS configurations to enable "GET" requests to the web-app. Which was only possible after learning more about the Google CLI commands.

Another change within my repository is that I've also modified the CORS configuration file to work with Google Cloud which can be seen directly within the corsconfig.json file.

Linking the CORS configuration with the bucket was done by this command "Gsutil cors set corsconfig.json gs://website-deployment-asl" - This command sets the CORS configurations for the bucket specificed within the JSON file. To use this command, one needs to download Google CLI into their system and set a directory to it via the PATH, eventually linking it to the repository via VSCODE or any other code editor in the terminal and also assuming that one has already created a bucket.

Linking to the code editor terminal can be done with the Google CLI command - "gcloud auth login" 
This will redirect you to Google to link the terminal with the SDK and then back to your terminal with your bucket and the code linked.

After this, one can start the react project with the command "npm start" - You'll need to have React.js installed for this to work.

After loading up the project onto your browser, you most likely won't have the object detection capabilities of the model, the reason as to why this is the case is because there are three following objects that outputs are unique and the given ones within the repository work for myself, therefore trial and error will be required to get the object detection working. This can be done by going to the app.js file and finding the lines of code referencing boxes, classes and scores these have  unique indexes, and traversal through the object indexes will be required to find the correct values for the objects. In my case, boxes was index 4, classes was index 7 and scores was index 1.

Traversal can be done via - "console.log(await obj["input index"].array())" only do this after loading up the react project on your browser, and then use inspect element and check the output of the index via the console. 

TIPS: Classes are whole numbers, boxes are already processed values, and scores is a confidence metric that top value is the highest and bottom value being the lowest.



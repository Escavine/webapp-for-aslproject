## Web Application for ASL Project
This project is a web application that integrates a machine learning model trained on the American Sign Language (ASL) dataset. The model is saved in JSON format and can be accessed through the web application as long as the server is active, this is for my A Level Computer Science project.

# Acknowledged changes
Instead of using IBM Cloud, this project uses Google Cloud to create a bucket and link it with the given CORS configurations to enable "GET" requests to the web application and allow for object detection.

Another change within this repository is that the corsconfig.json has been modified so it works for Google Cloud.

This repository has the 8 ASL symbols within the labelmap, therefore those won't need changing unless you are using another model.

## Getting Started Prerequisites
- Visual Studio Code
- Google Cloud 
- Google CLI 
- React.js 
- Knowledge of the object detection model outputs (boxes, classes, and scores)
- Setting up the Bucket and CORS Configurations
- Create a bucket on Google Cloud.

## Tutorial

STEP 1: Download Node.JS and download dependencies on the terminal with the comamnd...

```npm install ```

STEP 2: Create a bucket within Google Cloud

STEP 3: After creation of bucket, go to the app.js file and get the public link to the JSON model within the bucket and paste that into the tf.loadGraphModel function.

STEP 4: Download the Google CLI into your system and set a directory to it via PATH.

STEP 5: Ensure that the Google Bucket has public access by allowing allUsers to access the bucket, this way the CORS configuration can work with the bucket to access resources from other websites.

STEP 6: Link the code editor terminal with the Google SDK with this command, which will lead you to the login screen on your web browser to confirm your details and then once successful will lead you back to the terminal.

```gcloud auth login ```

STEP 7: Set the directory to the repository in the terminal and run the command below. This command sets the CORS configurations for the specified bucket within the JSON file.

```gsutil cors set corsconfig.json gs://[BUCKET-NAME]```


## Running the Web-App
STEP 8: Load up the project onto your browser by running the command

```npm start ```


STEP 9: Traverse through the object indexes to find the correct values for the objects (boxes, classes, and scores). You can use the following command to check the output of the index via the console when you use inspect element after starting the react project. The reason as to why this is the case is that each of the object indexes are unique to most systems, the ones that worked for me are index 4 for boxes, index 7 for classes and index 1 for scores.

``` console.log(await obj["input index"].array()) ```

## Tips
Classes are whole numbers, boxes are already processed values, and scores are a confidence metric where the top value is the largest and the bottom value is the smallest.

## Contributing
If you would like to make any improvements or changes to the repository, please feel free to do so. You can fork the repository and create a pull request to merge your changes into the main branch.

## Credits
- https://github.com/nicknochnack/TFODApp - Nick Rennotte

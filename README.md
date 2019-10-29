# Video Doorbell, Lab 7

*A lab report by John Q. Student*

### In This Report

1. Upload a video of your version of the camera lab to your lab Github repository
1. As usual, update your class Hub repository to add your [forked IDD-Fa18-Lab7](/FAR-Lab/IDD-Fa18-Lab7) repository.
1. Answer the questions in-line below on your README.md.

## Part A. HelloYou from the Raspberry Pi

**a. Link to a video of your HelloYou sketch running.**

[hello you](https://photos.app.goo.gl/bMa4ph3JhhSaF7SN6)

## Part B. Web Camera

**a. Compare `helloYou/server.js` and `IDD-Fa18-Lab7/pictureServer.js`. What elements had to be added or changed to enable the web camera? (Hint: It might be good to know that there is a UNIX command called `diff` that compares files.)**

In order to enable the camera by using the arduino button, I commented out the "LedOn" function, and used this message as the listener for the takePicture function. In doing so, any time the button is pressed down a picture is taken and the doorbell is rang.

**b. Include a video of your working video doorbell**

## Part C. Make it your own

**a. Find, install, and try out a node-based library and try to incorporate into your lab. Document your successes and failures (totally okay!) for your writeup. This will help others in class figure out cool new tools and capabilities.**

I decided to use an [NPM package](https://www.npmjs.com/package/@google-cloud/vision#before-you-begin) that integrated with Google's Vision API. To do so I first had to go to my Google Cloud API dashboard, create an app that used the vision API and set up authentication through a service account. 

Once this was completed, I started to play around with the API, and quickly realized I had no completed the authentication step. I had create a .env file to store the credentials I had created. However the package didn't seem to like my .env setup, so I instead had to google how to pass env variables via command line. This resolved the authenticaion issues, and I was able to test the API again.

I quickly realized however that a webcam that returns overexposed images is a terrible use case for any vision API. I was initially trying out the facial detection API, but thought perhaps the tagging API would be more useful given the state of the images. This proved to be somewhat accurate, but most images still return the same taggings.


**b. Upload a video of your working modified project**

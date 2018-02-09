# Lung-Xray-Diagnostic-Android

**DESCRIPTION** 

This app, intended as a prototype and NOT meant to actually function as a diagnostic tool, runs a MobileNet model that was trained on approximately 200 NIH lung x-ray images to diagnose whether a particular lung x-ray contains a mass, a nodule, or neither. The app opens to the phone's camera function, which can be pointed at the lung x-ray. The screen will show the result, as follows:

![What the tool looks like in use](https://github.com/priyankaincode/Lung-Xray-Diagnostic-Android/blob/master/images/IMG_1275.jpg?raw=true) 
  
 **INSTALLATION AND USAGE**
 
 To install this app, you simply have to load the file onto your Android phone (whether by emailing it to yourself, or opening GitHub in your mobile browser, however) and then tap the file to install it.
 
 To use, simply open the app on your phone and point the camera at a picture of a lung x-ray.
 
 
 **ANALYSIS**
 
 Because this model uses a [MobileNet](https://research.googleblog.com/2017/06/mobilenets-open-source-models-for.html) with its final layer retrained to recognize the difference between a mass, a module, and nothing on an x-ray. The resulting accuracy is horrendous, actually - somewhere around 35%. You would be better off asking a random person on the street if you had cancer!!!!
 
 There are many reasons for why it functions so poorly, but the biggest one is that MobileNet is not a good starting point for a transfer learning application in this case. MobileNet was trained on ImageNet, which just recognizes a variety of everyday objects. It was not designed to be used in any kind of healthcare setting, and thus does not possess the ability to finely differentiate between x-rays. Another reason is that I used a very small training set - only about 200 images in total - that were also sized down to about 224 pixels (to comply with MobileNet's requirements). One way to improve the accuracy would be to just retrain the algorithm on a larger data set, as well as to play with the learning rate and other hyperparameters to be able to more accurately diagnose a tool. I will work on that as time allows.
 
 Also, the designer in me has to say that the UI/UX definitely needs a lot of work :) But for a proof-of-concept prototype, this is just fine!
 
 **CREDIT**
 
What a wonderful resource Google's CodeLabs are! I followed the TensorFlow for Poets Codelabs ([1](https://codelabs.developers.google.com/codelabs/tensorflow-for-poets/index.html#0) and [2](https://codelabs.developers.google.com/codelabs/tensorflow-for-poets-2/#0)) and modified it for my own purposes. All images are courtesy of the [NIH](https://www.nih.gov/news-events/news-releases/nih-clinical-center-provides-one-largest-publicly-available-chest-x-ray-datasets-scientific-community), and the original model comes from the [Google Research](https://research.google.com/) team.

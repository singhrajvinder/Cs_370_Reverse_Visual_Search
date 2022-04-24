# CS370 Reverse Visual Search Project
1. rs2264@njit.edu - Rajvinder Singh - AWS
2. nsd33@njit.edu - Nikita Dubinin
3. ajr72@njit.edu - Ashutosh Rana

Colab notbook:  

# Documentation

## Start 

We start this project off by first downloading the LFW Funneled dataset provided. here: http://vis-www.cs.umass.edu/lfw/ we chose LFW because they rotate the image so the face is always facing upright so it is easier to recognise. even the smalest tilt can change the distance between features extracted from the faces. thus having a straight up face is necessary. another thing that is neciserry is if the person is facing the camera or not. if you only see one side of the face the detector will have trouble trying to find a match of the person. as you can see with Arminio Fraga int query image only half of his face is visible thus the mathces where not that great.

## Creating baseline

For the baseline we decided to use the basic tensorflow model to do the recognition of features. this is due to it not being the best and not the worst either. but when it comes to faces it can not do much except put features on eyhes and mouth. only rarly does that work as you can see in the baseline exsamples above. 
1. We first went through all the images and got all the featueres and stored them in a list so we can access them later. 
2. we get the query image and get its features just like before
3. we then find the distance between eatch feature and then normalise it with numpy so that its one number so we can easly sort in assending order. 
4. then we get the lowset 20 images and display to the user

As we have said above the basline does not do a really good job of really matching faces to faces but as a basline to reconice faces its great.

Read inline comments for step by step of the code.

## Improving baseline with face recognition api

To improve our basline we used Face Recognitioin's Api: https://github.com/ageitgey/face_recognition?ref=hackernoon.com becasue it actually worked in our enviornment and we saw actual results. as we didnt have to use anyother models we could just call Face Recognition whcih would boudn box the faces and plot important facial features at once. As this was an all in one the time to go throuhg all the images and find all features drastically deacreased. even then it would still be idle to have the features ready for all the images before you start querying.
1. implement Face recfnition api instead of tensorflow model 
2. do the same for the query image to find its features
3. now just like before we find the distance between eatch featuer and then normalise it with numpy
4. just like before we show the lowest 20 distanced featured images

This time around you will actually see same faces and similar faces as compared to the baseline. 

Read inline comments for step by step.

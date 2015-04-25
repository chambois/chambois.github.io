---
layout: post
title:  "Promises"
date:   2014-06-02 15:06:00
categories: javascript
---

The term has flown passed my awareness a few times. A couple of readings here
and there but it still hasn't sunk in. So what the hell are promises anyway?

On our current project we ran into a situation that required a callback to
fire after another callback. Basically we had to post some data via ajax, then
upon success we had to carry out another post. Upon running this scenario
passed our uber tech lead he mentioned this elusive concept of promises. So
with that here is an attempt to try to get my head around it and hopefully
with my thick skull if it penetrates into my brain it should pass into yours
too.

## Our problem
We are currently writing the functionality to upload an image to our website.
We're using an external CDN to host the image and a custom-built
content-service to store all our other content (text, meta-data, etc) separate
from our presentation.

First we need to upload the image to the CDN (first POST). Upon success, we'll
get the URI of our image. Following that we then need to take that URI, along
with some other meta-data (not important here) and send that to our
content-service via our internal API (second POST).

## The Callback solution
    // Callback 1
    function cdnSuccessCallback(response) {
      uploadImageToContentService(response.data); 
    } 

    // Callback 2
    function csSuccessCallback(response) {
      view.presentData(response.data);
    }

    function uploadImageToCdn() {
      $.post('/cdn-upload-uri', {/*data*/}, cdnSuccessCallback);
    }
    
    function uploadImageToContentService(imageUri) {
      $.post('/internal-api-uri', {/*data*/}, csSuccessCallback);
    }

    ...

    uploadImageToCdn();   // Start the ball rolling...

## The Promises solution
    $.post();

## Main event
* inciting incident come to a head (aka the climax). This is either the answer
to the question we asked in the second beat or where the protagonist solves
his or her dilemma — a pivot or a change (even if it's just a shift in
attitude) should occur.

* Promises
  * 

## Summary (Resolution)
* highlight what makes the story unique. If you've just described a failure or
challenge, this would be the time to reflect on what you learned. 



# Image Resizer And Positon Watermark for Cordova #
By: Protonet GmbH

Authors: Joschka Schulz

## Adding the Plugin ##

Use the Cordova CLI and type in the following command:

```
// This plugin uses the cordova-plugin-camera
cordova plugin add cordova-plugin-camera

// This plugin
cordova plugin add https://github.com/azhengyongqin/cordova-plugin-image-resizer-watermark
```

## Sample Code

At the moment the plugin is available on android, iOS and windows

### resize

    window.ImageResizer.resize(options, success, failed);
    
### Options
  - **position**(String):The position of geographic location information
  - **longitude**(String)
  - **latitude**(String)
  - **uri**(String): The Uri for the image on the device to get scaled
  - **folderName**(String, required on Android): The name of the folder the image should be put in **android only**
  - **fileName**(String, required on iOS): A custom name for the file. Default name is a timestamp.
  - **quality**(Number): Quality given as Number for the quality of the new image **android and iOS only**
  - **width**(Number): The width of the new image,
  - **height**(Number): The height of the new image
  - **base64**(Boolean): Whether or not to return a base64 encoded image string instead of the path to the resized image **iOS only**

### Android Example
    var options = {
          uri: uri,
          folderName: "Protonet Messenger",
          quality: 90,
          width: 1280,
          height: 1280,
          base64: true};

    window.ImageResizer.resize(options,
      function(image) {
         // success: image is the new resized image
      }, function() {
        // failed: grumpy cat likes this function
      });

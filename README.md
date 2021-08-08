# Animated
*Link to preview website: https://s-codes14.github.io/animated*<br>
***Note this wasn't originally created by me, It is made from open source and some blog posts***

Animated takes a 2D vector illustration and animates its containing curves in real-time based on the recognition result from PoseNet and FaceMesh. It borrows the idea of skeleton-based animation from computer graphics and applies it to vector characters.

This is running in the browser in realtime using [TensorFlow.js](https://www.tensorflow.org/js). Check out more cool TF.js demos [here](https://www.tensorflow.org/js/demos).

*This is not an officially supported Google product.*
*But does use google's open source*

In skeletal animation a character is represented in two parts:
1. a surface used to draw the character, and 
1. a hierarchical set of interconnected bones used to animate the surface. 

In Animated, the surface is defined by the 2D vector paths in the input SVG files. For the bone structure, Animated provides a predefined rig (bone hierarchy) representation, designed based on the keypoints from PoseNet and FaceMesh. This bone structure’s initial pose is specified in the input SVG file, along with the character illustration, while the real time bone positions are updated by the recognition result from ML models.





The camera  animates a 2D avatar in real-time from a webcam video stream and a static place.



## Build And Run

Install dependencies and prepare the build directory:
yarn
```sh
yarn
```
npm
```sh
npm install
```

To watch files for changes, and launch a dev server:
yarn
```sh
yarn watch
```
npm 
```sh
npm run watch
```

## Platform support

Demos are supported on Desktop Chrome and iOS Safari.

It should also run on Chrome on Android and potentially more Android mobile browsers though support has not been tested yet.

# Animate your own design

1. Download the [sample skeleton SVG here](/resources/samples/skeleton.svg).
1. Create a new file in your vector graphics editor of choice. Copy the group named ‘skeleton’ from the above file into your working file. Note: 
	* Do not add, remove or rename the joints (circles) in this group. Animated relies on these named paths to read the skeleton’s initial position. Missing joints will cause errors.
	* However you can move the joints around to embed them into your illustration. See step 4.
1. Create a new group and name it ‘illustration’, next to the ‘skeleton’ group. This is the group where you can put all the paths for your illustration.
    * Flatten all subgroups so that ‘illustration’ only contains path elements.
    * Composite paths are not supported at the moment.
    * The working file structure should look like this:
	```
        [Layer 1]
        |---- skeleton
        |---- illustration
              |---- path 1
              |---- path 2
              |---- path 3
	```
1. Embed the sample skeleton in ‘skeleton’ group into your illustration by moving the joints around.
1. Export the file as an SVG file.
1. Open [Animated camera demo](https://s-codes14.github.io/animated/camera.html). Once everything loads, drop your SVG file into the browser tab. You should be able to see it come to life :D

# Credits
 * (all credits go to open source)
 * google developers platform
 * stackoverflow
 * tensorflowjs(greate softwre by the way)
 * blogs from medium.com and dev.to

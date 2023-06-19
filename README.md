Camera.js
=========

A simple wrapper around the HTML5 getUserMedia API, offering cross-browser access to the user's webcam video stream. 

## Usage

Upon initalization, the library asks the user for permission, sets up the necessary getUserMedia code and starts the stream. All parameters are optional, their default values are explained below.

The `onFrame` callback function is called each time there is a new frame to be processed, with respect to the `fps` option.

If you want the video stream to also be rendered in a `<canvas>` element, set the `targetCanvas` option to an element reference.

```javascript
camera.init({
	width: 160, // default: 640
	height: 120, // default: 480
	fps: 30, // default: 30
	mirror: true,  // default: false
	targetCanvas: document.getElementById('webcam'), // default: null 

	onFrame: function(canvas) {
		// do something with image data found in the canvas argument
	},

	onSuccess: function() {
		// stream succesfully started, yay!
	},

	onError: function(error) {
		// something went wrong on initialization
	},

	onNotSupported: function() {
		// instruct the user to get a better browser
	}
});
```

To pause the video capture, call `camera.pause()`. To resume, call `camera.start()`.

## Live examples

<table>
  <tr>
    <th>ASCII Camera</th>
    <th>Predator Vision</th>
  </tr>
  <tr>
    <td><a href="http://radhesh1.github.io/ascii-camera/"><img src="http://radhesh1.github.io/ascii-cam/images/screenshot.png" width="267" height="200"></a></td>
    <td><a href="http://radhesh1.github.io/predator-vision/"><img src="http://radhesh1.github.io/killer-vision/images/screenshot.png" width="278" height="200"></a></td>
  </tr>
</table>

## Supported browsers

* Chrome &ge; 21
* Firefox &ge; 17 (requires `media.navigator.enabled = true` in `about:config`)
* Opera &ge; 12

## Author

**Andrei Gheorghe**

* [About me]([http://idevelop.github.com](https://portfolio-radhesh1.vercel.app/))
* LinkedIn: [linkedin.com/in/idevelop](https://linkedin.com/in/radhesh-g)
* Twitter: [@radhesh1](http://twitter.com/radhesh1)

## License

- This code is licensed under the MIT License.

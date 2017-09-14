Example
===========

Quick Start
-----------
To start using Draco, you could try the example `webgl_loader_draco.html`.
The code shows a simple example of integration of threejs and Draco Javascript or WebAssembly decoder. From the example, you should be able to load an encoded draco mesh file and visualize it through threejs's fancy 3D tools.

How to run the example code:

(1) Clone this project to a working directory, e.g. draco/.

(2) From the project's root directory, start a local http server.
E.g, with Python, you could run "python -m SimpleHTTPServer".

(3) Load javascript/example/webgl_loader_draco.html. You should be able to see
a bunny rendered by threejs using Draco loader.

Advanced Example
---------------------
To use more advanced features of Draco loader, please look at the example `webgl_loader_draco_advanced.html`.
In this example, you could:

(1) Switch between Javascript decoder and WebAssembly decoder if it's supported by the browser.

(2) Load your own encoded Draco file (.drc) by clicking on "Choose File" and select a file.

Static Loading Javascript Decoder
---------------------------------

In the previous examples, `DRACOLoader.js` will dynamically load Javascript decoder or
WASM decoder depending on the support of the browser. To avoid dynamical loading the decoder, e.g. to use with JS bundler like webpack, you could directly include `draco_decoder.js` and set the decoder type to `js`. For example:

Include Javascript decoder:
~~~~~ html
<script src="../draco_decoder.js"></script>
~~~~~

Create DracoLoader by setting the decoder type:
~~~~~ js
var dracoDecoderType = {};
dracoDecoderType.type = 'js';
var dracoLoader = new THREE.DRACOLoader('path_to_decoder', dracoDecoderType);
~~~~~
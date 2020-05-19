# EngineEditorCamera
## A game engine editor-type camera for easy traversal through [three.js](https://threejs.org) scenes

[LIVE DEMO](https://nevr.to/02)

Featuring:
* smooth scene traversal - right click + W/A/S/D/Q/E to get around

* right click + **shift** + WASDEQ to go faster

* mouse scroll wheel up/down to increase/decrease camera movement speed

* session persistence: location, rotation and movement speed persist over refreshes (extra convenient for hot reloading)  


## Instructions:
* add `engineEditorCamera.js` to a threeJS app
* in your main app JS file (or wherever you want, long as you're fine refrencing your camera and renderer there):

```js
// app.js

import * as THREE from "three"
import EngineEditorCamera from "PATH/TO/engineEditorCamera"]

//  (set up your renderer and camera, for example:)

const camera = new THREE.PerspectiveCamera( 75, window.innerWidth/window.innerHeight, 0.1, 1000 );

const renderer = new THREE.WebGLRenderer();
renderer.setSize( window.innerWidth, window.innerHeight );
document.body.appendChild( renderer.domElement );

// create a new EngineEditorCamera with camera and your renderer's DOM element, like so:
const engineEditorCamera = new EngineEditorCamera(camera, renderer.domElement)


// in your update loop, call the .update() method, for example:

const animate = function () {
    requestAnimationFrame( animate );
    engineEditorCamera.update();
    renderer.render( scene, camera );
};

animate();

```

And that's it. Happy scene traversal!


# Node-Based Shader Editor
 
This is the result of my final degree project, which consist on a node-based shader editor implemented on web. The framework is based mainly on the usage of this libraries:

 * [Litegl.js](https://github.com/jagenjo/litegl.js) - A JavaScript library that contains several classes for managing different items (like Buffer, Mesh, Texture, Shader) for WebGL applications. It was originally created for WebGLStudio, a 3D graphics suite for browser.
 * [Litegraph.js](https://github.com/jagenjo/litegraph.js) - Complementary to LiteGL, this one is used to manage graphs in the browser. It also includes an editor to construct and tests the graphs. Like the previous one, it is also used in WebGLSudio, by the same author.

## Functionalities

This is the list of the most important functionalities of the application.

 * Manipulation of the Volume Render algorithm via nodes.
 * Load and visualization of Dicom datasets. In the case you don't have any but you want to try it, I uploaded an anonymized dataset in the repository. More info [here](https://www.dicomlibrary.com/).
 * Manipulation of the datasets by editing the transfer function.
 * Download of the Vertex Shader and Fragment Shader createds by the graph editor.
 * Try an online demo [here](https://victorubieto.github.io/graph_system/).

## List of Nodes

This is the list of the nodes currently available. There are more comming soon, so stay tunned.

 * **Input:** Number, Color, Coordinates.
 * **Texture:** Gradient, Noise, Dicom, Transfer Function.
 * **Operator:** Math, MixRGB, ColorRamp, Translate, Scale, Rotate, Separate, Combine.
 * **Shader:** Volume.
 * **Output:** Material Output.
 
 | Type |  Inputs | Outputs |
 | **Input** | | |
 | :------ | ------- | ------- |
 | Number | - | Factor: value |
 | Color | - | Color: vec3 |
 | Coordinates | - | Generated: vec3<br/>Normal: vec3<br/>UV: vec3<br/>Object: vec3<br/>Camera: vec3 |
 | **Texture** | | |
 | Gradient | Vector: vec3 | Color: vec4 <br/>Factor |
 | Noise | Vector: vec3 | Color: vec4 <br/>Factor |
 | Dicom | - | Density: value |
 | Transfer Function | - | Color: vec4 |
 | **Operator** | | |
 | Math | Value A, Value B | Result (=) |
 | MixRGB | Factor <br/>Color A, Color B | Color: vec4, Factor: value |
 | ColorRamp | Value | Color: vec4, Factor: value |
 | Translate | Vector: vec3 | Vector: vec3 |
 | Scale | Vector: vec3 | Vector: vec3 |
 | Rotate | Vector: vec3 | Vector: vec3 |
 | Separate | RGBA: vec4 | R: red value<br/>G: green value<br/>B: blue value<br/>A: aplha value |
 | Combine | R: red value<br/>G: green value<br/>B: blue value<br/>A: aplha value | RGBA: vec4 |
 | **Shader** | | |
 | Volume | Color: vec4<br/>Density:value | Volume: algorithm that calculates the final color |
 | **Output** | | |
 | Material Output | Frag Color: computation for the final color | - |

## Other libraries used

 * [Daikon.js](https://github.com/rii-mango/Daikon) - A pure JavaScript DICOM reader. 
 * [Gl-Matrix.js](https://github.com/toji/gl-matrix) - A library to perform vector and matrix operations really fast.
 * [JQuery.js](https://github.com/jquery/jquery) - It makes things like HTML document manipulation and event handling much simpler.
 * [JsColor.js](https://github.com/EastDesire/jscolor) - Color picker widget for web.
 * [Rendeer.js](https://github.com/jagenjo/rendeer.js) - A 3D scene graph library for 3D web apps and games. It has some classes for handle the scene (like Scene, SceneNode, Camera).
 * [Volume-base.js](https://github.com/upf-gti/Volumetrics/blob/master/src/volume-base.js) - Class that describes a 3D dataset.
 * [Volume-loader.js](https://github.com/upf-gti/Volumetrics/blob/master/src/volume-loader.js) - This library has functions to parse Dicom, Nifti and VL files. It requires Volume-base file.
 * [W2ui.js](https://github.com/vitmalina/w2ui) - A modern and intuitive JavaScript UI library for web applications.

## Examples

Clouds Modeling
![alt text](https://github.com/victorubieto/graph_system/blob/master/img/readme_examples/example_clouds.PNG?raw=true)

Dicom Visualization
![alt text](https://github.com/victorubieto/graph_system/blob/master/img/readme_examples/example_torax.PNG?raw=true)

WebGL performance tips - Nicolas Silva
======================================
@nicalsilva - http://nical.github.com/onGameStart2013

- WebGL high lvl API and low lvl API
- Both FF & Chrome use
 - on mobile: openGL ES2
 - on Mac & Linux: "desktop" OpenGL
 - On Windows: OpenGL ES2 (throught ANGLE - > Direct3D)
- ANGLE also provides with shader translation/validation on all platforms
- WebGL tries to pipeline commands as much as possible
- A point of synchronization can block the JS thread for a long time
- for instance: gl.getErrors(), gl.readPixels(), gl.finish()
- data transfer f between CPI and GPU is slow
 - texture uploads, vertex buffers,
- cache gets calls like gl.getParameter(), gl.getUniformLocation()
- avoid gl.uniform1f(gl.getUniformLocation(program, "time"), time);
- generally the most important optimization!
- state changes are expensive (texture bindings, shaders)
- pack all the geometry that share the same states together in the same drawing commangds
- pack several textures info one, and select the appropriate region with texture coordinates
- shaders - highly parallel execution
- compile in GPU 
- we can render worlds in two trangles

DEMO: https://github.com/nical/GLSL-Raymarching/blob/master/demo/webgl/raymarcher.html

- Branching is slow
if (foo < 0.5) {
 // do A...
} else {
 // do B...
}
- often the cost of computing both A and B
- coherency usually  improves performance
- CPU cache locality 
- for the texture cache, proximity is considered in 2D
- cache misses are expensive
- mip mapping - from big image to small without mistakes in redered
- warning: shader compile times
- shader compilation si synchronous
- very heavy shaders can block the browser for sever seconds on some drivers

DEMO: http://shadertoy.com/

- avoid high precision floats in fragment shaders (mobile gardware dont support it)

QUESTION: what's is the most famous tool of debugging WebGL which you use?

- use gl.finish() (but not in production!) ----- ;)
- GPU is not a silver bullet 
- GPU is good at doing some specific operations
- its not good fo:
 - rendering text
 - vector shapes in general (bezier curves)
 - processing that is sequential by nature
- js that calls info webGL runs in the same thread as layout and most of web content
- means other things can block your games's thread
- WebGL workers \o/ ---------- ;)
- security - OpenGL specifications have behavios left undefined to acheve the best performance
- on the wev we cannot


http://khronos.org/registry/webgl/specs/1.0<br />
http://khronos.org/webgl/security<br />
http://hacks.mozilla.org/2013/04/the-concepts-of-webgl<br />
http://khronos.org/webgl/wiki/WebGL_and_OpenGL_Differences<br />

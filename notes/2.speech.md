Native fast HTML5 with Windows Phone and Android - Yuri Dobronravin
===================================================================

http:/logicking.com/

Why HTML5?
- small team
- develop once
- ship everywhere
- tech savyy

QUESTION: what are you experience with Smart TV Alliance ?

- ultimate.js
- low-level:
 - OOP Java style
 - DOM based , not using Canvas
 - GUI components

---
- high-level:
 - game states
 - sprites & sprites

---
- server-side:
 - nodeJS
 - postresSQL
 - same entities classes as in clients

---
- screen resolutions
 - margin: 70px 169px
 - enhaced scene: 1138x640
 - main scene 800x500

---
- spaceport, phonegap, cocoon, mosync, marmalade, appMobi(!)
- HTML overheads
 - ineffective gtaphics management (slow positionnigs, string-bases type conversion, heavy html4 legacy)
 - low objects scaling efficiency (more objects = more lags)

---
- problems
 - difference ways to build eficient bridge between js and native (windows phone - fast js from natvie, very slow native calls from js, slow js from native)
 - difference between internal work od DOM (windows Phone and Android)
 - which js interpreter to use?

---
- solutions
 - push as many data as we can (without direct rewuest) to js from native on windows phone,
 and pull as many data as we can on Android
 - caching DOM objects ----- how?
 - using stock web browser as js interpreters only

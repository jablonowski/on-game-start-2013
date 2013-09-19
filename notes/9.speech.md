Cross platform game for mobile and desktop - Greg Galajewicz
============================================================

- Realm of Empires
- use HTML5
- light of animation
- our goals
 - native-like user experience
 - run in browser & app
 - support
  - android v 2.3+
  - iOS 5+
  - all major desktop browsers
 - simultaneously develop for Android, iOS & desktop
 - must support android

---
- Why app?
 - seamless auth
 - payments
 - notifications
 - common experience
- No to browsers!
 - many browsers
 - many incompatibilities (like in meta tag)
 - unable to reliably sniff the  browser

- build app with: Xamarin, PhoneGap

Stock browser != WebView control
Androig stock browser ~ WebView
Safari ~ UIWebView
Wind8 IE 10 != win8 WebView

Architecture choices
1) stateless - multi-page
2) stateful - one-page
 - fastest UI
 - best UI
 - difficult
  - large app in JS
  - lack of good devs
3) Hybrid - Stateful Frame

Performance
- canvas animation
 - vector animation only on iphone 4s and up
 - sprite animation
  - 24-30fpx - galaxy s3 & iphone 3gs
  - 2fps on many android 4.0 including tablets
 - Ghost canvas bug 35474 still on Android 4.3
 - iOS large canvas crash
 - html rendering - adding html
```
  display none | block
  visibility | visible
```
1 - 1.5sec display time is typical
- css is incosequential

- CSS3 transitions, animation
 - horrible on android 4.0
 - android 4.1 ~ iphone 3gs still choopy for non-triviral html
  - improvement - dont trigger reflow


Interactivity feedback aka click effect - hard to do on Android
```
// failed on Android
$('.mainButton').toggleClass('clicked-effect').showMailPopup();

// hack
$('.mainButton').toggleClass('clicked-effect');
setTimeout(showMailPopup, 300);
```

- jQuery animations - oh no no !
- data entry - oh god!
 - no good sliders
 - html5 input types - dont bet on them
 - avoid display:fixed
 - avoid entry boxes in bottom half of screen
 - get creative!

Future of Android
- Chromium to power android WebView
- amazon launched a Chromium bases WebView August 2013
 - available on ALL Androids v2.3 and above
- Samsung may move away from Android to Tizen
- Non app-based envirouments
 - Amazon web app
 - Win8 js runtime
 - BB10 is runtime

*RoE Mobile*
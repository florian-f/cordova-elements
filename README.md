# Cordova-Elements

Web-Components that expose the API of Apache Cordova and (some) Cordova Plugins. 
More at [cordova-elements-demo](https://github.com/florian-f/cordova-elements-demo)

Once I decide whether this project makes sense or not I might set it up properly with bower and write some gulp tasks that make working with cordova easier. 

Note that in `cordova-base/cordova.html' a script tag that loads cordova.js is created. The actual (platform-specific) cordova.js is not available at the time gulp builds the polymer app. This is the solution I came up with in order to enable inlining and still have the script tag.  Cordova complains if it doesn't find its own script tag since it needs to look at the src attribute to determine the location of the plugin scripts.
Unfortunately, after I upated yeoman it produces a different gulpfile and somehow nothing worked unless I disabled the vulcanize task, so no inlining for now.

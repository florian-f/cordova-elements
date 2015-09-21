# Cordova-Elements

Web-Components that expose the API of Apache Cordova and (some) Cordova Plugins. 
## Usage: 

    <cordova-device platform="{{platform}}"></cordova-device>
    <p>platform: <span>{{platform}}</span></p>

More at [cordova-elements-demo](https://github.com/florian-f/cordova-elements-demo)

## Additional Notes
Once I decide whether this project makes sense or not I might set it up properly with bower and write some gulp tasks that make working with cordova easier. 

Note that in `cordova-base/cordova.html' a script tag that loads cordova.js is created. The actual (platform-specific) cordova.js is not available at the time gulp builds the polymer app. This is the solution I came up with in order to enable inlining and still have the script tag.  Cordova complains if it doesn't find its own script tag since it needs to look at the src attribute to determine the location of the plugin scripts.
Unfortunately, after I upated yeoman it produces a different gulpfile and somehow nothing worked unless I disabled the vulcanize task, so no inlining for now.

Also, it is not clear if it's a good idea to inline the javascript for codova and the individual plugins. It would be a lot of work - one would have to maintain a fork of cordova and every plugin, and jshint errored a lot when I accidentally inlined cordova.js. Also, functionality where cordova only uses a plugin if the browser doesn't already provide the corresponding api might be broken.

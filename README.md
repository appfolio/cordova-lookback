Cordova Lookback Plugin
=======================

Official Cordova plugin for http://lookback.io. Originally written by
[Ryan French](https://github.com/RYFN), to whom Lookback owes its eternal
gratitude.

Methods will be accessable on the window.Lookback object.

Utilizes Lookback Safe, which will not record with as good framerate as Lookback
HD, but can freely be deployed to AppStore. (I'll make the cordova plugin
automatically choose the correct plugin variant (HD or Safe) depending on
build configuration once I figure out how).

Install
-------

Install with `cordova plugin add https://github.com/lookback/cordova-lookback`

Currently supported functions
-----------------------------

Most of the functionality of the
[Lookback class](https://s3-eu-west-1.amazonaws.com/lookback-public/docs/ios/0.9.0/Lookback_h/Classes/Lookback/index.html#//apple_ref/occ/cl/Lookback)
has been implimented.

### setupWithAppToken
call this first, once, and after device ready.

### shakeToRecord
true|false

### userIdentifier
Some unique per-device identifier, or set to `deviceName` to use the
currentDevice name as assigned by iOS. ([[UIDevice currentDevice] name]);

### paused
true|false

### enteredView
pass in a view name

### exitedView
pass in a view name

Example
-------

    document.addEventListener('deviceready', function(){
            window.Lookback.setupWithAppToken('your-app-token');
            window.Lookback.shakeToRecord(true);
            
            // optional: store user's name with recording
            window.Lookback.userIdentifier('name or email of user'); 
            // or 
            //window.Lookback.userIdentifier('deviceName');
        }, false);

or to try some optional features:

    document.addEventListener('deviceready', function(){
        window.Lookback.setupWithAppToken('your-app-token');
        window.Lookback.shakeToRecord(false);
        
        window.Lookback.userIdentifier('name or email of user'); // optional
        
        window.Lookback.enteredView('my view name');
    }, false);

License
-------

Use of lookback.io Framework subject to terms available on http://lookback.io


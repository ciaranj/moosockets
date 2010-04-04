moosockets
===========

A port of the jquery plugin ( http://bloga.jp/ws/jq/ ) to provide some extra functionality on top of the raw WebSocket object.

How to use
----------

Simply include the source. You will be able to construct a moosockets instance as follows:

    var ms= new MooSocket({
      url : "ws://localhost:8081",
      onopen : function () {
        console.log('connected');
      },
      onmessage : function (data) { 
        console.log('received data');
      },
    
      onclose : function (event) {
        console.log('disconnected');
      }                         
    });

You should provide implementations of each of these callback functions as appropriate to your needs.

To send data to the server do the following:

    ms.wssend(JSON.encode({"a":1,"b":[]});
    

If you wish to use logging (handy for diagnostics) then set the 'loggingEnabled' option to 'true'. (You can also override the default logging behaviour by also passing a function as the 'logger' option.)
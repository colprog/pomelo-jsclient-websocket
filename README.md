#Pomelo javascript client

The javascript client libary for [Pomelo](https://github.com/NetEase/pomelo) 
this javascript client based on original websocket not [socket.io](https://github.com/LearnBoost/socket.io-client) so it supports binary transfer  
we use a new [protocol](https://github.com/NetEase/pomelo/wiki/Pomelo-%E5%8D%8F%E8%AE%AE) to communicate between server and client , and this client supports it   

##Usage

### connect to the server
``` javascript
  pomelo.init(params, callback);
```  
params object are 

example:
``` javascript
  pomelo.init({
    host: host,
    port: port,
    user: {},
    handshakeCallback : function(){}
  }, function() {
    console.log('success');
  });
```

user field is user define json content  
handshakeCallback field is handshake callback function  

### send request to server with callback
``` javascript
  pomelo.request(route, msg, callback);
```

example:
``` javascript
	pomelo.request(route, {
		rid: rid
	}, function(data) {
    console.log(dta);	
	});
```

### send request to server without callback
``` javascript
  pomelo.notify(route, params);
```

### receive message from server 
``` javascript
  pomelo.on(route, callback); 
```

example: 
``` javascript
	pomelo.on('onChat', function(data) {
		addMessage(data.from, data.target, data.msg);
		$("#chatHistory").show();
	});
```

### disconnect from server  
``` javascript
pomelo.disconnect();
```  

##License
(The MIT License)

Copyright (c) 2012-2013 NetEase, Inc. and other contributors

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the 'Software'), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

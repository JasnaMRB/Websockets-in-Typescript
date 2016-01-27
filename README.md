#Websocket in TypeScript
This is a simple app to demonstrate how to create WebSocket connections in TypeScript.

##To run
Have TypeScript installed:
<code>npm install -g typescript</code>

Create a folder called 'build' in the root directory.

Transpile the TypeScript:
<code>tsc --removeComments --module commonjs --target ES5 --outDir build src/server.ts</code>

Run the server:
<code>node build/server</code>

Make some connections. In your Web browser Developer Tools console, add the following code:
  <code>
  var socket = new WebSocket('ws://localhost:3000');

  socket.onmessage = function (message) {
    console.log('Connection 1', message.data);
  };

  var socket2 = new WebSocket('ws://localhost:3000');

  socket2.onmessage = function (message) {
    console.log('Connection 2', message.data);
  };

  var socket3 = new WebSocket('ws://localhost:3000');

  socket3.onmessage = function (message) {
    console.log('Connection 3', message.data);
  };
  </code>
Then, send some messages:
  <code> socket.send(JSON.stringify({ name: 'Bob', message: 'Hello' }));. </code>

###Thanks
[Code Project](http://www.codeproject.com/Articles/871622/Writing-a-chat-server-using-Node-js-TypeScript-and)

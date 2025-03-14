 taken from zig book by pedro park
https://pedropark99.github.io/zig-book/Chapters/04-http-server.html
https://github.com/pedropark99/zig-book
https://pedropark99.github.io/zig-book/

 http core is stateless but http cookies allow for statefulness
 see https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Overview for more
 In C we commonly implement a web server in following steps:
 1. Create a TCP socket object.
 2. Bind an address to socket object
 3. Make the socket start listening and waiting for incoming connections
 4. Accept connection upon arrival and exchange http request and response
 5. simply close the connection


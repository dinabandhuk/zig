# From zig book by pedro park
https://pedropark99.github.io/zig-book/Chapters/04-http-server.html
https://github.com/pedropark99/zig-book
https://pedropark99.github.io/zig-book/

---

## Notes
1. http core is stateless but http cookies allow for statefulness
 see https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Overview for more
 In C we commonly implement a web server in following steps:
 1. Create a TCP socket object.
 2. Bind an address to socket object
 3. Make the socket start listening and waiting for incoming connections
 4. Accept connection upon arrival and exchange http request and response
 5. simply close the connection

1. Zig enums can have private and public methods in them
2. Zig returns struct objects in order they are declared
```bash
[mounam@moksha http_server (main)]$ zig run src/main.zig 
Server Address: 127.0.0.1:8000
request.Request{ .method = request.Method.GET, .uri = { 47 }, .version = { 72, 84, 84, 80, 47, 49, 46, 49, 13 } }
[mounam@moksha http_server (main)]$ 
```
the ordering of .method, .uri, .version is based on this declaration and changes if I move things around
```zig
const Request = struct {
    method: Method,
    uri: []const u8,
    version: []const u8,
```

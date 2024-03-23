# Reflection
## Commit 1
Before implementing handle_connection, our server simply established TCP connections without processing them, demonstrating only basic TCP/IP functionality. The addition of handle_connection enabled us to read and interpret HTTP requests, marking a crucial advancement in handling client-server interactions. By using a BufReader with the TcpStream, we efficiently parsed the text-based HTTP protocol.
## Commit 2
![Commit 2 screen capture](/assets/images/commit2.png)
The updated handle_connection method reads hello.html and construct an HTTP response including this HTML content. This method meticulously assembles an HTTP response with a proper status line, headers, and the actual HTML content, ensuring browsers can correctly render the served page. It highlights the transition from a simple TCP server to a web server capable of delivering HTML content, marking a critical step in web development.
## Commit 3
![Commit 3 screen capture](/assets/images/commit3.png)
I added request validation, enabling it to distinguish between valid and invalid requests and respond with either the correct content or a 404 Not Found page. This is achieved by parsing the initial request line and deciding which HTML file to serve based on the request's target path. The server now serves hello.html for the root path (GET / HTTP/1.1) and bad.html for any other requests.
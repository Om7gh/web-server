🌐 webserv

webserv is a fully functional HTTP/1.1 server built from scratch in C++ using low-level socket programming.

This project recreates the core behavior of real web servers like NGINX and Apache HTTP Server, giving a deep understanding of networking, HTTP internals, and system-level programming.

🚀 Features

⚡ Built entirely in C++

🔌 Low-level BSD socket API

🌍 HTTP/1.1 compliant

📥 GET method

📤 POST method

❌ DELETE method

🗂 Static file serving

📦 Large file handling (tested with files up to 10GB+)

🧬 CGI execution (PHP & Java)

🧵 Multi-client handling (non-blocking I/O)

🧠 Designed using SOLID principles

📡 HTTP Capabilities
🔹 GET

Serve static files (HTML, CSS, JS, images)

Directory handling (if enabled)

Proper MIME type detection

🔹 POST

Handle form submissions

Support file uploads

Manage large payloads efficiently

🔹 DELETE

Delete server-side resources

Proper permission and error validation

🧬 CGI Support

The server supports Common Gateway Interface (CGI) execution.

Supported:

PHP scripts

Java CGI programs

How it works:

Detect CGI request

fork() a child process

Set up environment variables

Execute script using execve()

Capture output

Send generated response back to client

This allows dynamic content generation just like real production servers.

📦 Large File Handling

Efficient file streaming

Handles files larger than 10GB

Avoids loading entire file into memory

Uses chunked reading/writing strategy

Optimized for performance and memory safety

📊 Status Code Handling

The server can respond with proper HTTP status codes, including:

100 Continue

200 OK

201 Created

204 No Content

301 Moved Permanently

400 Bad Request

403 Forbidden

404 Not Found

405 Method Not Allowed

413 Payload Too Large

500 Internal Server Error

502 Bad Gateway

And more...

🏗 Architecture & Design

The server was designed following SOLID principles:

Single Responsibility Principle
Clear separation between parsing, routing, response building, and CGI handling.

Open/Closed Principle
Easy to extend with new HTTP methods or features.

Dependency Inversion
Core logic decoupled from low-level implementation details.

Internal Components

Socket Manager

Event Loop (poll/select/epoll if used)

HTTP Request Parser

Response Builder

Router

CGI Handler

Configuration Parser

File Handler

🔁 Server Workflow

Create socket

Bind to port

Listen for connections

Accept clients

Parse HTTP request

Route request

Execute CGI (if needed)

Build HTTP response

Send response

Close or keep connection alive

🛠 Tech Stack

C++

BSD Sockets

HTTP/1.1

CGI

Makefile

🧪 How to Run
1️⃣ Compile
make
2️⃣ Run
./webserv config.conf
🎯 What This Project Demonstrates

Deep understanding of TCP/IP

HTTP protocol internals

System calls (socket, bind, listen, accept, fork, execve)

Process management

Memory management in C++

Handling concurrency

File streaming optimization

Building scalable network software

🔮 Possible Improvements

HTTPS (SSL/TLS)

HTTP/2 support

Advanced caching

Logging system

Reverse proxy mode

Load balancing

teams:
me
outman oulcaid
tarik amehri

# Client vs Server

## Client

The client is the user-facing application that makes requests.

Examples:
- Web browser (Chrome, Firefox)
- Mobile app
- Desktop app

Responsibilities:
- Send HTTP requests
- Display UI
- Handle user input

## Server

The server is a computer/program that processes requests and returns responses.

Responsibilities:
- Handle business logic
- Access databases
- Authenticate users
- Return data (HTML, JSON, etc.)

## How They Communicate

Communication happens over HTTP or HTTPS.

Example:

1. Client requests a web page
2. Server processes request
3. Server sends back response
4. Client renders the content

## Example Flow

User types:
```
https://example.com
```


Browser:
- Sends HTTP request to server

Server:
- Returns HTML

Browser:
- Renders page


## Summary

Client = Requests & UI  
Server = Logic & Data
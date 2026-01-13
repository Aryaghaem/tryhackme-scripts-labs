# Telnet HTTP Enumeration

Used telnet to manually interact with a web server over TCP port 80.

- Connected to the server using telnet
- Sent a raw HTTP request (GET / HTTP/1.0)
- Identified the web server software and version
- Retrieved a flag from the HTTP response

Skills practiced:
- TCP communication
- HTTP basics
- Service enumeration
  
- ## Retrieving a Hidden Web Resource

Extended the same telnet technique to request a non-default file on the web server.

- Manually requested a specific resource using `GET /flag.html HTTP/1.0`
- Observed the full HTTP response, including headers and HTML body
- Identified hidden content that is not rendered in a browser

Additional skills reinforced:
- Manual web enumeration
- Understanding HTTP request formatting
- Identifying information exposure in server responses


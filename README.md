# EX01 Developing a Simple Webserver
## Date:1.09.25

## AIM:
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
```python
from http.server import HTTPServer, BaseHTTPRequestHandler

content = '''<!doctype html>
<html>
<head>
<title>My Web Server</title>
</head>
<body align="center">
<h1> TCP/IP Protocol</h1>

<table border="1" align="center" cellpadding="10" cellspacing="0" bgcolor="lightblue">

  <tr>
    <th>S.NO</th>
    <th>Name of the Layer</th>
    <th>Name of the Protocols</th>
  </tr>

  <tr>
    <td><b>1</b></td>
    <td><b>Application Layer</b></td>
    <td><b>HTTP, HTTPS, FTP, SMTP, POP3, IMAP, DNS, Telnet, SSH</b></td>
  </tr>

  <tr>
    <td><b>2</b></td>
    <td><b>Transport Layer</b></td>
    <td><b>TCP (Transmission Control Protocol), UDP (User Datagram Protocol)</b></td>
  </tr>

  <tr>
    <td><b>3</b></td>
    <td><b>Network Layer (Internet Layer in TCP/IP)</b></td>
    <td><b>IP (IPv4, IPv6), ICMP, IGMP, ARP, RARP</b></td>
  </tr>

  <tr>
    <td><b>4</b></td>
    <td><b>Link Layer (Network Access Layer in TCP/IP)</b></td>
    <td><b>Ethernet</b></td>
  </tr>
</table>
</body>
</html>
'''

class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver") 
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
```

## OUTPUT:
<img width="1919" height="1131" alt="image" src="https://github.com/user-attachments/assets/7765ece3-09dd-4c4d-8d35-6ab4375010aa" />
<img width="1073" height="164" alt="image" src="https://github.com/user-attachments/assets/890a946c-f4a7-4f12-9a06-f2907aaffe7a" />


## RESULT:
The program for implementing simple webserver is executed successfully.

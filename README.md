# EX01 Developing a Simple Webserver
## Date:26.10.2024

## AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:
'''
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''
<html>
<title>Laptop Specification</title>
<body>
<table border="4"  cell spacing="12" cell padding="6">
<tr>
   <th>S.no</th>
   <th>Configuration</th>
   <th>Description</th>
</tr>
<tr>
   <th>1</th>
   <th>Name</th>
   <th>Lenovo thinkpad</th>
</tr>
<tr>
   <th>2</th>
   <th>Processor</th>
   <th>I5</th>
</tr>
<tr>
   <th>3</th>
   <th>Graphics Card</th>
   <th>Nvidia Geforce MX550</th>
</tr>
<tr>
   <th>4</th>
   <th>Installed ram</th>
   <th>16.0GB</th>
</tr>
<tr>
   <th>5</th>
   <th>System type</th>
   <th>64-bit operating system, x64-based processor</th>
</tr>
<tr>
   <th>6</th>
   <th>Edition</th>
   <th>Windows 11 Home</th>
</tr>
<tr>
   <th>7</th>
   <th>Version</th>
   <th>22H2</th>
</tr>
<tr>
   <th>8</th>
   <th>OS Build</th>
   <th>22621.4</th>
</tr>
<tr>
   <th>9</th>
   <th>Colour</th>
   <th>Black</th>
</tr>
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
server_address =('',4000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
'''

## OUTPUT:
![alt text](<Screenshot 2024-10-26 140214.png>)
![alt text](<Screenshot 2024-10-26 140244.png>)


## RESULT:
The program for implementing simple webserver is executed successfully.

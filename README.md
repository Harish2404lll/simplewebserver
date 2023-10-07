# Developing a Simple Webserver
## DATE
24-09-2023
## AIM:
To develop a simple webserver to serve html pages.

## DESIGN STEPS:
### Step 1: 
HTML content creation
### Step 2:
Design of webserver workflow
### Step 3:
Implementation using Python code
### Step 4:
Serving the HTML pages.
### Step 5:
Testing the webserver

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler

# HTML content with a list of the top 5 revenue-generating companies
content = """
<!DOCTYPE html>
<html>
<head>
    <title>Top 5 Revenue-Generating Companies</title>
</head>
<body>
    <h1>Top 5 Revenue-Generating Companies</h1>
    <ol>
        <li>Apple Inc.</li>
        <li>Saudi Aramco</li>
        <li>Amazon.com Inc.</li>
        <li>Microsoft Corporation</li>
        <li>Alphabet Inc. (Google)</li>
    </ol>
</body>
</html>
"""

class MyHandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Request received")
        self.send_response(200)
        self.send_header('Content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())

server_address = ('', 80)
httpd = HTTPServer(server_address, MyHandler)
print("My webserver is running...")
httpd.serve_forever()
```

## OUTPUT:

![output png](https://github.com/Harish2404lll/simplewebserver/assets/141472096/deb4c17e-2b43-4a61-9ab2-6e9dab207e6b)
![image](https://github.com/Harish2404lll/simplewebserver/assets/141472096/146c3dae-b45a-4752-a139-57cb1b843a16)


## RESULT:
The program for implementing simple webserver is executed successfully.

# Developing a Simple Webserver

AIM:
Develop a webserver to display about top five web application development frameworks.

DESIGN STEPS:
Step 1:
HTML content creation is done

Step 2:
Design of webserver workflow

Step 3:
Implementation using Python code

Step 4:
Serving the HTML pages.

Step 5:
Testing the webserver

PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<titlt>MY WEBSERVER</title>
</head>
<body>
<h1>WELCOME TO MY SIMPLE WEBSERVER</h1>
</body>
</html>
"""
class HelloHandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request recieved")
        self.send_response(200)
        self.send_header('Content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())


server_address = ('', 8080)
httpd = HTTPServer(server_address, HelloHandler)
print("my webserver is running.....")
httpd.serve_forever()
```
OUTPUT:
![image](https://user-images.githubusercontent.com/120359170/215380199-4310efb0-1213-4ffb-9a12-623205c766e8.png)


RESULT:
The program is executed succesfully


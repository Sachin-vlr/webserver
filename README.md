# Developing a Simple Webserver

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

HTML content creation is done

### Step 2:

Design of webserver workflow

### Step 3:

Implementation using Python code

### Step 4:

Serving the HTML pages.

### Step 5:

Testing the webserver

## PROGRAM:
```python
from http.server import HTTPServer,BaseHTTPRequestHandler
content='''
<!doctype html>
<html>
<head>
<title> My Web Server</title>
</head>
<body>
<h1>Top Five Web Application Development Frameworks</h1> 
<h2>1.Django</h2>
<h2>2. MEAN Stack</h2>
<h2>3. React </h2> 
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

SERVER OUTPUT

![Screenshot 2023-03-27 094729](https://user-images.githubusercontent.com/113497666/228900015-65737c37-34dc-4e29-b939-7a98575d6979.png)


CLIENT OUTPUT

![Screenshot 2023-03-27 094643](https://user-images.githubusercontent.com/113497666/228900128-65874c61-c159-4af6-8305-59d2556c845b.png)

## RESULT:
The program is executed succesfully

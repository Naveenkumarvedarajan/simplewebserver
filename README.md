# EX01 Developing a Simple Webserver
## Date:24/02/2024

## AIM:
To develop a simple webserver to serve html pages.

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
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<title>software company</title>
</head>
<body>
<center> <h1> Top five revenue generating software companies </h1> </center>
<table border="5" cellspacing="7" cellpadding="17">

<tr>
<th>rank</th>
<th>company</th>
<th>sales</th>
<th>nationality</th>
<th>revenue</th>
</tr>

<tr>
<td>1</td>
<td>microsoft</td>
<td>57.9c</td>
<td>USA</td>
<td>100000</td>
</tr>

<tr>
<td>2</td>
<td>oracles</td>
<td>21.8c</td>
<td>USA</td>
<td>950000</td>
</tr>

<tr>
<td>3</td>
<td>SAP</td>
<td>16.1c</td>
<td>GERMANY</td>
<td>900000</td>
</tr>

<tr>
<td>4</td>
<td>Computer Associates</td>
<td>4.2c</td>
<td>USA</td>
<td>850000</td>
</tr>

<tr>
<td>5</td>
<td>Adobe</td>
<td>3.4c</td>
<td>USA</td>
<td>80000</td>
</tr>

</table>
</body>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()

```

## OUTPUT:
![Screenshot (40)](https://github.com/Naveenkumarvedarajan/simplewebserver/assets/147140428/426311a9-2e06-4205-860c-79cd3f8d1025)
![image](https://github.com/Naveenkumarvedarajan/simplewebserver/assets/147140428/c343f24c-6259-487a-9da7-b8919f10d296)






## RESULT:
The program for implementing simple webserver is executed successfully.

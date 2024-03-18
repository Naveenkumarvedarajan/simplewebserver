# EX01 Developing a Simple Webserver
## Date:06/03/2024

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
<title> Software company </title>
</head>
<body>
<center> <h1> Top Five revenue Generating Software Companies </h1> </center>
<table border="5" cellspacing="13" Cellpadding="13">

<tr>
<th>Rank</th>
<th>Company</th>
<th>sales</th>
<th>Nationality</th>
<th>Revenue</th>
</tr>

<tr>
<td>1</td>
<td>Microsoft</td>
<td>57.9</td>
<td>USA</td>
<td>100000</td>
</tr>

<tr>
<td>2</td>
<td>Oracle</td>
<td>21.0</td>
<td>USA</td>
<td>95000</td>
</tr>

<tr>
<td>3</td>
<td>SAP</td>
<td>16.1</td>
<td>GERMANY</td>
<td>90000</td>
</tr>

<tr>
<td>4</td>
<td>Computer Associates</td>
<td>4.2</td>
<td>USA</td>
<td>85000</td>
</tr>

<tr>
<td>5</td>
<td>Adobe</td>
<td>3.4</td>
<td>USA</td>
<td>80000</td>
</tr>


</table>

</body>
</html>
8=(
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
![Screenshot (29)](https://github.com/Naveenkumarvedarajan/simplewebserver/assets/147140428/3ff12a11-d68c-493f-8818-a8a83b48d4fd)
![image](https://github.com/Naveenkumarvedarajan/simplewebserver/assets/147140428/2925620f-343e-4643-bd8d-3b29b23d3fc4)





## RESULT:
The program for implementing simple webserver is executed successfully.

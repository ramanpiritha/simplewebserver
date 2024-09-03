# EX01 Developing a Simple Webserver
## Date: 03-09-24
## Name: Piritharaman R
## Reg no: 212223230148

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
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
     <title> High Technology company</title> </title>
     <body>
           <center><table border = "4" cellspacing = "10" cellpading = "6"></center>
              <caption>Top most Revenue Generating High tech Companies </caption>
              <tr>
                  <th>S.No</th>
                  <th>Company</th>			
                  <th>Revenue</th>
              </tr>
              <tr>
                  <td>1</td>
                  <td>Google (Alphabet Inc.)</td>
                  <td>75 Billion</td>
             </tr>
             <tr>
                  <td>2</td>
                  <td>Apple Inc.</td>
                  <td>36.8 Billion</td>
             </tr>
             <tr>
                  <td>3</td>
                  <td>Salesforce</td>
                  <td>12.9Billion</td>
            </tr>
            <tr>
                  <td>4</td>
                  <td>Adobe Systems</td>
                  <td>33 Billion</td>
            </tr>
            <tr>
                  <td>5</td>
                  <td>Cisco Systems</td>
                  <td>7.5 Billion</td>
            </tr>
            <tr>
                <td>6</td>
                <td>Intel Corporation</td>
                <td>8.9 Billion</td>
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
![Screenshot (68)](https://github.com/user-attachments/assets/b910c659-8d3c-4d8d-b37c-d0a893246c59)



## RESULT:
The program for implementing simple webserver is executed successfully.

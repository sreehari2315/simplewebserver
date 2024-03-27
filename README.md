# EX01 Developing a Simple Webserver
## Date:

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
'''
from http.server import HTTPServer,BaseHTTPRequestHandler
content="""
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        a{
        color: red;
        padding: 30px;
        text-decoration:none;
        font-family: arial;
        font-size: 18px;
        }
        a:hover {
            color: rgb(253, 2, 2);
        }
    </style>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet"
        integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">
    {% load static1 %}

</head>

<body style="background-color:black;">

    <div style="display:flex;">
        <div style="width: 25%"><img style="width: 100%" src="title2.png"></div>
        <div style="width: 50%;padding-top: 125px;">
            <a href="https://en.wikipedia.org/wiki/Attack_on_Titan">Home</a>
            <a href="https://www.crunchyroll.com/series/GR751KNZY/attack-on-titan">Episodes</a>
            <a href="https://www.crunchyroll.com/series/GR751KNZY/attack-on-titan">Seasons</a>
            <a href="https://www.crunchyroll.com/series/GR751KNZY/attack-on-titan">ARC</a>
        </div>
        <div style="width: 20%;padding-top: 125px">
            <input
                style="width: 100%;height: 30px;background-image: url('si.png');background-size: contain;background-repeat: no-repeat;border-radius: 15px;padding-left: 40px;background-color:rgb(59, 8, 245);"
                type="text" placeholder="     search">
        </div>

    </div>
    <div style="width: 100%;">
        <div id="carouselExampleIndicators" class="carousel slide" data-bs-ride="carousel">
            <div class="carousel-indicators">
                <button type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide-to="0" class="active"
                    aria-current="true" aria-label="Slide 1"></button>
                <button type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide-to="1"
                    aria-label="Slide 2"></button>
                <button type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide-to="2"
                    aria-label="Slide 3"></button>
            </div>
            <div class="carousel-inner">
                <div class="carousel-item active">
                    <img src="{% static1 'img/12.jpg' %}" class="d-block w-100" alt="...">
                </div>
                <div class="carousel-item">
                    <img src="{% static1 'img/11.jpg' %}" class="d-block w-100" alt="...">
                </div>
                <div class="carousel-item">
                    <img src="{% static1 'img/13.jpg' %}" class="d-block w-100" alt="...">
                </div>
            </div>
            <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleIndicators"
                data-bs-slide="prev">
                <span class="carousel-control-prev-icon" aria-hidden="true"></span>
                <span class="visually-hidden">Previous</span>
            </button>
            <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleIndicators"
                data-bs-slide="next">
                <span class="carousel-control-next-icon" aria-hidden="true"></span>
                <span class="visually-hidden">Next</span>
            </button>
        </div>

    </div>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"
        integrity="sha384-YvpcrYf0tY3lHB60NNkmXc5s9fDVZLESaAA55NDzOxhy9GkcIdslK1eN7N6jIeHz"
        crossorigin="anonymous"></script>
</body>

</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(2002)
        self.send_header('content-type','text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address=('',8000)
httpd=HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()        
    
'''

## OUTPUT:

![Screenshot 2024-03-13 082741](https://github.com/selvasachein/simplewebserver/assets/139331590/3d19f087-97d1-46ec-8ca1-3fbd2aaf49d4)
![Uploading Screenshot 2024-03-25 153521.png…]()

## RESULT:
The program for implementing simple webserver is executed successfully.

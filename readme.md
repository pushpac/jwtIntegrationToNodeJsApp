Integrate JWT token in to a node based application

To Run the application, Open a terminal and run this.

node server.js // starts server on 8000 port

Now, open a browser and make a request for home page - GET- http://localhost:8000

You will get - "{"success":false,"message":"Auth token is not supplied"}

Our application is preventing us from accessing index without supplying the token. So, lets make post request with 

header - Content-Type : application/json

request method - 'Post'

and data - {"password":"password", "username":"admin"}

url : http://localhost:8000/login

now, notice the json response received as follows

{

 "success": true,
    
"message": "Authentication successful!",
    
"token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6ImFkbWluIiwiaWF0IjoxNTUzNDg5OTU1LCJleHAiOjE1NTM1NzYzNTV9.otGH9i2DUN55vC4fUsQr4szHV6POFwyWykzeUPHuXmY"

}

Now, We can remake our last home page request by adding a bearer token

GET- http://localhost:8000
header - Authorization: Bearer 
token : eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6ImFkbWluIiwiaWF0IjoxNTUzNDg5OTU1LCJleHAiOjE1NTM1NzYzNTV9.otGH9i2DUN55vC4fUsQr4szHV6POFwyWykzeUPHuXmY

So, we will get successful repsonse as follows
{
    "success": true,
    "message": "Index page"
}

This is how JWT authentication works and is now successfully integrated with out node js application.
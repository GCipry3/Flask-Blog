
# Flask-Blog 
```diff
-( Server status : Offline for maintenance)
```

The project is a __web-based__ blog application built using the Flask web framework and Flask-SQLAlchemy extension. 

The __backend__ of the application is powered by Flask and Flask-SQLAlchemy, which handle the server-side logic and database interactions respectively. 

The __frontend__ of the application is built using HTML, CSS, and Bootstrap, which provide the layout and styling for the website. 

![FirstPage](https://github.com/GCipry3/Flask-Blog/blob/main/docs/Home.png)

The application allows users to __create__, __read__, __update__, and __delete blog posts__, as well as manage user accounts and authentication. 
It also provides functionality for __pagination__ and __image uploads__. 
Overall, the project provides a simple and clean blog platform for users to share their thoughts and ideas.


## Application Deployment Scheme

![DeploymentScheme](https://github.com/GCipry3/Flask-Blog/blob/main/docs/ApplicationScheme.png)


## Deployment

For deployment, the project was deployed on an __Amazon Web Services (AWS) 
Elastic Compute Cloud (EC2) instance__, which is a virtual server that allows users to run their applications on the cloud. 

* Inbound Rules for our EC2 instance
![InboundRules](https://github.com/GCipry3/Flask-Blog/blob/main/docs/InboundRules.jpg)

The application is run using __Gunicorn__, a Python Web Server Gateway Interface (WSGI) 
HTTP server, and __Nginx__, a high-performance web server and reverse proxy. 

These technologies work together to allow the application 
to handle multiple requests at once and provide a stable and fast performance. 
The combination of __Gunicorn and Nginx also makes the application visible__ to the 
public by making it accessible through a web browser using a domain name or IP address.

* The application IP address
```http
    http://3.66.169.202/
```

## Maintenance

The project is being maintained by Supervisor, a process control system. 
This allows for the automatic initiation of the application upon server startup, 
through the execution of the command :
```sh
    gunicorn -w 3 run:app
```
Supervisor also manages the logging aspect of the application, 
by directing any errors to __flaskblog.err.log__ and any standard outputs to __flaskblog.out.log__ 
for better monitoring and troubleshooting.

* The Config File:
![ConfigFile](https://github.com/GCipry3/Flask-Blog/blob/main/docs/SupervisorConfigFile.png)

## Run Locally

Clone the project

```bash
  git clone git@github.com:GCipry3/Flask-Blog.git
```

Go to the project directory

```bash
  cd Flask-Blog
```

Install dependencies

* Install python3 , python3 virtual environment module and pip
```bash
  sudo apt install python3 python3-venv python3-pip
```

* Create the virtual environment
```bash
  python3 -m venv .venv
```

* Activate the virtual environment to separate all the necessary dependencies from the computer
```bash
  source .venv/bin/activate
```

* Install the dependencies into the venv
```bash
  pip install -r requirements.txt
```

Start the server

```bash
  export FLASK_APP=run  
```

```bash
  flask run
```

Open the application

* Access the localhost on port 5000 through your browser
```http
  http://localhost:5000/
```

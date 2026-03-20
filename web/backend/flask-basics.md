# Flask Basics

Flask is a **lightweight Python web framework** used to build web applications and APIs.

It provides:

- URL routing
- HTTP request handling
- templating with Jinja2
- development server
- extension ecosystem

Flask follows a **minimal core philosophy**, allowing developers to add only the components they need.

Official Documentation: 
[https://flask.palletsprojects.com/en/stable/](https://flask.palletsprojects.com/en/stable/)

## Table of Contents

- [Installing Flask](#installing-flask)
- [Basic Flask Application](#basic-flask-application)
- [Routing](#routing)
- [Route Parameters](#route-parameters)
- [HTTP Methods](#http-methods)
- [Templates (Jinja2)](#templates-jinja2)
- [Handling Request Data](#handling-request-data)
- [JSON APIs](#json-apis)
- [Project Structure](#project-structure)
- [Development Server](#development-server)
- [Common Use Cases](#common-use-cases)

## Installing Flask

Install Flask with pip:

```bash
pip install flask
```

Verify installation:

```bash
python -m flask --version
```

## Basic Flask Application

A minimal Flask app:

```python
from flask import Flask

app = Flask(__name__)

@app.route("/")
def home():
    return "Hello, World!"

if __name__ == "__main__":
    app.run(debug=True)
```

Run the server:

```bash
python app.py
```

Default server address:

```
http://127.0.0.1:5000
```

## Routing

Flask maps **URLs to Python functions** using routes.

Example:

```python
@app.route("/about")
def about():
    return "About page"
```

When a user visits:

```
/about
```

Flask calls the `about()` function.

## Route Parameters

Routes can accept dynamic parameters.

Example:

```python
@app.route("/user/<name>")
def user(name):
    return f"Hello {name}"
```

Visiting:

```
/user/lizzie
```

returns:

```
Hello lizzie
```

## HTTP Methods

Routes can specify HTTP request methods.

Example:

```python
@app.route("/submit", methods=["GET", "POST"])
def submit():
    return "Form submitted"
```

Common HTTP methods:

| Method | Purpose       |
| ------ | ------------- |
| GET    | Retrieve data |
| POST   | Send data     |
| PUT    | Update data   |
| DELETE | Remove data   |

## Templates (Jinja2)

Flask uses Jinja2 templates to generate HTML dynamically.

Example:

```python
from flask import render_template

@app.route("/")
def home():
    return render_template("index.html")
```

Template file:

```
templates/index.html
```

Example template:

```html
<h1>Hello {{ name }}</h1>
```

## Handling Request Data

Flask provides access to request data through the request object.

Example:

```python
from flask import request

@app.route("/login", methods=["POST"])
def login():
    username = request.form["username"]
    return f"Hello {username}"
```

Common request data sources:

| Source         | Description          |
| -------------- | -------------------- |
| `request.args` | URL query parameters |
| `request.form` | form data            |
| `request.json` | JSON request body    |

## JSON APIs

Flask is commonly used to build REST APIs.

Example:

```python
from flask import jsonify

@app.route("/api/data")
def data():
    return jsonify({
        "message": "Hello",
        "status": "ok"
    })
```

Response:

```json
{
  "message": "Hello",
  "status": "ok"
}
```

## Project Structure

A simple Flask project:

```
project/
├── app.py
├── templates/
│   └── index.html
├── static/
│   ├── css/
│   └── js/
```

Folders:

| Folder    | Purpose         |
| --------- | --------------- |
| templates | HTML templates  |
| static    | CSS, JS, images |

## Development Server

Run the Flask development server:

```bash
flask run
```

Enable debug mode:

```bash
flask run --debug
```

Debug mode provides:

- automatic reload
- detailed error pages

## Common Use Cases

Flask is commonly used for:

- REST APIs
- backend services
- small web apps
- prototypes
- machine learning APIs
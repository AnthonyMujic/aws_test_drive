# aws_test_drive
Deploy a python application using AWS serverless technology

## Application stack
* Flask

## CI/CD technology
* Amazon CDK

## Hosting 
* AWS Lambda

---

## Creating a basic Flask application

1. Install flask

```python
pip install flask
```

2. Create ```app.py``` and add the following:

```python
from flask import Flask

app = Flask(__name__)

@app.route("/")
def index():
    return "<p>Hello from AWS!</p>"
```
3. Run the application locally

```
flask run
```
You will be warned that 'This is a development server. Do not use it in a production deployment. Use a production WSGI server instead.' This is fine for local development, but considering the intention of this exercise is to see how to deploy to production, we need to use a production server instead.

I have heard good things about gunicorn, so let's set it up.

4. Create ```requirements.txt``` to track application dependencies, in it add the following

```
flask
gunicorn
```
Then run:
```
pip install -r requirements.txt
```
5. To server the application from gunicorn run
```
gunicorn -w 4 'app:app'
```
Now that we have a runnable application, time to commit our changes and deploy it to AWS lambda.






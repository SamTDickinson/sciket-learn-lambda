# scikit-learn-lambda
 
Steps for creating packages for your aws lambda layers. I need it to scikit-learn, but can be used for any
project and packages.


What you need: 

Docker
AWS CLI

Add your requirements to requirements.txt

Then from your terminal run

```shell
docker run --rm -v $(pwd):/foo -w /foo lambci/lambda:build-python3.8 \
    pip install -r requirements.txt -t python
```

We are using docker-lambda for replicating the aws lambda environment. Which creates a docker layer and downloads it if needed, creates the lambda
layer in a python file as required by aws and installs all the requirements for you.

You can then zip up the python folder and create your lambda layers

```shells

 zip -r scikit-learn.zip python
 ```
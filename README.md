# my-aws-python-packages

## build docker image
```
docker build -t my-aws-python-packages -f ./Dockerfile ./
```

## Run container, mount folders, pass aws keys
```
docker run -it --name my-aws-python-packages -p 8888:8888 --mount type=bind,source="$(pwd)/work",target=/home/jovyan/work --mount type=bind,source="$(pwd)/packages",target=/home/jovyan/packages -e AWS_ACCESS_KEY_ID=$(aws --profile default configure get aws_access_key_id) -e AWS_SECRET_ACCESS_KEY=$(aws --profile default configure get aws_secret_access_key) my-aws-python-packages
```

## Stop container
```
docker stop my-aws-python-packages
```

## Remove container
```
docker container rm my-aws-python-packages
```

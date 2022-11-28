# Project-s3-cfn
A Secure S3 bucket creation using Cloudformation.
Add additional security features to an existing cloudformation stack.

The current, basic cloudformation template doesn't contain any additional security featuress/configurations.cfn-nag reports show 3 warnings. We will extend the cloudformation template accordingly with all the S3 security features. 

# Setup - 

## Start localstack

```shell
docker-compose up
```

## Authentication
```shell
export AWS_ACCESS_KEY_ID=xxxx
export AWS_SECRET_ACCESS_KEY=xxxx
export AWS_REGION=xxxx
```
## AWS CLI examples
### S3
```shell
aws --endpoint-url http://localhost:4566 s3api list-buckets
```

## Create Stack
```shell

aws --endpoint-url http://localhost:4566 cloudformation create-stack --stack-name project-s3 --template-body file://stack.template --parameters ParameterKey=BucketName,ParameterValue=my-test

```

<img width="1630" alt="image" src="https://user-images.githubusercontent.com/82893856/204152978-2d9460f8-dd86-4be4-aa3d-8c642c378acb.png">

## CFN-NAG Report

### Show last report

```shell
docker-compose restart cfn-nag
docker logs cfn-nag

```

<img width="713" alt="image" src="https://user-images.githubusercontent.com/82893856/204153034-91d75d08-fd3d-4775-8197-9575942ec903.png">




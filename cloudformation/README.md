# Cloudformation assignment

Add additional security features to an existing cloudformation stack.

# Assignment

The current, basic cloudformation template doesn't contain any additional security featuress/configurations. Please have a look at the cfn-nag report. There are a couple of findings which have to be fixed. Please extend the cloudformation template accordingly.

# Setup - 

## Start localstack

```shell
docker-compose up
```

## Authentication
```shell
export AWS_ACCESS_KEY_ID=foobar
export AWS_SECRET_ACCESS_KEY=foobar
export AWS_REGION=eu-central-1
```
## AWS CLI examples
### S3
```shell
aws --endpoint-url http://localhost:4566 s3api list-buckets
```

## Create Stack
```shell

aws --endpoint-url http://localhost:4566 cloudformation create-stack --stack-name <STACK_NAME> --template-body file://stack.template --parameters ParameterKey=BucketName,ParameterValue=<BUCKET_NAME>

```

## CFN-NAG Report

### Show last report
```shell
docker logs cfn-nag
```
### Recreate report
```shell
docker-compose restart cfn-nag
```


# Create a Development Environment with Okteto, Kubernetes, and Localstack AWS services

This is an example of how to configure and deploy a development environment that includes polyglot microservices, an AWS SQS queue, and an S3 bucket. The AWS infrastructure is deployed using LocalStack to keep things simple.

## Architecture

![Architecture diagram](https://raw.githubusercontent.com/okteto/external-resources-tf-localstack/main/docs/architecture.png)

## Run the demo application in Okteto

### Prequisites:
1. Okteto CLI 2.23 or newer
1. An Okteto account ([Sign-up](https://www.okteto.com/try-free/) for 30 day, self-hosted free trial)
Once this is configured, anyone with access to your Okteto instance will be able to deploy an development environment automatically, including the required cloud infrastructure.


```
$ git clone https://github.com/okteto/external-resources-tf-localstack
$ cd external-resources-tf-localstack
$ okteto context use $OKTETO_URL
$ okteto deploy
```

## Develop on the Menu microservice

```
$ okteto up menu
```

## Develop on the Kitchen microservice

```
$ okteto up kitchen
```

## Develop on the Result microservice

```
$ okteto up check
```

## Notes

This isn't an example of a properly architected perfectly designed distributed app... it's a simple
example of the various types of pieces and languages you might see (queues, persistent data, etc), and how to
deal with them in Okteto.

Happy coding!

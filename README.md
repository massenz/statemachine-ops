# Helm Chart to Deploy Statemachine Server

*Created by M. Massenzio, 2024*

## Overview

This is a simple Helm chart to deploy the [Statemachine Server](https://github.com/massenz/go-statemachine) on a Kubernetes cluster.

## Install

Simply run:

```shell
helm install -n <ns> fsm ./chart
```


## Test

To test functionality, we use [Localstack](#) deployed as a `Pod` via the `localstack.yaml` spec; once deployed, these steps are necessary to create the SQS queues:

```shell
keti awslocal -- aws configure
keti awslocal -- aws sqs create-queue --region us-west-2 \
     --endpoint-url=http://localhost:4566 --queue-name notifications
keti awslocal -- aws sqs create-queue --region us-west-2 \
     --endpoint-url=http://localhost:4566 --queue-name events
```
*(see the test/mkq.sh script)*

- [ ] This should be implemented as a one-time `Job`.

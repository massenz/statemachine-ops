# Helm Chart to Deploy Statemachine Server

*Created by M. Massenzio, 2024*

## Overview

This is a simple Helm chart to deploy the [Statemachine Server](https://github.com/massenz/go-statemachine) on a Kubernetes cluster.

## Install

Simply run:

```shell
helm install -n <ns> fsm .
```

## Limitations

This currently deploys also a local Pod running [Localstack](#) to emulate AWS SQS queues, and requires a number of manual steps.

We need to remove this, and simply use Kafka instead.

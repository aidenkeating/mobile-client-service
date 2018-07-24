[![CircleCI](https://circleci.com/gh/aerogear/mobile-client-service.svg?style=svg)](https://circleci.com/gh/aerogear/mobile-client-service) [![Coverage Status](https://coveralls.io/repos/github/aerogear/mobile-client-service/badge.svg?branch=master)](https://coveralls.io/github/aerogear/mobile-client-service?branch=master)

# Mobile Client Service

## Prerequisites

* Golang (1.10)
* Nodejs

## Setup

```bash
make setup
```

## Build

```bash
# Build the API server
make build
# Build the UI
make ui
```

## Run

### Run locally

```bash
make serve
```

### Run on OpenShift

```bash
oc project <namespace>
oc process -f mobile-client-service.template.yaml | oc create -f -
```

For more information on parameters, run:

```bash
oc process -f mobile-client-service.template.yaml --parameters
```

The OpenShift `oauth-proxy` can also be used with the server using:

```bash
oc project <namespace>
oc process -f auth-proxy-mobile-client-service.template.yaml | oc create -f -
```

This will create a proxy and provide an access token in the `X-Forwarded-Access-Token`
header for each request to the server. 

## Test

```bash
make test
```

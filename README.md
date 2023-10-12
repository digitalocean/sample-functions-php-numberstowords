# Sample Function: PHP Numbers to Words

## Introduction

This repository contains a sample function written in PHP. You can deploy it on DigitalOcean's App Platform as a Serverless Function component or as a standalone Function. Documentation is available at https://docs.digitalocean.com/products/functions.

### Requirements

* You need a DigitalOcean account. If you don't already have one, you can sign up at [https://cloud.digitalocean.com/registrations/new](https://cloud.digitalocean.com/registrations/new).
* To deploy from the command line, you will need the [DigitalOcean `doctl` CLI](https://github.com/digitalocean/doctl/releases).

## Deploying the Function

```
# clone this repo
git clone git@github.com:digitalocean/sample-functions-php-numberstowords.git
```

```
# deploy the project, using a remote build so that compiled executable matched runtime environment
doctl serverless deploy sample-functions-php-numberstowords --remote-build
```

The output from the deploy command will resemble the following.
```
Deploying 'sample-functions-php-numberstowords'
  to namespace 'fn-...'
  on host '...'
Submitted function 'main/n2w' for remote building and deployment in runtime php:default (id: ...)
Deployment status recorded in 'sample-functions-php-numberstowords/.deployed'

Deployed functions ('doctl sls fn get <funcName> --url' for URL):
  - main/n2w
```

## Using the Function
```
doctl serverless functions invoke main/n2w -p number:123
{
  "body": "one hundred and twenty-three"
}
```

You can use that API directly in your browser, with `curl` or with an API platform such as Postman.
Parameters may be passed as query parameters, or as JSON body. Here are some examples using `curl`.

```
curl `doctl sls fn get main/n2w --url`?number=456
```

```
curl -H 'Content-Type: application/json' -d '{"number":"789"}' `doctl sls fn get main/n2w --url`
```

## Project File Structure

- There is a single API implemented in [./packages/default/n2w](./packages/default/n2w).
- The required library is specified in [./packages/default/n2w/composer.json](./packages/default/n2w/composer.json).
- There is a [`build.sh`](./packages/default/n2w/build.sh) to install the required library during deployment.

### Learn More

You can learn more about Functions by reading the [Functions Documentation](https://docs.digitalocean.com/products/functions). 

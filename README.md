# Sample Function: PHP Numbers to Words

## Introduction

This repository contains a sample function written in PHP. You can deploy it on DigitalOcean's App Platform as a Serverless Function component.

**Note: This feature is currently in a [limited beta release](https://docs.digitalocean.com/products/platform/product-lifecycle/#beta). Following these steps may result in charges for the use of DigitalOcean services.**

### Requirements

* You need a DigitalOcean account. If you don't already have one, you can sign up at [https://cloud.digitalocean.com/registrations/new](https://cloud.digitalocean.com/registrations/new).
* You need to have access to the beta release of App Platform Serverless Functions. You can sign up for notifications about beta and early access releases [using this form](https://www.digitalocean.com/nimbella).

## Deploying the Function

During the beta, documentation for Serverless Functions will be available to beta participants only in the [Serverless Functions Closed Beta Google Doc](https://docs.google.com/document/d/1qhxnl4ndb0Jh2WkNnNLa2lAUo6u7EAfLyBlUsaPZA0Y). Please refer to this document for instructions on how to deploy Serverless Functions in App Platform.

## Project File Structure

- There is a single API implemented in [./packages/default/n2w](./packages/default/n2w).
- The required library is specified in [./packages/default/n2w/composer.json](./packages/default/n2w/composer.json).
- There is a [`build.sh`](./packages/default/n2w/build.sh) to install the required library during deployment.

### Learn More

You can learn more about App Platform and how to manage and update your application in [the official App Platform Documentation](https://www.digitalocean.com/docs/app-platform/).

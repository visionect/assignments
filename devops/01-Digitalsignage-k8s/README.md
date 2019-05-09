# Digital signage in Kubernetes - Devops assignment #01

## Introduction

We have a web app for digital signage that is written in golang. We need to dockerize that app and run it in Kubernetes system.

## Submission

Assignment should be submitted by providing a link to accessible `git` repository or `compressed archive`. It should include README file with run instructions.

### 1. Docker

Take our digital signage project located [in our github repo](https://github.com/visionect/digitalsignage) and pack it in Docker image. You can use already compiled executable located [here](https://github.com/visionect/digitalsignage/releases) if you wish.

Make sure that app is available on http://localhost:4000 when running image locally.

### 2. Kubernetes and Helm

Create a Helm configuration that will deploy the above image to Kubernetes system. App should be able to scale horizontally. Provide a public link where app is available in the README.

### 3. Let's Encrypt (bonus)

Ensure that the above app is accessible via HTTPS. Use Let's encrypt service for getting the certificates and make sure they are auto extended.

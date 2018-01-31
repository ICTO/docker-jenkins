# Docker Jenkins enviroment

Jenkins image is build from jenkins/jenkins:lts image with added dependencies
for ICTO :

* ansible
* FPM
* Composer

## Usage

```
docker-compose up
```

Jenkins is available on localhost:8080 ( for first usage, look at the log output
for the admin key ).

## Storage

The jenkins workspace is added as a docker volume.

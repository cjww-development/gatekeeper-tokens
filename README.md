[![Apache-2.0 license](http://img.shields.io/badge/license-Apache-brightgreen.svg)](http://www.apache.org/licenses/LICENSE-2.0.html)

gatekeeper-tokens
==========

Gatekeeper is an OAuth2 and OIDC implementation.

Features
============


Prerequisites
==========
- Scala 2.13.5
- SBT 1.4.9
- MongoDB 4.2

We recommend managing Scala and SBT via SDKMan. SDKMan installation notes can be found [here](https://sdkman.io/install).

With SDKMan install Scala and SBT can be installed with

```
sdk install scala 2.13.5
sdk install sbt 1.4.9
```

For MongoDB, we recommend running MongoDB in docker. To boot a MongoDB image in docker, run

```
docker run -d -p 27017:27017 -v ~/data:/data/db mongo
```

How to run
==========
```
sbt -Dplay.http.router=testing.Routes run
```

test@email.com should be replaced with a email address or domain that's been verified in AWS SES

This will start the application on port *5678*

Running tests
=============
```
sbt compile test it:test
```
To the run the integration tests under `it:test` you will need MongoDB running. Refer to the prerequisites section to understand how to boot MongoDB in docker.

```
sbt clean coverage test it:test coverageReport
```
To run with tests and integration tests with coverage enabled run the above.

Booting in docker
=================
The `docker-boot.sh` file packages gatekeeper into a tgz to be used by the Dockerfile. Docker image is then built from the file and subsequently booted along with MongoDB from the docker-compose file.
  
Run `./docker-boot.sh` to run this process.

License
=======
This code is open sourced licensed under the Apache 2.0 License


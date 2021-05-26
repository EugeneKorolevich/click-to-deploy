# solr-docker

Container solution for Apache Solr.
Learn more about Apache Solr in [official documentation](https://lucene.apache.org/solr/).

## Upstream

- Source for [Apache Solr docker solution](https://github.com/docker-solr/docker-solr/)

## Disclaimer

This is not an official Google product.

## About

This image contains an installation Solr. 

For more information, see the [Official Image Marketplace Page](https://console.cloud.google.com/marketplace/details/google/solr8).

### Prerequisites

Configure [gcloud](https://cloud.google.com/sdk/gcloud/) as a Docker credential helper:

```shell
gcloud auth configure-docker
```
### Pull command

```shell
gcloud docker -- pull marketplace.gcr.io/google/solr8
```
# <a name="table-of-contents"></a>Table of Contents

* [Using Docker](#using-docker)
  * [Running Solr](#running-solr-docker)
    * [Starting a Solr instance](#starting-a-solr-instance-docker)
    * [Adding persistence](#adding-persistence-docker)
  * [Configurations](#configurations-docker)
    * [Using configuration volume](#using-configuration-volume-docker)
* [References](#references)
  * [Ports](#references-ports)
  * [Variables](#references-Variables)

# <a name="using-docker"></a>Using Docker

## <a name="running-solr-docker"></a>Running Solr

### <a name="starting-a-solr-instance-docker"></a>Starting a Solr instance

Use the following content for the `docker-compose.yml` file, then run `docker-compose up`.


```yaml
version: '2'
services:
  solr:
    image: marketplace.gcr.io/google/sonarqube8
    ports:
     - "8983:8983"
    command:
      - solr-precreate
      - gettingstarted
```
Or you can use `docker run` directly:

```shell
docker run --name solr_demo -d -p 8983:8983 solr:8 solr-demo
```


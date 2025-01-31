# EMR to CDP Demo
<div align="center">
<img src="https://github.com/paulvid/emr_to_cdp/raw/master/data/cloudera_logo_darkorange.png" width="820" height="100" align="middle">
</div>

# Overview

This demo offers an example of moving workloads from EMR to CDP.
It automates the following:
* Creating an EMR cluster and uploading Worldwide Bank data and setting up Hive testbench (via nifi flow)
* Downloading Hive one Tez application logs from EMR and upload them to WXM (via nifi flow)
* Creating a CDP cluster and setting up Hive testbench (via nifi flow) 
* Downloading EMR glue information and generating Hive DDL in CDP

# Setup

## Pre-requisites


* AWS cli: Configure AWS cli with your credentials and region
* CDP cli: Configure CDP cli with your credentials and region
* WXM: 
  * Docker
  * Uploader and WXM (uploader.tar and altus.json), see [wiki](https://cloudera.atlassian.net/wiki/spaces/ENG/pages/100831814/Workload+XM+Setup+How+to+collect+upload+workloads+from+customer+clusters)
* Local nifi instance

## Configuration


### 1. Clone this repository
```
git clone https://github.com/paulvid/emr_to_cdp.git
```

### 2. Add data and config files

* Add WXM files to local path:
```
cp [local_path]/altus.json [local_path_to_clone]/scripts/wxm/
cp [local_path]/uploader.tar [local_path_to_clone]/scripts/wxm/
```

* Upload worldwidebank data to S3 bucket (follow the same directory structure)

### 3. Configure nifi

* Add template to your nifi instance
* Setup variables with your data


# Authors

**Paul Vidal** - *Initial work* - [LinkedIn](https://www.linkedin.com/in/paulvid/)

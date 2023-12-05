# Setup Guide

## Pre-requisites :

* Core Python
* Pyspark
* Druid
* Kafka
* MongoDB

## System Requirements :

* Java version 1.8. 0 or More
* Python 3.6
* Druid
* Kafka

## How to set up

First clone project

`git clone` [`https://github.com/shikshalokam/ml-analytics-service.git`](https://github.com/shikshalokam/ml-analytics-service.git)

Checkout latest version or repo

* install python and pip
* add alias python=python3.8 in \~/.bashrc file
* Refresh with source .bashrc command \[Try `python -V` && `pip -V` to confirm the installation]
* Install virtual environment using `pip install virtual env` command or `sudo apt install python3.8-venv` command
* Create a virtual environment using the `python -m venv spark_venv` command
* Activate virtual environment using source `spark_venv/bin/activate` command
* Install the required dependency using `sudo pip install -r requirements.txt`
* Use the `pip list` command to recheck if the dependencies are installed correctly
* Create a config.ini file and add config paths ( In the ml-analytics dir )

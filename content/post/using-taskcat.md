---
title: "Using Taskcat"
date: 2020-06-11T15:46:55+08:00
draft: false
# image: "images/using_taskcat_cover.jpg"
tags: ["IAC", "CLOUD", "AWS"]
categories: ["CLOUD"]
---

#### Let's play with TaskCat in python virtual environment

* Create a working directory

```
cd $HOME
cd python-demos
mkdir python-demo2
cd python-demo2
python3 -m venv .
source ./bin/activate
pip list
```

* Create a file `requirements.txt` with the following content
```
taskcat
```

* Run `pip install -r requirements.txt`
```python
pip install -r requirements.txt

(python-demo2) sais-MBP:python-demo2 sai$ pip list
Package                            Version
---------------------------------- ----------
attrs                              19.3.0
aws-sam-translator                 1.24.0
backports.shutil-get-terminal-size 1.0.0
boto3                              1.13.21
botocore                           1.16.21
certifi                            2020.4.5.1
cfn-lint                           0.33.0
chardet                            3.0.4
dataclasses-jsonschema             2.12.0
decorator                          4.4.2
docker                             4.2.1
docutils                           0.15.2
dulwich                            0.20.2
idna                               2.9
Jinja2                             2.11.2
jmespath                           0.10.0
jsonpatch                          1.25
jsonpointer                        2.0
jsonschema                         3.2.0
junit-xml                          1.9
MarkupSafe                         1.1.1
mock                               2.0.0
mypy-extensions                    0.4.3
networkx                           2.4
pbr                                5.4.5
pip                                19.2.3
pyrsistent                         0.16.0
python-dateutil                    2.8.1
PyYAML                             5.3.1
reprint                            0.5.2
requests                           2.23.0
s3transfer                         0.3.3
setuptools                         41.2.0
six                                1.15.0
tabulate                           0.8.7
taskcat                            0.9.18
typing-extensions                  3.7.4.2
urllib3                            1.25.9
websocket-client                   0.57.0
yattag                             1.13.2
WARNING: You are using pip version 19.2.3, however version 20.1.1 is available.
You should consider upgrading via the 'pip install --upgrade pip' command.
```

* Verify `taskcat` is installed.

```
$ taskcat --version
 _            _             _
| |_ __ _ ___| | _____ __ _| |_
| __/ _` / __| |/ / __/ _` | __|
| || (_| \__ \   < (_| (_| | |_
 \__\__,_|___/_|\_\___\__,_|\__|

version 0.9.18
0.9.18

$ taskcat --help
 _            _             _
| |_ __ _ ___| | _____ __ _| |_
| __/ _` / __| |/ / __/ _` | __|
| || (_| \__ \   < (_| (_| | |_
 \__\__,_|___/_|\_\___\__,_|\__|

version 0.9.18
usage: taskcat [args] <command> [args] [subcommand] [args]

taskcat is a tool that tests AWS CloudFormation templates. It deploys your AWS CloudFormation template in multiple AWS Regions and generates a report with a pass/fail grade for each region. You can specify the regions and number of Availability Zones you want to include in the test, and pass in parameter values from your AWS CloudFormation template.

optional arguments:
  -h, --help          show this help message and exit
  -v, --version       show program's version number and exit
  -q, --quiet         reduce output to the minimum
  -d, --debug         adds debug output and tracebacks
  --profile _PROFILE  set the default profile used.

commands:
  delete - [ALPHA] Deletes an installed package in an AWS account/region
  deploy - [ALPHA] installs a stack into an AWS account/region
  lint - checks CloudFormation templates for issues using cfn-python-lint
  list - [ALPHA] lists taskcat jobs with active stacks
  package - packages lambda source files into zip files. If a dockerfile is present in asource folder, it will be run prior to zipping the contents
  test - Performs functional tests on CloudFormation templates.
  update-ami - Updates AMI IDs within CloudFormation templates
  upload - Uploads project to S3.
```

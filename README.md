# Fetch application, Gbolahan Abiodun

Take home assignment submission.


## Description

"For this exercise, we are asking that you evaluate the code example that we provide, find any existing issues with the code, improve the code to ensure that it meets the provided requirements"

Requirements:
* Must use either the provided Go or Python code as your starting point
* Must accept a YAML configuration as command line argument
* YAML format must match that in the sample provided
* Must accurately determine the availability of all endpoints during every check cycle
* Endpoints are only considered available if they meet the following conditions: Endpoints are only considered available if they meet the following conditions, Endpoint responds in 500ms or less
* Must return availability by domain
* Must determine availability cumulatively
* Check cycles must run and log availability results every 15 seconds regardless of the number of endpoints or their response times

## Changes made

### Input-related Fix

* Issue - The code does assumes that the input config yaml file will always have all the required parameters such as headers, method, body.
Therefore, the code fails for inputs from the config file on lines 7,8 and 15,16.
* Resolution - I improved the code by adding defaults for these parameters if they are absent from any of the config file's yaml array entries.

### Requirement-related Fix

* Issue - Requirement for "must ignore port numbers when determining domain".
* Resolution - I tested with a sample domain that includes a port number, and the script added the port number as part of the domain. I added another split on a colon, in order to strip out the port number

### Installing

* Install yaml module for python. 
```
pip install pyyaml
```
* Rename the file to monitor.py
```
mv main.py monitor.py
```

### Executing program

```
python .\monitor.py .\sample.yaml
```

# Addons
    
> see https://aka.ms/autorest

This is the AutoRest configuration file for Addons RP.



---
## Getting Started 
To build the SDK for Addons, simply [Install AutoRest](https://aka.ms/autorest/install) and in this folder, run:

> `autorest`

To see additional help and options, run:

> `autorest --help`
---

## Configuration



### Basic Information 
These are the global settings for the Addons API.

``` yaml
openapi-type: arm
tag: package-2018-03
```

### Tag: package-2018-03

These settings apply only when `--tag=package-2018-03` is specified on the command line.

``` yaml $(tag) == 'package-2018-03'
input-file:
- Microsoft.Addons/preview/2018-03-01/addons-swagger.json
```

### Tag: package-2017-05

These settings apply only when `--tag=package-2017-05` is specified on the command line.

``` yaml $(tag) == 'package-2017-05'
input-file:
- Microsoft.Addons/preview/2017-05-15/Addons.json
```

---
# Code Generation


---
## C# 

These settings apply only when `--csharp` is specified on the command line.
Please also specify `--csharp-sdks-folder=<path to "SDKs" directory of your azure-sdk-for-net clone>`.

``` yaml $(csharp)
csharp:
  azure-arm: true
  license-header: MICROSOFT_MIT_NO_VERSION
  namespace: Microsoft.Azure.Management.Addons
  output-folder: $(csharp-sdks-folder)/addons/Microsoft.Azure.Management.Addons/src/Generated
  clear-output-folder: true
```


## Python

These settings apply only when `--python` is specified on the command line.
Please also specify `--python-sdks-folder=<path to the root directory of your azure-sdk-for-python clone>`.
Use `--python-mode=update` if you already have a setup.py and just want to update the code itself.

``` yaml $(python)
python-mode: create
python:
  azure-arm: true
  license-header: MICROSOFT_MIT_NO_VERSION
  payload-flattening-threshold: 2
  namespace: azure.mgmt.addons
  package-name: azure-mgmt-addons
  clear-output-folder: true
```
``` yaml $(python) && $(python-mode) == 'update'
python:
  no-namespace-folders: true
  output-folder: $(python-sdks-folder)/azure-mgmt-addons/azure/mgmt/addons
```
``` yaml $(python) && $(python-mode) == 'create'
python:
  basic-setup-py: true
  output-folder: $(python-sdks-folder)/azure-mgmt-addons
```

## Go

These settings apply only when `--go` is specified on the command line.

``` yaml $(go)
go:
  license-header: MICROSOFT_APACHE_NO_VERSION
  clear-output-folder: true
  namespace: addons
```


### Go multi-api

``` yaml $(go) && $(multiapi)
batch:
  - tag: package-2018-03
  - tag: package-2017-05
```

### Tag: package-2018-03 and go

These settings apply only when `--tag=package-2018-03 --go` is specified on the command line.
Please also specify `--go-sdk-folder=<path to the root directory of your azure-sdk-for-go clone>`.

``` yaml $(tag)=='package-2018-03' && $(go)
output-folder: $(go-sdk-folder)/services/preview/addons/mgmt/2018-03-01/addons
```

### Tag: package-2017-05 and go

These settings apply only when `--tag=package-2017-05 --go` is specified on the command line.
Please also specify `--go-sdk-folder=<path to the root directory of your azure-sdk-for-go clone>`.

``` yaml $(tag)=='package-2017-05' && $(go)
output-folder: $(go-sdk-folder)/services/preview/addons/mgmt/2017-05-15/addons
```

## Java

These settings apply only when `--java` is specified on the command line.
Please also specify `--azure-libraries-for-java-folder=<path to the root directory of your azure-libraries-for-java clone>`.

``` yaml $(java)
azure-arm: true
fluent: true
namespace: com.microsoft.azure.management.addons
license-header: MICROSOFT_MIT_NO_CODEGEN
payload-flattening-threshold: 1
output-folder: $(azure-libraries-for-java-folder)/azure-mgmt-addons
```

### Java multi-api

``` yaml $(java) && $(multiapi)
batch:
  - tag: package-2018-03
  - tag: package-2017-05
```

### Tag: package-2018-03 and java

These settings apply only when `--tag=package-2018-03 --java` is specified on the command line.
Please also specify `--azure-libraries-for-java=<path to the root directory of your azure-sdk-for-java clone>`.

``` yaml $(tag) == 'package-2018-03' && $(java) && $(multiapi)
java:
  namespace: com.microsoft.azure.management.addons.v2018_03_01
  output-folder: $(azure-libraries-for-java-folder)/sdk/addons/mgmt-v2018_03_01
regenerate-manager: true
generate-interface: true
```

### Tag: package-2017-05 and java

These settings apply only when `--tag=package-2017-05 --java` is specified on the command line.
Please also specify `--azure-libraries-for-java=<path to the root directory of your azure-sdk-for-java clone>`.

``` yaml $(tag) == 'package-2017-05' && $(java) && $(multiapi)
java:
  namespace: com.microsoft.azure.management.addons.v2017_05_15
  output-folder: $(azure-libraries-for-java-folder)/sdk/addons/mgmt-v2017_05_15
regenerate-manager: true
generate-interface: true
```



## Multi-API/Profile support for AutoRest v3 generators 

AutoRest V3 generators require the use of `--tag=all-api-versions` to select api files.

This block is updated by an automatic script. Edits may be lost!

``` yaml $(tag) == 'all-api-versions' /* autogenerated */
# include the azure profile definitions from the standard location
require: $(this-folder)/../../../profiles/readme.md

# all the input files across all versions
input-file:
  - $(this-folder)/Microsoft.Addons/preview/2018-03-01/addons-swagger.json
  - $(this-folder)/Microsoft.Addons/preview/2017-05-15/Addons.json

```

If there are files that should not be in the `all-api-versions` set, 
uncomment the  `exclude-file` section below and add the file paths.

``` yaml $(tag) == 'all-api-versions'
#exclude-file: 
#  - $(this-folder)/Microsoft.Example/stable/2010-01-01/somefile.json
```


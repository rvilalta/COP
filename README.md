# CONTROL ORCHESTRATION PROTOCOL (COP)

## Overview
COP description

## YANG models for COP

[service-call.yang](https://)

## Using pyang swagger plugin

###Install pyang

### Copy pyang swagger plugin to pyang install directory:

```
sudo cp pyang_plugins/swagger.py /usr/local/lib/python2.7/dist-packages/pyang/plugins/
```

### Run pyang swagger plugin

```
pyang -f swagger service-call.yang -o service-call.json
```

## Try JSON output with SWAGGER editor

[Swagger editor](http://editor.swagger.io/#/)


## To build a server stub

We will use swagger code generator. The obtained swagger files from pyang plugin are in swager v2.0. To generate code from these swagger file version we will need the development branch from swagger code generator:


```
https://github.com/swagger-api/swagger-codegen/tree/develop_2.0
```


Go to swagger-codegen main folder and compile the maven project:

```
mvn clean install
```

Run the code-generator by executing the compiled .jar file:

```
java -classpath 'target/swagger-codegen-2.1.0-SNAPSHOT.jar:target/lib/*' com.wordnik.swagger.codegen.Codegen -i example.json -l jaxrs
```

Run generated server:

```
cd generated-code/javaJaxRS
mvn jetty:run
```


License
-------

Copyright 2015 CTTC.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at [apache.org/licenses/LICENSE-2.0](http://www.apache.org/licenses/LICENSE-2.0)

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.


## jigsaw

### Example

```bash
$ jigsaw -config ./example/config.yaml ./example/trace.json
@startuml
"v1-service" -> "v2-service": Ping Request
"v1-service" <-- "v2-service": Ping Response
"v2-service" -> "v3-service": Pong Request
"v2-service" <-- "v3-service": Pong Response
@enduml
```

![output](https://user-images.githubusercontent.com/8219560/127774843-107403dc-53a6-472e-aac6-60fb30b6ff36.png)

### Usage

```bash
$ go get -u github.com/upamune/jigsaw
$ jigsaw trace.json -c config.yaml
```

```bash
$ cat config.yaml
include_services:
  - foo-service
  - bar-service
exclude_grpc_services:
  - /foo.bar.v0.Service
grpc_serivce_alias:
  /foo.bar.v1.Service: v1-serivce
  /foo.bar.v2.Service: v2-serivce
```

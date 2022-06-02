# protoc-gen-http-map
kratos proto helper to get all service api path and its related operation
base on Kratos `protoc-gen-go-http`cmd
To Use
1. compile protoc
2. Add line in Makefile of a kratos project
```bash
.PHONY: api
# generate api proto
api:
	protoc --proto_path=./api \
	       --proto_path=./third_party \
 	       --go_out=paths=source_relative:./api \
 	       --go-http_out=paths=source_relative:./api \
 	       --http-map_out=paths=source_relative:./api \
 	       --go-grpc_out=paths=source_relative:./api \
 	       --openapi_out==paths=source_relative:. \
	       $(API_PROTO_FILES)
```
`--http-map_out=paths=source_relative:./api \` is what I added.
# signoz-trace-example
# Bookstore REST API using Gin and Gorm

Read this [article](https://blog.logrocket.com/how-to-build-a-rest-api-with-golang-using-gin-and-gorm/) on understand how to build a sample golang app using Gin and Gorm.

## Note:
If you are using the `without-instrumentation` branch to instrument the app following the [blog post present here](https://signoz.io/opentelemetry/go/), after you are done with making the necessary changes in the `main.go` file, run:

```
go mod tidy
```
to download the required packages and populate the go.sum file. 


## To run and configure app to send data to SigNoz by http:
```
SERVICE_NAME=goApp OTEL_EXPORTER_OTLP_ENDPOINT=<IP of SigNoz backend>:4318 go run main.go
```

This runs the gin application at port `8090`. Try accessing API at `http://localhost:8090/books`

Below are the apis available to play around. The API calls will generate telemetry data which will be sent to SigNoz which can be viewed at `<IP of SigNoz backend>:3000`
```
GET    /books                    
GET    /books/:id               
POST   /books                    
PATCH  /books/:id                
DELETE /books/:id                
```
default: fmt lint install generate

tools:
	go install github.com/golangci/golangci-lint/v2/cmd/golangci-lint@v2.4.0

build:
	go build -v ./...

install: build
	go install -v ./...

lint:
	golangci-lint run

generate:
	cd tools; go generate ./...

fmt:
	gofmt -s -w -e .

test:
	go test -v -cover -timeout=120s -parallel=10 ./...

testacc:
	TF_ACC=1 go test -v -cover -timeout 120m ./...

.PHONY: fmt lint tools test testacc build install generate

- > 製作容器映像檔時有個常見的原則: 映像檔越小越好
- ## Example
	- ```Dockerfile
	  FROM alpine AS base
	  RUN apk add --no-cache curl wget
	  
	  FROM golang:1.9.2 AS go-builder
	  WORKDIR /go
	  COPY *.go /go/
	  RUN CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -o main .
	  
	  FROM base
	  COPY --from=go-builder /go/main /main
	  CMD ["/main"]
	  ```
- ## Stages
	- ### Stage 0 (base)
		- ```dockerfile
		  FROM alpine AS base
		  RUN apk add --no-cache curl wget
		  ```
		- 使用 `AS <NAME>` 將 **Stage 0** 命名為 `base`
		- 以 `alpine` 為 parent image 建立中間映像檔，並在裡面安裝所需的套件 (curl, wget)
	- ### Stage 1 (builder)
		- ```dockerfile
		  FROM golang:1.9.2 AS go-builder
		  WORKDIR /go
		  COPY *.go /go/
		  RUN CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -o main .
		  ```
		- 將 **Stage 1** 命名為 `go-builder`
		- 編譯 packages & dependencies
	- ### Stage 2
		- ```dockerfile
		  FROM base
		  COPY --from=go-builder /go/main /main
		  CMD ["/main"]
		  ```
		- 利用 **stage 0** (stage base) 建立好的中間映像檔作為 parent image
		- 利用 `COPY` 取得剛剛在 stage 1 (stage go-builder) 產生的 artifacts
- ## Reference
- [透過 Multi-Stage Builds 改善持續交付流程](https://tachingchen.com/tw/blog/docker-multi-stage-builds/)
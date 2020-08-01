FROM golang AS building

WORKDIR /app
ADD . /app
RUN go build -o testgo

FROM alpine
WORKDIR layer
COPY --from=building /app/testgo /layer/
ENTRYPOINT ./testgo

# Security P2

## Read report/Report.org

## Create certificates
``` sh
openssl genrsa -out server-key.pem 4096
openssl req -new -key server-key.pem -out server.csr -passout pass:3 -subj "/C=FR/ST=./L=./O=ACME Signing Authority Inc/CN=localhost"
openssl x509 -req -days 365 -passin pass:3 -in server.csr -key server-key.pem -set_serial 01 -out server-cert.pem 
```

## Run server and client
``` sh
npm run server
npm run client
```

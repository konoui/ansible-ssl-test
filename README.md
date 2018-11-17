# Usage
## Development
```
vagrant up
vagrant provision
```


# Client Authentication with SSL/TLS
## TEST
```
openssl rsa -noout  -modulus -in /vagrant/tmp/target01_key.pem  | openssl md5
openssl x509 -noout -modulus -in /vagrant/tmp/target01.cert.pem  | openssl md5
```

```
curl --key /vagrant/tmp/target01_key.pem --cert /vagrant/tmp/target01.cert.pem https://localhost -k
```

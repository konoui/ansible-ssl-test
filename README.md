# Usage
## Development
```
vagrant up
vagrant provision
```


# Client Authentication with SSL/TLS
## Setup
```
sudo yum install httpd -y

sudo vim /etc/httpd/conf.d/ssl.conf

add following sentence

SSLCACertificateFile /etc/pki/CA/certs/ca_cert.pem
SSLVerifyClient require
SSLVerifyDepth  10
```

## TEST
```
curl --key /vagrant/tmp/target01_key.pem --cert /vagrant/tmp/target01.cert.pem https://localhost -k
```

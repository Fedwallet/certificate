Implementation of a certificate authority using OpenSSL tools.

The root pair--which forms the identity of the certificate authority-- consists of the root key (ca.key.pem) and the root certificate (ca.cert.pem). The root pair configuration is stored in root/ca/openssl.cnf. Values are based off the 'man ca' and 'man x509v3_config' pages.

The root directory also contains directories for certs (which holds the root certificate), a certificate revocation list, new certs, and a private directory to hold the root key.

In addition to the root, there also exists an intermediate certificate authority. The intermediate CA signs certs on behalf of the root, which is only used to sign for the intermediate CA (forming a chain of trust).

The intermediate CA has a similar structure to that of the root, containing directories to hold the intermediate certificate and certs of web servers signed by the intermediate CA, a certificate revocation list, new certs, a private directory to hold the intermediate CA's key and keys issued to web servers, and in addition a directory to hold certificate signing requests. The intermediate CA also contains a certificate chain file in order to verify future certificates signed by the intermediate CA. 

```
ssh-keygen
id_rsa	id_rsa.pub
```

```
cat ~/.ssh/authorized_keys
ssh-rsa AAAAB3NzaC1yc...KhtUBfoTzlBqRV1NThvO04opzEwRQo1mWx user1
```

```
ssh -i id_rsa user1@server1
```

**Copy the SSH key on the remote server**

```
ssh-copy-id -i newkey user1@server1
```

---

Certificates are basically formatted in x509 style

This x509 is then encoded in ASN.1 - which is machine readable

ASN.1 - can be secured or encoded in `.csr` `.pem` `.key` `.pkcs12` etc., formats.

```
> openssl genrsa -out my-bank.key 1024
my-bank.key
```

```
> openssl rsa -in my-bank.key -pubout > mybank.pem
my-bank.key mybank.pem
```

`mybank.pem` contains the public key (may also contain certificate chain until root, and private key)

PEM - Privacy Enhanced Mail 

`my-bank.key` is the private key

---

https://serverfault.com/questions/9708/what-is-a-pem-file-and-how-does-it-differ-from-other-openssl-generated-key-file

**PEM** - Privacy Enhanced Mail

Contains public key (`/etc/ssl/certs`) and may contain private key and certificate chain until root

**CSR** - Certificate Signing Request

This is the format in which a request is made to the signing authority to get a public certificate signed.

Contains public key and the meta data that proves that you own that public key.
Returns a signed public key.

**Example to generate `.csr` for OPENSSL**

```
openssl req -new -key my-bank.key -out my-bank.csr -subj "/C=US/ST=CA/O=MyOrg, Inc./CN=mydomain.com"

# Another example where details are prompted interactively
sudo openssl req -new -newkey rsa:2048 -nodes -keyout app01.key -out app01.csr
```

Above command generates two files 

1. `.key`
2. `.csr`

CSR should be present in `/etc/httpd/csr` 

**KEY** 

**PEM** formatted file with just the `private` key. Usually, **PEM** only contains public key (and optionally certificate chain until root)

**PKCS12** or **PFX** or **P12**

Contains both public and private keys.

`openssl` can convert this into `.pem` file - again containing both public and private keys

---

### Public Keys

`.pem` `.crt`

### Private Keys

`.key` `-key.pem`

---

### Create Self-Signed Certificate

Certs should be present in `/etc/httpd/certs`

When the below command is executed, same information as when generating a `.csr` is prompted.

```
sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout app01.key -out app01.crt
```

---

### Updating Apache with the keys (public and private)

Config is present at `/etc/httpd/conf.d/ssl.conf`

---

### Check which cert is used by `httpd`

```
echo | openssl s_client -showcerts -servername app01.com -connect app01:443 2>/dev/null | openssl x509 -inform pem
```


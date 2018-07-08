# OpenSSL

## Generate public key from private key

```
openssl rsa -in your-private-key.pem -pubout > your-public-key.pub
```

If you need to ommit `writing RSA key` from the output, you need to redirect sterr with `2>/dev/null`

# kms

## Decrypting a blob with the AWS CLI

```
aws kms decrypt --ciphertext-blob fileb://file_path \
				--output text \
				--query Plaintext \
	| base64 -d
```

where:
* `ciphertext-blob`: (required) The ciphered text be decrypted
* `fileb`: binary reads from the file path
* `output`: outputs content in the specified format, text in this example
* `query`: returns only the Plaintext field of the query

There return of `Plaintext` is base64 encoded, parse it with `base64 -d` to decode

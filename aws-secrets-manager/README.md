# AWS Secrets Manager

AWS Secrets Manager is a managed service to store and transport sensitive data launched by AWS in the end of 2017.

## Key features

* Access control with IAM policies
* Auditable via CloudTrail and CloudWatch
* Secrets can be versioned
* Built in integration with RDS

### Secret storage

Secrets are encrypted at rest using KMS keys and tansmited over the wire with TLS. Secrets Manager creates a default key call `DefaultEncryptionKey` in KMS but a custom can also used.

### Secret rotation

The following options are available to rotate secrets:

* Schedule
* AWS Console
* AWS SDK
* AWS CLI

### Secret retrieval 

Secretes can be retrieved via:

* AWS Console
* SDK 
* CLI.

### Pricing

* $0.40 per month, per secret
* $0.05 per 10,000 API calls

## Limitations

* No cross account access
* Secrets are stored per region
* Secret retrieval is done by name and not by ARN

## CLI usage

Creating a secret

```bash
aws secretsmanager create-secret --name testSecret --description "this is a test" --secret-string "23sf23c#et"
{
    "ARN": "arn:aws:secretsmanager:REGION:ACCOUNTNUMBER:secret:testSecret-ID",
    "Name": "testSecret",
    "VersionId": "VERSIONGUID-ab12-1234-123a-123456789"
}
```

Retrieving a secret

```bash
aws secretsmanager get-secret-value --secret-id ${secret_name}
```

List secrets defined in secret manager

```bash
aws secretsmanager list-secrets
```

## Reference

* https://aws.amazon.com/secrets-manager/
* https://aws.amazon.com/secrets-manager/features/
* https://docs.aws.amazon.com/secretsmanager/latest/userguide/intro.html

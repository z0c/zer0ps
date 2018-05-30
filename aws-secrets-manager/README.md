# AWS Secrets Manager

AWS Secrets Manager is a managed service to store and transport sensitive data launched by AWS in the end of 2017.

## Key features

* Access control with IAM policies
* Auditable via CloudTrail and CloudWatch
* Secrets can be versioned
* Built in integration with RDS

### Secret storage

Secrets are encrypted at rest using KMS keys and tansmited over the wire with TLS. Secrets Manager creates a default key call `DefaultEncryptionKey` in KMS but a custom can also used.

The permissions required to retrive secrets are:
* secretsmanager:GetSecretValue
* kms:Decrypt - Required only if using a custom key for encryption

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
* CLI

### Pricing

* $0.40 per month, per secret
* $0.05 per 10,000 API calls

## Limitations

* No cross account access
* Secrets are stored per region
* Support for on perm

## CLI usage

### Creating a secret

```bash
aws secretsmanager create-secret --name testSecret --description "this is a test" --secret-string "kjdgsaIITAG&GIGVJV1213"
{
    "ARN": "arn:aws:secretsmanager:REGION:ACCOUNT:secret:testSecret-ID",
    "Name": "testSecret",
    "VersionId": "VERSIONGUID-ab12-1234-123a-123456789"
}
```

### List secrets

```bash
aws secretsmanager list-secrets
{
    "SecretList": [
        {
            "ARN": "arn:aws:secretsmanager:REGION:ACCOUNT:secret:testSecret-ID",
            "Name": "testSecret",
            "Description": "VERSIONGUID-ab12-1234-123a-123456789",
            "LastChangedDate": 1527694267.157,
            "SecretVersionsToStages": {
                "a12345b-ab12-1234-123a-123456789"": [
                    "AWSCURRENT"
                ]
            }
        }
    ]
}
```

### Retrieving a secret

```bash
aws secretsmanager get-secret-value --secret-id testSecret
{
    "ARN": "arn:aws:secretsmanager:REGION:ACCOUNT:secret:testSecret-ID",
    "Name": "testSecret",
    "VersionId": "VERSIONGUID-ab12-1234-123a-123456789",
    "SecretString": "kjdgsaIITAG&GIGVJV1213",
    "VersionStages": [
        "AWSCURRENT"
    ],
    "CreatedDate": 1527694267.151
}
```
The `secret-id` value can be either the friendly name or the secret ARN 

The `query` parameter can be used to filter just the `SecretString` part of the output:

```bash
aws secretsmanager get-secret-value --secret-id testSecret --query SecretString
"kjdgsaIITAG&GIGVJV1213"
```

### Deleting a secret

```bash
aws secretsmanager delete-secret --secret-id testSecret --recovery-window-in-days 7
{
    "ARN": "arn:aws:secretsmanager:REGION:ACCOUNT:secret:testSecret-ID",
    "Name": "testSecret",
    "DeletionDate": 1528300247.205
}
```

If the `recovery-window-in-days` is not specified it will default to 30 days. The minimum value is 7 days.

## Reference

* https://aws.amazon.com/secrets-manager/
* https://aws.amazon.com/secrets-manager/features/
* https://docs.aws.amazon.com/secretsmanager/latest/userguide/intro.html
* https://docs.aws.amazon.com/cli/latest/reference/secretsmanager/index.html#cli-aws-secretsmanager
* https://docs.aws.amazon.com/secretsmanager/latest/userguide/auth-and-access_overview.html

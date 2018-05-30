# AWS Secrets Manager

AWS Secrets Manager is a managed service to store and transport sensitive data launched by AWS in the end of 2017.

## Key features

* Access control with IAM policies
* Auditable via CloudTrail and CloudWatch
* Secrets can be versioned
* Built in integration with RDS

## Secret storage

Secrets are encrypted at rest using KMS keys and tansmited over the wire with TLS.

## Secret rotation

The following options are available to rotate secrets:

* Schedule
* AWS Console
* AWS SDK
* AWS CLI

## Secret retrieval 

Secretes can be retrieved via:

* AWS Console
* SDK 
* CLI.

## Pricing

* $0.40 p/month p/secret
* $0.05 per 10,000 API calls

## Reference

* https://aws.amazon.com/secrets-manager/
* https://aws.amazon.com/secrets-manager/features/
* https://docs.aws.amazon.com/secretsmanager/latest/userguide/intro.html

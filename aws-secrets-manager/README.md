# AWS Secrets Manager

AWS Secrets Manager is a managed service to store and transport sensitive data launched by AWS in the end of 2017.

## Key features

* Access control with IAM policies
* Auditable via CloudTrail and CloudWatch
* Secrets can be versioned
* Built in integration with RDS

## Secret storage

Secrets are encrypted at rest using KMS keys.

## Secret rotation

The following options are available to rotate secrets:

* Schedule
* AWS Console
* AWS SDK
* AWS CLI

## Reference

* https://aws.amazon.com/secrets-manager/

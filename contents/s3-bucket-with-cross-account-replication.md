# Creating an AWS S3 Bucket with cross account replication

How to setup replication in for S3 buckets accross different accounts

1. Create a S3 bucket in the destination account.

2. In the source bucket select `Management` and the `Replication`

3. Select the `Get started` option.

4. Under `Set source` select the contents to be replicated. Folders can be set using a `/` at the end.

5. Under `Storage class transition` sekect `Buckets in another account` and enter the Account ID and Bucket name.

... Incomplete

from https://stackoverflow.com/questions/49244504/s3-cross-account-and-cross-region-data-sync

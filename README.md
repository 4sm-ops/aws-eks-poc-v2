# Implemented security controls 

## External secrets

EKS Cluster with the External Secrets Operator. The cluster is populated with a ClusterSecretStore and SecretStore example using SecretManager and Parameter Store respectively. A secret for each store is also created. Both stores use IRSA to retrieve the secret values from AWS.

## AWS for Fluent Bit

Fluent Bit is an open source Log Processor and Forwarder which allows you to collect any data like metrics and logs from different sources, enrich them with filters and send them to multiple destinations.

AWS provides a Fluent Bit image with plugins for both CloudWatch Logs and Kinesis Data Firehose. 

Configured to stream the worker node logs to CloudWatch Logs by default. 

## TLS with AWS PCA Issuer

- Enables cert-manager module
- Enables cert-manager CSI driver module
- Enables aws-privateca-issuer module
- Creates AWS Certificate Manager Private Certificate Authority, enables and activates it
- Creates the CRDs to fetch tls.crt, tls.key and ca.crt , which will be available as Kubernetes Secret.

# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## 1.2.1
- Revert to using the full service name for the CN. There is an open issue in 
  EKS in which the SAN is not added to the signed certificates, making the 
  TLS requests from the apiserver to the webhook fail.
  https://github.com/awslabs/amazon-eks-ami/issues/341

## 1.2.0

- Use a much shorter common name for the certificate (only the Service's name)
  to avoid problems due to the character limit in CNs.

## 1.1.1

- Updated musl library to avoid security vulnerability: https://app.snyk.io/vuln/SNYK-LINUX-MUSL-458116

## 1.1.0

### Changed

- Container user is now is `1000` instead of `root`

## 1.0.1

### Added

- Better compatibility with Openshift by patching the webhook configuration json with an `add` operation instead of `replace`.

## 1.0.0
- Initial version of the Kubernetes Webhook Certificate Manager.

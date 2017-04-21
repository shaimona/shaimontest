
Cloud Custodian: Cloud Custodian an is opensource project from CapitalOne.
It is a rules engines for AWS fleet management. It allows users to define policies
to enable a well managed cloud infrastructure.

Cloud Custodian can be used to manage AWS accounts by ensuring real time compliance
to security policies (IAM policies, SecurtyGroups etc), tag policies and cost
management.

For more information visit Cloud Custodian github https://github.com/capitalone/cloud-custodian
For documentation: http://www.capitalone.io/cloud-custodian/docs/

cloud_custodian.yaml: CloudFormation template for setting up a Amazon Linux
Cloud Custodian server. Cloud init script in this template will download Cloud
Custodian, create install script, create SQS queue, create SES lambda function.

Custodian_policy.yml: Custodian policy file.

Quick Install: Create a CloudFormation stack using cloud_custodian.yaml
Copy custodian_policy.yml file to /opt/custodian_policies in custodian server
Run /opt/cloud-custodian/tools/c7n_mailer/bin/custodian run -s . \
    /opt/custodian_policies/policy.yml --region us-west-2 --cache 0

``
IAM_Authenticator_Readme.md
pre-requisite:
------------
conjur account
IAM Role arn

### load the policies
- conjur policy load -f authn-iam-aws-prod.yml -b conjur/authn-iam
- conjur authenticator enable --id authn-iam/prod
- conjur policy load -f authn-iam-aws-prod-host.yaml -b data
- conjur policy load -f clients(ec2-apps)-grants.yaml -b conjur/authn-iam/prod
- conjur policy load -b data -f variables.yaml

### cloud configuration Details and variable:
- conjur account: conjur
- conjur_cloud_url: https://edgejwttest.secretsmgr.integration-cyberark.cloud/api
- service_id: prod
- host: host/data/myspace/601277729239/InstanceReadJenkinsExecutorHostFactoryToken
- variables: data/database/username "aws_role_as_username"
            data/database/password "trustedAWSRole@password"
``

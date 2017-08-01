# Security Checklist

## Web application instances

- [ ] Are in a private subnet to block the incoming internet connection

- [ ] Can’t be sshed from outside of the private network.

- [ ] Allow only requests from specific local Ip range

- [ ] All web instances have well defined security groups and there is no open ports to the world.

- [ ] Instances has no ssh keys and has only one key in `~/.ssh/authorizedkeys`

## Nat Gateway

- [ ] In a public network.

- [ ] Can not be pinged

- [ ] Can not be sshed

## Security Groups

- [ ] All security groups are well defined and well named

- [ ] Any irrelevant security group has to be removed

## Load Balancer

- [ ] There is a security group just for load balancer

## IAM & AWS Credentials & Keys

- [ ] Production & staging SSH keys has to be secured with a passphrase.

- [ ] Every AWS user has different different and well defined policies

- [ ] AWS Keys has to be rotated at least in every 6 months. Add a calendar entry that repeats every 6 months.

- [ ] AWS Root key has to be protected well. If no need to use. The access key has to be deleted from AWS panel.

- [ ] Root account shouldn’t be used just to access to AWS. Create an individual AWS account for yourself (as manager)

- [ ] Check every AWS user has MFA

- [ ] Require users to create strong passwords. Check the related setting for this requirement. [docs.aws.amazon.com](http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_passwords_account-policy.html)

- [ ] Check and delete unnecessary keys

- [ ] Encrypt ~/.aws/credentials file in your local

## CloudTrail

- [ ] is active

- [ ] Check the latest CloudTrail archive date on S3

## S3

- [ ] Check if the sensitive files encrypted at S3 

## Database

- [ ] Check if data encryption is enabled on MongoDb

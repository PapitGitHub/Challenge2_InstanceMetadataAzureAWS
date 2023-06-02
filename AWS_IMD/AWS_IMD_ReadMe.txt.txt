To get the metadata on an EC2 instance ?

Fetch metadata from IPv4:
curl -s http://169.254.169.254/latest/dynamic/instance-identity/document

Fetch metadata from IPv6:
curl -6 http://[fd00:ec2::254]/latest/dynamic/instance-identity/document

============================================================================================================
Following command will return the identity of your EC2 instance with details such as instance type, region, and instance ID in JSON format:

Request URL# curl -s http://169.254.169.254/latest/dynamic/instance-identity/document

Response Received#
{
  "accountId": "012345678901",
  "architecture": "x86_64",
  "availabilityZone": "eu-central-1c",
  "billingProducts": null,
  "devpayProductCodes": null,
  "marketplaceProductCodes": null,
  "imageId": "ami-01ff76477b9b30d59",
  "instanceId": "i-0b4ae3f67d725bbe7",
  "instanceType": "t3a.nano",
  "kernelId": null,
  "pendingTime": "2022-06-20T09:51:52Z",
  "privateIp": "172.29.40.136",
  "ramdiskId": null,
  "region": "eu-central-1",
  "version": "2017-09-30"
}
============================================================================================================

Request URL# curl -s http://169.254.169.254/latest/meta-data

Response Received#
ami-id
ami-launch-index
ami-manifest-path
block-device-mapping/
events/
hostname
iam/
identity-credentials/
instance-action
instance-id
instance-life-cycle
instance-type
local-hostname
local-ipv4
mac
metrics/
network/
placement/
profile
public-hostname
public-ipv4
reservation-id
security-groups
services/
============================================================================================================

Use the ec2-metadata tool from AWS to fetch the EC2 instance metadata:

# Download the ec2-metadata script
wget http://s3.amazonaws.com/ec2metadata/ec2-metadata

# Modify the permission to execute the bash script
chmod +x ec2-metadata
============================================================================================================

Get the instance type from within the EC2 instance :

Run the following command on the EC2 instance to get its instance type:
curl -s http://169.254.169.254/latest/meta-data/instance-type
============================================================================================================

Get the public IP address from within an EC2 instance :

Run the following command to get the public IP address of this instance:
curl -s http://169.254.169.254/latest/meta-data/public-ipv4
============================================================================================================
Get the instance id from within an EC2 instance :

Run the following command to get the ID of this instance:
curl -s http://169.254.169.254/latest/meta-data/instance-id
============================================================================================================
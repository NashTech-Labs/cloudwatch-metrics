# Send memory and disk metrics from EC2 instance to Cloudwatch
Some of the metrics included in an EC2 instance are:
1. CPUUtilization
2. DiskReadOps and DiskWriteOps
3. NetworkIn and NetworkOut
4. StatusCheckFailed
5. EBSWriteOps and EBSReadOps

EC2 does not provide OS-level memory usage or disk usage metrics. Therefore we would have to integrate Cloudwatch and get them as custom metrics.

## Pre-requisites
1. Install Cloudwatch agent in the ec2 instance
2. Create IAM role to enable the metrics collection
3. Create Cloudwatch agent configuration file


## Create a configuration file for Cloudwatch
If you create or edit the CloudWatch agent configuration file manually, you can give it any name. For simplicity in troubleshooting, it is recommended that we name it /opt/aws/amazon-cloudwatch-agent/etc/amazon-cloudwatch-agent.json on a Linux server and $Env:ProgramData\Amazon\AmazonCloudWatchAgent\amazon-cloudwatch-agent.json on servers running Windows Server.  

The cloudwatch configurations for Linux and Windows are present in their respective directories in this repository.
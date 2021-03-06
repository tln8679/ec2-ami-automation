# ec2-ami-automation

-Two scripts to add to your crontab. 
  1. ec2-create-image.sh: Creates a full amazon machine image from a currently running instance. 
  2. del-snapshots.sh: Deregisters all amazon images that are older than a date D and then deletes all snapshots that are older than D    (Amazon charges you for storage of snapshots, so you want to clean these up. There is no charge for having AMI's but they must be   deregistered before deleting their associated snapshots)

## Notes
- To use this script you must have the AWS CLI installed on the device that will run the script: https://docs.aws.amazon.com/cli/latest/userguide/awscli-install-linux.html and configured: https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-started.html

- For del-snapshots.sh, you must have you account number for the owners parameter. From the aws console, select support center from the top right corner of the dashboard. When the page loads, your account number/owner id will be at the top of the page.

- If you are not using an ubuntu os you may need to change your use of date to: __PASTDUE=$(date -v -3d "+%Y-%m-%d").

- Change '3d' to whatever length of time you want. If you can afford to keep snapshots associated with 10 Amazon machine images, then change to __PASTDUE=$(date -v -10d "+%Y-%m-%d"); or __PASTDUE=$(date --date="10 days ago" +"%Y-%m-%d"), for ubuntu.

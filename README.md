# ec2-ami-automation
Two scripts to add to your crontab. 
1. Creates a full amazon machine image from a currently running instance. 
2. Deregisters all amazon images that are older than a date D and then deletes all snapshots that are older than D (Amazon charges you for storage of snapshots, so you want to clean these up. There is no charge for having AMI's but they must be deregistered before deleting their associated snapshots)

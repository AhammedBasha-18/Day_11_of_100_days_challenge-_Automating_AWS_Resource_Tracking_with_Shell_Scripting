# Day_11_of_100_days_challenge-_Automating_AWS_Resource_Tracking_with_Shell_Scripting
Title: Automating AWS Resource Tracking with Shell Scripting
Day 11 of 100 Days of DevOps Challenge
Cloud cost management is a critical aspect of DevOps. This document outlines a project for automating AWS resource tracking using shell scripting and AWS CLI.
________________________________________
Steps to Automate Resource Tracking
1.	Setup AWS CLI
Configure the AWS CLI for your environment. Use:
2.	aws configure
3.	Shell Script Overview
o	List active EC2 instances: 
o	aws ec2 describe-instances --query 'Reservations[*].Instances[*].[InstanceId,State.Name]' --output table
o	Retrieve S3 buckets: 
o	aws s3 ls
4.	Schedule the Script with Cron Jobs
o	Add to crontab for daily execution at 6 PM: 
o	0 18 * * * /path/to/script.sh >> /path/to/logfile.log 2>&1
5.	Testing and Debugging
o	Run the script manually to verify functionality.
o	Use tools like jq to format JSON output for readability.

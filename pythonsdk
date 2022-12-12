#!/usr/bin/python

#Boto3 is the AWS SDK for Python
import boto3

#Specify the region here. It would just as easily be an argument
regionid = "us-east-1"

#This initiates communucation with the EC2 service API endpoint
#Note this will only communicate with one region at a time
ec2 = boto3.resource("ec2", region_name=regionid)

#This next line issues an EC2 Describe Volumes operation
#It will filter based on volume status of "available"
available_volumes = ec2.volumes.filter(
  Filters=[{'Name': 'status', 'Values': ['available']}]
)

#This loop will execute a Delete Volume operation on all available volumes
#Note how clean this is using the SDK because we are dealing with objects
#as opposed to the CLI where we deal with strings and JSON
for volume in available_volumes:
  print(volume.id)
  volume.delete()

## S3
	
### Listing 

	aws s3 ls s3://s3Projects/
	aws s3 list 
	aws s3api get-object --if-match "*tfstate"
	aws s3api list-buckets
	aws s3api get-bucket-tagging --bucket "*tfstate"
	aws s3api list-buckets  |grep tfstate
	aws s3api list-account-aliases¶\n
	aws s3api list-buckets |grep tfstate | cut -d\" -f4
	aws s3api list-buckets --output text |grep tfstate | awk '{print $3}'
	aws s3api list-buckets --output text --filters 'Name=tag:Name,Values=xxx'

### Deleting

	aws s3api delete-objects --bucket bucket-name --delete "$(aws s3api list-object-versions --bucket bucket-name | jq -M '{Objects: [.["Versions","DeleteMarkers"][]|select(.Key == "key-value")| {Key:.Key, VersionId : .VersionId}], Quiet: false}')"
	aws s3api delete-objects --bucket s3bucket --delete "$(aws s3api list-object-versions --bucket s3bucket | jq -M '{Objects: [.["Versions","DeleteMarkers"][]|select(.Key == "key-value")| {Key:.Key, VersionId : .VersionId}], Quiet: false}')"

### Writing


## Instance

### describe

	aws ec2 describe-instances --instance-id i-0000
	aws ec2 describe-instances --region eu-central-1 --filters Name=instance-state-name,Values=running Name=instance-type,Values=p3.2xlarge,p3.8xlarge,p3.16xlarge | grep -i InstanceLifecycle

### stop

	aws ec2 stop-instances --instance-id i-0000

### terminate

	aws ec2 terminate-instances --instance-id i-0000

### run

aws ec2 run-instances --image-id ami-016cebe2c5b2257db --instance-type t2.micro --security-group-ids sg-1111 --subnet-id subnet-1111 --key-name key --iam-instance-profile Name=InstanceProfile --region us-west-2 --tag-specifications 'ResourceType=instance,Tags=[{Key=Name,Value=MyEc2}, {Key=Unit,Value=Ec2}, {Key=Owner,Value=Ec2}, {Key=Environment,Value=Sandbox}, {Key=CostCenter,Value=Ec2}, {Key=WBS,Value=Ec2}, {Key=BusinessUnit,Value=Ec2}, {Key=CostAllocationGroup,Value="Ec2 Ec2 Ec2"}, {Key=Application,Value=Ec2}, {Key=InfraLocation,Value=USW2}, {Key=BackupInterval,Value=Daily}, {Key=BackupRetention,Value=Retention_30}, {Key=ServiceLevel,Value=Standard_8X5}, {Key=ScheduerID,Value=True}, {Key=BackupPlan,Value=Yes}]'

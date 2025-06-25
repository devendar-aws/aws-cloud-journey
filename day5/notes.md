### IAM - Identity and Access Management

https://console.aws.amazon.com/iam/

Users > Create user

Specify User details > User Name > aws-cli-user-test (do not check Provide user access to the AWS Management Console) > Next

Set Permissions > Attach policies directly > Permission Policies - Search for Amazons3FullAccess - select > Next

Review and create > Create user

Select aws-cli-user-test > Create access key 

Access Key best practices & alternatives > Select Command Line Interface (CLI) - Acknowledge > Next

Set description tag > CLI access key for test user > Create access key

Retrieve access keys > Download csv. consisting Access key and secret access key > Done 


### Using CLI
Install AWS CLI on local machine from https://awscli.amazonaws.com/AWSCLIV2.msi
Open Gitbash 
aws --version
aws configure 

enter access key, secret access key from the csv file downloaded.
Region - AWS account region ap-south-1
Output - Json


connected to s3 through aws cli on local machine 
aws s3 ls
lists out the buckets in our s3 bucket.

1.Created a file on your local machine using Git Bash:
echo "This is a test file" > dev.txt

2. Copied the local file to your S3 bucket:
aws s3 cp dev.txt s3://devendar-s3-site/

3. Downloaded the file back from S3 to your local machine (to current working directory):
aws s3 cp s3://devendar-s3-site/dev.txt .

4. Deleted the file from your S3 bucket:
aws s3 rm s3://devendar-s3-site/dev.txt

I created, uploaded, downloaded, and deleted files with S3 using the CLI.
I understood the flow of data between your local system and cloud storage.
I'm using programmatic access credentials (aws cli) successfully.

List Buckets and objects
aws s3 ls
aws s3 ls s3://your-bucket-name
aws s3 ls s3://devendar-s3-site

Create and Delete S3 buckets from CLI

1. Create: make_bucket
aws s3 mb s3://your-new-bucket-name

2. Delete: remove_bucket
aws s3 rb s3://your-new-bucket-name --force

3. Delete objects from the bucket
Delete object from the bucket
aws s3 rm s3://your-new-bucket-name/object 

Delete all the objects from the bucket
aws s3 rm s3://your-new-bucket-name --recursive

This will only delete objects from S3 bucket even though the local directory is synced to the S3 bucket

***Disclaimer***
If you use, aws s3 sysc s3://my-bucket  . --delete
this will delete the files from the local machine. 

Sync Directories

 S3 Sync & Move Operations Recap:
1. Synced local files to S3 bucket
aws s3 sync . s3://dev-newbucket-cli
Uploads all files from your current local directory to the dev-newbucket-cli S3 bucket.

2. Synced S3 bucket files to local
aws s3 sync s3://dev-newbucket-cli .
Downloads all files from the S3 bucket to your current local directory.

3. Created a new file locally
echo "Syncing Files" > sync.txt
Creates a sync.txt file containing the text Syncing Files.

4. Moved sync.txt to S3
aws s3 mv sync.txt s3://dev-newbucket-cli
Moves the file from local machine to S3.
It no longer exists in your local directory after this command.

5. Re-synced S3 bucket to local again
aws s3 sync s3://dev-newbucket-cli .
Downloads sync.txt back into your local directory.

I successfully demonstrated bidirectional sync between local and S3, and understood the behavior of mv vs sync.

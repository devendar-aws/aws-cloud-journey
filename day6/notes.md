# Day 5 – AWS S3 CLI & Static Hosting

## Tasks Covered

- Enabled S3 static website hosting via CLI: 


website.json: 
{"IndexDocument": {"Suffix":"index.html"},"ErrorDocument":{"Key":"error.html"}}


aws s3api put-bucket-website --bucket dev-newbucket-cli --website-configuration file://website.json


- Allow Public Access via CLI


aws s3api put-public-access-block --bucket dev-newbucket-cli --public-access-block-configuration 'BlockPublicAcls=false,IgnorePublicAcls=false,BlockPublicPolicy=false,RestrictPublicBuckets=false'

- Set bucket policy via CLI

bucket-policy.json:
{"Version": "2012-10-17", "Statement":[{"Sid": "PublicReadGetObject", "Effect": "Allow", "Principal": "*", "Action": "s3:GetObject", "Resource": "arn:aws:s3:::dev-newbucket-cli/*" }]}

aws s3api put-bucket-policy --bucket dev-newbucket-cli --policy file://bucket-policy.json


- Deployed index.html publicly


## Tools Used
- AWS CLI
- S3
- JSON policies

## Endpoint:
http://dev-newbucket-cli.s3-website-ap-south-1.amazonaws.com/

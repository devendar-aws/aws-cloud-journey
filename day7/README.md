## ✅ Objective:
Host a static website using AWS S3 **entirely via CLI**, including:
- Bucket configuration
- Static hosting setup
- Public access policy

---

## 🧰 Tools Used:
- AWS CLI (v2)
- Amazon S3
- Terminal (Git Bash / PowerShell)

---

## 🪜 Steps Followed:

1. **Created a new S3 bucket**:
   ```bash
   aws s3api create-bucket --bucket dev-newbucket-cli --region ap-south-1

2. **Disabled Block Public Access**:
 aws s3api put-public-access-block \
  --bucket dev-newbucket-cli \
  --public-access-block-configuration BlockPublicAcls=false,IgnorePublicAcls=false,BlockPublicPolicy=false,RestrictPublicBuckets=false


3. Uploaded HTML files:

aws s3 cp index.html s3://dev-newbucket-cli/

4. Enabled static website hosting:

aws s3 website s3://dev-newbucket-cli/ --index-document index.html --error-document error.html

5. Set public-read bucket policy:

    {
      "Version": "2012-10-17",
      "Statement": [
        {
          "Sid": "PublicRead",
          "Effect": "Allow",
          "Principal": "*",
          "Action": "s3:GetObject",
          "Resource": "arn:aws:s3:::dev-newbucket-cli/*"
        }
      ]
    }

Applied using:

        aws s3api put-bucket-policy \
          --bucket dev-newbucket-cli \
          --policy file://bucket-policy.json

🌐 Website Endpoint:

http://dev-newbucket-cli.s3-website.ap-south-1.amazonaws.com/

✅ Hosted successfully via CLI!


#### Learning Outcomes:
- Learned AWS S3 bucket setup via CLI
- Understood public access and policy configs
- Practiced website hosting through AWS CLI
- Gained CLI confidence for real-world cloud workflows

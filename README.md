# 100 Days of AWS - Devendar Nandaiahgari

## Goal: Land a 15-18 lpa Cloud Role by September 29, 2025

### Day 1 - June 21, 2025

- Created GitHub account
- Created my first GitHub repo to track AWS progress
- Tried to create an AWS account

### Day 2 - June 22, 2025

- Completed full AWS account signup and verification
- Set default AWS region to Asia Pacific (Mumbai)
- Explored AWS console layout and services
- Prepared to launch first EC2 instance on Day 3.

### Day 3 - June 23, 2025

- Launched first EC2 instance (Ubuntu 22.04)
- Installed Apache Web Server
- Accessed live Apache Homepage via Public IP
- Cloud project is live
- Created a folder, day3
- Added the screenshot of the apache web page on the browser to the 'day3/' folder [View Screenshot in 'day3/'](day3/apache-page.png)

### Day 3.5 - June 23, 2025 (Self - test)

- Launched and configured a new EC2 instance independently
- Terminated the instance after testing to manage cost and lifecycle
- Gained confidence in navigating AWS Console without step-by-step guidance.


### Day 4 - June 24, 2025

- Created a HTML file on Local Machine.
- Created an S3 bucket by blocking public access and unchecking the warning checkbox, with bucket versioning diabled for now and Bucket key enabled.
- Uploaded the html file to the S3 bucket in objects.
- Enabled S3 static website hosting in S3 bucket Properties.
- Gave Bucket Policy in JSON on S3 bucket's Permissions tab.
- Publicly Accessible project is Live [S3 website endpoint](http://devendar-s3-site.s3-website.ap-south-1.amazonaws.com).
- Created a folder, day4
- Added the screenshot of the Live HTML web page on the browser to the 'day4/' folder [View Screenshot in 'day4/'](day4/live-html-page.png)


### Day 4.5 - June 24, 2025 (Connect using SSH)

#### 🔐 SSH – Secure Shell (Brushed-up Concept)

While practicing EC2 + Linux basics, I revisited the foundational concept of **SSH** — not as something new, but as part of reinforcing what I already understand well from past hands-on experience.

> **SSH (Secure Shell)** is a secure protocol that allows encrypted remote login from one computer to another over the internet.  
> It uses **asymmetric key cryptography** to authenticate access.

##### ✅ What I Brushed Up:

- During EC2 creation, I generated a **key pair**:
  - **Public Key**: Stored in EC2 instance
  - **Private Key (.pem)**: Stored on my local machine

- I changed permissions of the key to secure it:
  chmod 400 private-key.pem

- Then I connected to the instance via SSH:
  ssh -i "private-key.pem" ubuntu@<EC2-Public-IP>

- The connection medium is the internet, and only someone with the correct private key can decrypt the handshake and access the instance.

    In the real world, this ensures secure access control for cloud servers — even if the public IP is exposed.


- Linux Basics on EC2
- Created files, folders, gave permissions to files and modified files on local machine.
- Took screen shot of EC2 instance terminal showing Linux shell and a message from the file created on the local machine.
- Added screenshot of terminal to 'day4/' folder [Screenshot of EC2 terminal](day4/linux-on-ec2.png)



### Day 5 - June 25, 2025 (IAM, CLI) [Day 5 notes](day5/notes.md)

- Installed and configured AWS CLI.
- Created IAM user with programmatic access (CLI).
- Understood aws configure and credentials usage.
- Created a file locally and uploaded it to S3.
- Downloaded the file from S3.
- Deleted the file from S3.
- Create and Delete Buckets and Objects
- Sync local directory to S3 and vice versa.


### Day 6 - June 26, 2025 (AWS S3 CLI & Static Hosting) [Day 6 notes](day6/notes.md)

#### Tasks Covered

- Enabled S3 static website hosting via CLI: 
- Allow Public Access via CLI
- Set bucket policy via CLI
- Deployed index.html publicly

[Endpoint](http://dev-newbucket-cli.s3-website.ap-south-1.amazonaws.com/)

### Day 7 - June 27, 2025 (Static Website Hosting on S3 via AWS CLI) [Day 7 notes](day7/README.md)

- Host a static website using AWS S3 **entirely via CLI**, including:
  - Bucket configuration
  - Static hosting setup
  - Public access policy

1. **Created a new S3 bucket**
2. **Disabled Block Public Access**
3. **Uploaded HTML files**
4. **Enabled static website hosting**
5. **Set public-read bucket policy**
6. **Hosted successfully via CLI!**

[Endpoint](http://dev-newbucket-cli-test.s3-website.ap-south-1.amazonaws.com/)



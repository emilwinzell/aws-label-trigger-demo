# Computer Vision Label Trigger for AWS S3

<span style="color:red">AWS Rekognition not availiable in all regions!</span>

* Step 0: Create new Cloud9 environment in avaliable region (e.g. eu-central-1)
* Step 1: In Cloud9, clone git repo (create ssh key first `ssh-keygen -t rsa`), cd into repo
* Step 2:  `sam init` and follow steps (use hello world template)
* Step 3: `sam build --use-container`
  * If not working could be because of lack of space on disk, check with `df -h` and for row /dev/xvda1 
  * Add more space in EC2 instance settings if necessary
* Step 4: `sam deploy --guided` and follow steps
* Step 5: Go to AWS Lambda and functions and open the recently created function
* Step 6: Click on add trigger and choose S3
* Step 7: Choose an existing bucket or create a new one by opening a new tab and navigating to S3
* Step 8: Leave prefix, add .jpg as a required suffix and create trigger
* Step 9: Go to IAM and click on policys and create new from JSON, paste the following:
```JSON
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "rekognition:*"
            ],
            "Resource": "*"
        }
    ]
}
```
* Still acess denied :((






# Disaster Recovery Plan


![image](https://user-images.githubusercontent.com/104793540/186161098-123115d9-f9c0-42f9-b0cc-7b7b7fc4b69d.png)

- what is s3
- disaster recovery plan 
- how we set up access and keys


```
Update
Upgrade
sudo apt-get install python -y
sudo apt install python3-pip
alias python=python3
python --version
sudo pip3 install awscli
aws configure
aws s3 ls
aws s3 mb s3://eng122-ayanle-bucket
sudo nano test.txt
sudo rm test.txt
aws s3 cp s3://eng122-ayanle-bucket/test.txt /home/ubuntu
output: download: s3://eng122-ayanle-bucket/test.txt to ./test.txt
sudo rm test.txt
```

AWS S3 Acivity:
- 10-15 lines of code max


- sudo apt-get install python3.7
- alias python=python3.7
- curl -O https://bootstrap.pypa.io/get-pip.py # might not need
- sudo apt install python-pip

![image](https://user-images.githubusercontent.com/104793540/186192657-de343c06-72dc-4a53-a743-b3eea098f520.png)

- pip install boto3

![image](https://user-images.githubusercontent.com/104793540/186192478-5ce4a26e-b365-4e13-8b37-3c1fdd95a839.png)

- Before using Boto3, you need to set up authentication credentials for your AWS account using either the IAM Console or the AWS CLI. 
- sudo pip3 install awscli
- aws configure

creating python file:
- sudo nano aws_s3.py

Using Boto3:
To use Boto3, you must first import it and indicate which service or services you're going to use:


#### Client Versus Resource
At its core, all that Boto3 does is call AWS APIs on your behalf. For the majority of the AWS services, Boto3 offers two distinct ways of accessing these abstracted APIs:

- Client: low-level service access
- Resource: higher-level object-oriented service access
You can use either to interact with S3.

To connect to the low-level client interface, you must use Boto3’s client(). You then pass in the name of the service you want to connect to, in this case, s3:

```
import boto3
s3_client = boto3.client('s3')
```

To connect to the high-level interface, you’ll follow a similar approach, but use resource():
```
import boto3
s3_resource = boto3.resource('s3')
import boto3
# Let's use Amazon S3
s3 = boto3.resource('s3')
```


Better way to get the region programatically is by taking advantage of a session object:
- The nice part is that this code works no matter where you want to deploy it: locally/EC2/Lambda. Moreover, you don’t need to hardcode your region.

```
#creating a bucket with region  using session object
def create_bucket(bucket_prefix, s3_connection):
    session = boto3.session.Session()
    current_region = session.region_name
    bucket_name = create_bucket_name(bucket_prefix)
    bucket_response = s3_connection.create_bucket(
        Bucket=bucket_name,
        CreateBucketConfiguration={
        'LocationConstraint': current_region})
    print(bucket_name, current_region)
    return bucket_name, bucket_response
```

![image](https://user-images.githubusercontent.com/104793540/186215017-4ab0bae3-b81a-42ea-a364-0dcaaf4f0690.png)

```python
import boto3
s3 = boto3.client('s3')


s3.create_bucket(Bucket='eng122-ayanle-boto3-bucket', CreateBucketConfiguration={'LocationConstraint':'eu-west-1'})



s3.upload_file(
        'test.txt','eng122-ayanle-boto3-bucket','pythonfile-test.txt')


```
- Type python SCRIPTNAME.py in the terminal to execute the script




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

```
sudo apt-get install python3.7
alias python=python3.7
curl -O https://bootstrap.pypa.io/get-pip.py # might not need
sudo apt install python-pip

![image](https://user-images.githubusercontent.com/104793540/186192657-de343c06-72dc-4a53-a743-b3eea098f520.png)

pip install boto3

![image](https://user-images.githubusercontent.com/104793540/186192478-5ce4a26e-b365-4e13-8b37-3c1fdd95a839.png)

python3 script.py #running python script in ubuntu

```

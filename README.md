# Disaster Recovery Plan


![image](https://user-images.githubusercontent.com/104793540/186161098-123115d9-f9c0-42f9-b0cc-7b7b7fc4b69d.png)

- what is s3
- disaster recovery plan 
- how we set up access and keys

10-15 lines of code max

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

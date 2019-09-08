# ec2-through-python
## Starting and Stopping an ec2 instance using Python







### This is a full guide on starting and stopping an Amazon AWS Ec2 instance through terminal and a Python IDE





### Starting and Stopping the instance through Terminal:

#### WHAT YOU NEED:
### - The rootkey file that is given to you by AWS with your Access Key ID and your Secret Access Key
### - The region name that your server is running in (eg. us-east-1)


<img width="257" alt="Screen Shot 2019-09-08 at 7 42 34 AM" src="https://user-images.githubusercontent.com/54153376/64489929-2b0a1680-d20d-11e9-9885-7297865c7a91.png">

<img width="257" alt="Screen Shot 2019-09-08 at 7 49 55 AM" src="https://user-images.githubusercontent.com/54153376/64489946-4543f480-d20d-11e9-9c7e-6291d942cfe5.png">
  
  
##### To be able to install the AWS command line interface on Terminal, one must download the pip script. Enter terminal, and curl the link: https://bootstrap.pypa.io/get-pip.py:
   
  ```
  curl https://bootstrap.pypa.io/get-pip.py > get-pip.py
 ```

##### We then execute the pip script on the Python that is built in to MacOS terminal:
  
  ```
  sudo python get-pip.py
  ```
##### Because you issued sudo, you will need your password as the ```sudo``` command runs as administrator 
##### You will now see pip script being downloaded by python
   
##### In order for pip to be be able to install other libraries, which in our case is the AWS CLI, we now type in:

    ```
    sudo pip install requests 
    
    ```
##### We now install AWS CLI (Command Line Interface):
 ``` pip install awscli  ```
 
##### Now that we have the AWS CLI installed, we configure it:
 ``` sudo aws configure ```
##### Remember that you will need your password again as  ``` sudo ``` runs as administrator 
#
##### When prompted, you type in the AWS Access Key ID, which will look something like "AKIAIOSFODNN7EXAMPLE"
#
##### When prompted, you will type in the AWS Secret Access Key, which can differ in appearance, but looks something like  " JalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY " , or with ' + ' instead of ' / '
#
##### When prompted, you will type in the region name, or availability zone, which is found in the AWS EC2 Dashboard, and will look something like " us-east-1 "
#
##### When prompted, type the output format you want to use: json, text, or table. I would reccomend table as it is more user friendly, although not programmatically useful.
#
##### You have now configured AWS to connect to your instance
##### whether or not your instance is online or offline, you can see the status of it by typing in ```aws ec2 describe-instances``` Note the instance ID 
##### You will see a similar page if you chose 'table' as the output format 
<img width="691" alt="Screen Shot 2019-09-08 at 8 29 16 AM" src="https://user-images.githubusercontent.com/54153376/64490545-d1a4e600-d212-11e9-8a4e-36e485191c71.png">

### Turn ON and OFF the Instance
#### Now we will turn ON and OFF the EC2 Instance that we have connected to

#### We can turn ON the Instance by entering this command into Terminal:
``` aws ec2 start-instances --instance-ids YOUR ID HERE ```

##### Replace the "YOUR ID HERE' with the instance ID found in the describe instances command we did earlier
##### You should now see something like this: 
<img width="225" alt="Screen Shot 2019-09-08 at 8 35 31 AM" src="https://user-images.githubusercontent.com/54153376/64490627-abcc1100-d213-11e9-8642-3db39c371726.png">
 
##### We can turn OFF the instance by entering this command into terminal:

``` aws ec2 stop-instances --instance-ids YOUR ID HERE ```

##### Replace the "YOUR ID HERE' with the instance ID found in the describe instances command we did earlier

##### You should see something like this: 
<img width="225" alt="Screen Shot 2019-09-08 at 8 38 15 AM" src="https://user-images.githubusercontent.com/54153376/64490655-10876b80-d214-11e9-888b-2a132172dbbd.png">
#

#### Terminating the Instance

#### Once we are done using the instance, we can delete it: ``` aws ec2 terminate-instances --instance-ids YOUR ID HERE ```

#### Replace the "YOUR ID HERE' with the instance ID found in the describe instances command we did earlier

# END
# ---------------------------------------------------

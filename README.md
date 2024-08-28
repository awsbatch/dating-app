Step 1 →setup ec2 on aws
Launch an Amazon EC2 instance: The first step is to create an Amazon EC2 instance on which you’ll install Nginx. Go to the EC2 console, select Launch Instance, and choose ubuntu . Once you’ve selected the AMI, follow the prompts to configure the instance details, such as instance type, storage, and security group.
Configure security group: When configuring your security group, make sure that you allow inbound traffic on port 80, which is the default port used by HTTP.
4. let’s connect to your ec2 via ssh using command “ssh -i “mykey.pem” ubuntu@ec2–54–197–62–157.compute-1.amazonaws.com”

3. run the following commands

a. sudo su

b. apt update

git installation
c. apt install git

clone the github repo by

c. git clone https://github.com/Aakibgithuber/Ask-for-a-date-app.git

Step 2 → setup nginx and docker to build image
run the following commands to install nginx →

a. sudo apt install nginx

Start Nginx: After installation, start the Nginx service

b. sudo systemctl start nginx

You can also enable Nginx to start on boot

c. sudo systemctl enable nginx

Check Nginx Status →To verify that Nginx is running without any errors, you can use

d. sudo systemctl status nginx


Docker installation
a. apt-get install docker.io
b. usermod -aG docker $USER # Replace with your username e.g ‘ubuntu’
c. newgrp docker
d. sudo chmod 777 /var/run/docker.sock → #is used to grant full read, write, and execute permissions to all users for the Docker socket file, which allows unrestricted access to the Docker daemon and is a significant security risk.

run the following commands to build and run docker container →

docker build -t my-dating-app.

b. below command maps the container port to your ec2 port

docker run -d --name netflix -p 8081:80 my-dating-app:latest →

c. go to your ec2 →security groups →open the port 8081 by adding rule custom tcp = 8081


your aplication is running go to your ec2 copy public ip and browse http://your_public_ip:8081 and it’s open like this


if you click on no it will run away

If you click on yes it will redirect you to next page

then choose a date

See you on a Date
This is a simple website if you wanna make it highly available then you could integrate grafana and prometheus for monitering and use EKS for high Availablity you could checkout the project

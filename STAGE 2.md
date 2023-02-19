# STAGE 2

Go to Amazon ECR service main page and click "Get started" 

![image](https://user-images.githubusercontent.com/96197101/219968075-52fd9db2-c0d1-4c5c-b6d5-3cf99655c98c.png)

Fill name for repository and make sure that "Visibility setting" are set to "Private" and click "Create repository".

![image](https://user-images.githubusercontent.com/96197101/219968146-637e5928-9e28-47eb-a4c2-18c2368426fc.png)

Got to Amazon EC2 service page and click in the left pane "Instances". There is an instance that were created during deployment of Cloudformation stack in stage 0.

![image](https://user-images.githubusercontent.com/96197101/219968351-9e1ffe37-8b88-454c-9614-76e0f2cdbcc9.png)

Run commands to install docker and unzip app.

<code>sudo amazon-linux-extras install docker -y
sudo service docker start
sudo usermod -a -G docker ec2-user
sudo su - ec2-user
unzip app.zip
</code>

Next run below commands to build and push docker image of app to Amazon ECR.

-Build the Docker image: <code>docker build -t skynet . </code>

-Tag the Docker image: <code>docker tag skynet:latest <AWS Account ID>.dkr.ecr.us-east-1.amazonaws.com/skynet-repo:latest</code>
  
-Login to the ECR repository: <code>aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin <AWS Account ID>.dkr.ecr.us-east-
1.amazonaws.com</code>
  
-Push the Docker image to the ECR repository: <code>docker push <AWS Account ID>.dkr.ecr.us-east-1.amazonaws.com/skynet-repo:latest</code>
  
  
Pushed app image in Amazon ECR repository that was created on the begining of this stage.
  
  ![image](https://user-images.githubusercontent.com/96197101/219969086-bdbd1f7e-7c60-47c1-b79b-6a9894dc3527.png)

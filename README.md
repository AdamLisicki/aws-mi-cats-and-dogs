# aws-mi-cats-and-dogs

![alt text](https://raw.githubusercontent.com/AdamLisicki/aws-ml-cats-and-dogs/main/aws-mi-cats-and-dogs-diagram.drawio%20(2).png)


## STAGE 0

Apply the template belowa and wait for CREATE_COMPLETE.

Template is creating reasources such as: VPC, EC2, IAM Roles, S3 Bucket.

<a href="https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/create/review?templateURL=https://learn-cantrill-labs.s3.amazonaws.com/aws-pet-rekognition-ecr/APPCFN.yaml&amp;stackName=PETREKOGNITIONECR" rel="nofollow">PETREKOGNITIONECR</a>

![image](https://user-images.githubusercontent.com/96197101/216157791-998db420-6aa3-4b18-a498-75a3beb1ce5a.png)

![image](https://user-images.githubusercontent.com/96197101/216163907-99b62884-6494-4c24-8e50-8209f0b59462.png)

## STAGE 1

In this part:
  - Creating a Rekognition model that will be used to detect cats and dogs in images
  - Training the model with a set of images that contain cats and dogs

1. Go to Rekognition console and click Use Custom Labels in the left-hand menu and then click Get started.

![image](https://user-images.githubusercontent.com/96197101/216169652-e6243808-ba33-4454-bb88-728da9b27ce6.png)

![image](https://user-images.githubusercontent.com/96197101/216170881-299fb11a-50e2-4876-9615-d4bbed7a3b42.png)

2. If no a Rekognition Custom Labels project has been created before a pop-up window will appear. This windows will ask to create an S3 bucket to store all the data related to the model.

![image](https://user-images.githubusercontent.com/96197101/216171363-396b161b-bcaa-4288-a868-0a30bfbd2ea7.png)

3. In the left-hand click Projects and create a project.

![image](https://user-images.githubusercontent.com/96197101/216171885-21715981-44e0-4e97-b604-9a3a8b426464.png)

![image](https://user-images.githubusercontent.com/96197101/216172188-3976f58f-1464-47fe-81ce-eb9324e2dac6.png)

![image](https://user-images.githubusercontent.com/96197101/216172275-6bb0702f-7c4a-4c32-9489-fec0a8b76344.png)

4. Clik on the "Create dataset" and select the following options:
  - Configuration options: Start with a single dataset
  - Training dataset details: Upload images from your computer
  - Click Create Dataset

![image](https://user-images.githubusercontent.com/96197101/216172392-250d07e5-1397-438e-8053-80c695a83862.png)

![image](https://user-images.githubusercontent.com/96197101/216172788-e87ff471-0762-432a-ad77-522add6b8319.png)

5. Upload the images to a dataset from the computer

Upload the images of cats and label them.

 ![image](https://user-images.githubusercontent.com/96197101/216173622-b7b8f180-ef73-4148-a3a3-f040e36a8efe.png)

 ![image](https://user-images.githubusercontent.com/96197101/216173732-8896d2da-7aba-4c76-a461-1a6b1687b4b3.png)

 ![image](https://user-images.githubusercontent.com/96197101/216173884-08a33665-4ad0-42ae-a557-4ca9079883dd.png)

 ![image](https://user-images.githubusercontent.com/96197101/216174637-7da760c6-dfcb-4ef3-a3ac-38b3ac7904e8.png)

 Select the images of cats and click Assign image-level labels
 
![image](https://user-images.githubusercontent.com/96197101/216176410-757ab73b-1bf1-479a-a0fb-afa9bd851db0.png)

![image](https://user-images.githubusercontent.com/96197101/216176502-e4366a83-d729-4381-9c76-ec311a46217e.png)

 ![image](https://user-images.githubusercontent.com/96197101/216174768-fbf64f8e-c4a6-4ca6-9da2-77e6d6e876db.png)

 ![image](https://user-images.githubusercontent.com/96197101/216175164-79c1d3e1-5b59-4c2e-ba99-eabbe91e8c6f.png)

Do the same with dogs.

When all of images are labeled click Train model

![image](https://user-images.githubusercontent.com/96197101/216248023-b5f6fd45-510f-4c46-9e01-6d92dc5614d3.png)

![image](https://user-images.githubusercontent.com/96197101/216248081-1db49690-f167-4631-8dc8-acc67f2eb346.png)

![image](https://user-images.githubusercontent.com/96197101/216248139-b6e1620d-80ac-40a9-bc13-0aa3659c5690.png)

![image](https://user-images.githubusercontent.com/96197101/216248216-46ae4ad5-f35f-42f1-96bd-5c8c0ca90761.png)




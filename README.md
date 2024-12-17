# Wine-Quality-Prediction-with-EC2-instance-and-MLFlow
End to End Machine Learning project that predicts wine quality. The project will be deployed on a EC2 instance and register models with MLFlow

You can check the tutorial [here](https://www.youtube.com/watch?v=pxk1Fr33-L4&list=PL-aNIpQL193HrbakiKsbNONogrIw9xnhO&index=21&ab_channel=KrishNaik)
![mflow](https://github.com/user-attachments/assets/e121fc98-04a6-4b49-837f-f5d6d8e08804)

### Built With
[![My Skills](https://skillicons.dev/icons?i=aws,githubactions,vscode,flask,docker)](https://skillicons.dev)


### The concepts learned
- [x] The lifecycle of an End-to-End MLOps project. Key concepts include Modularization, Error, and Artifact logging
- [x] Logging ML experiments with ML flow and DagsHub ( A GitHub alternative suited for data-related projects)
- [x] Configuring GitHub Actions to workflow and connecting it to an AWS EC2 instance
- [x] Configuring an AWS ECR for docker images
- [x] Configuring network rules to allow access to your application
- [x] Deploying a flask application

### Future improvements
- [ ] Adding a terraform module to deploy the AWS resources
- [ ] Working on the networking re-routing across different website redirects

# How to run?
### STEPS:

Clone the repository

```bash
https://github.com/Jnyambok/Wine-Quality-Prediction-with-EC2-instance-and-MLFlow
```
### STEP 01- Create a conda environment after opening the repository

```bash
conda create -n mlproj python=3.8 -y
```

```bash
conda activate mlproj
```


### STEP 02- install the requirements
```bash
pip install -r requirements.txt
```

```bash
python app.py
```


# AWS-CICD-Deployment-with-Github-Actions

## 1. Login to AWS console.

## 2. Create IAM user for deployment

	#with specific access

	1. EC2 access : It is virtual machine

	2. ECR: Elastic Container registry to save your docker image in aws


	#Description: About the deployment

	1. Build docker image of the source code

	2. Push your docker image to ECR

	3. Launch Your EC2 

	4. Pull Your image from ECR in EC2

	5. Lauch your docker image in EC2

	#Policy:

	1. AmazonEC2ContainerRegistryFullAccess

	2. AmazonEC2FullAccess

	
## 3. Create ECR repo to store/save docker image
    - Save the URI: xxxxx

	
## 4. Create EC2 machine (Ubuntu) 

## 5. Open EC2 and Install docker in EC2 Machine:
	
	
	#optinal

	sudo apt-get update -y

	sudo apt-get upgrade
	
	#required

	curl -fsSL https://get.docker.com -o get-docker.sh

	sudo sh get-docker.sh

	sudo usermod -aG docker ubuntu

	newgrp docker
	
# 6. Configure EC2 as self-hosted runner:
    setting>actions>runner>new self hosted runner> choose os> then run command one by one


# 7. Setup github secrets:

    AWS_ACCESS_KEY_ID=

    AWS_SECRET_ACCESS_KEY=

    AWS_REGION = us-east-1

    AWS_ECR_LOGIN_URI = 

    ECR_REPOSITORY_NAME =


For every component, these are the steps we took:
## Workflows
1. Update the config.yaml
2. Update the schema.yaml
3. Update the params.yaml
4. -Update the entity
5. -Update the configuration manager in src config
6. -Update the components
7. Update the pipeline
8. Update the main.py
9. Update the app.py

After working on the research/..pynb
1. Update the entity [entity/config.config_entity] - this is where your data class refers to. It is a yaml file that contains the pre-configurations that include the directories specifically

2. Update the configurations - DataTransformationConfig class.Creates a new instance of the class using the configuration data loaded from the YAML file.
>>Retrieves Data Transformation Configuration:

The config variable is assigned the data_transformation section of the overall configuration. This section likely contains specific settings related to data transformation, such as the root directory and data path.
Creates Directory:

>>The create_directories function is called to create the root_dir specified in the configuration. This directory will be used to store intermediate data files or transformed data.
Creates DataTransformationConfig Object:

>>A new instance of the DataTransformationConfig class is created.
The root_dir and data_path attributes of the new instance are assigned the corresponding values from the config object.
Returns Configuration Object:

>>sThe newly created data_transformation_config object is returned. This object can be used elsewhere in the code to access the root_dir and data_path for data transformation tasks.

3. Make a new file in the Component folder. This folder reserves the individual machine learning components that are modularized for reusabiity, scalability.


4. Make a new file in the Pipeline Folder.This folder joins the module into the pipeline ensuring one stage is 'validated' from the last


5. Finally, register the pipeline stage in the main.py

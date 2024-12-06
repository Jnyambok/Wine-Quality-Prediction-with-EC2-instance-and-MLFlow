# Wine-Quality-Prediction-with-EC2-instance-and-MLFlow
End to End Machine Learning project that predicts wine quality. The project will be deployed on a EC2 instance and register models with MLFlow

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
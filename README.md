# Udacity-Developing-Your-First-ML-Workflow

## Deploy and monitor a machine learning workflow for Image Classification

### Dataset Prep 

![S3_Train_Data.png](images/S3_Train_Data.png)

![S3_Test_Data.png](images/S3_Test_Data.png)

### Training Job 

![Training_Job.png](images/Training_Job.png)

### Endpoint Deployment

![Img_Classification_Endpoint.png](images/Img_Classification_Endpoint.png)

### 3 Lambdas for to take s3 image object key, serialise the s3 image object, get inference result and filter lower threshold results

```Codes in lambda.py```

1 - serializeImageData - Added permission for S3 Full Access to read S3 image objects
2 - inferSerializedImageData - Added permission for Sagemaker Full Access to invoke sagermaker endpoint
3 - filterResults - No extra permissions required

### Step Function Graph

![stepfunctions_graph.png](images/stepfunctions_graph.png)

```State Machine config in MLWorkflowStateMachine.json```

### State Machine Execution - Success

![MLWorkflowStateMachine_Success.png](images/MLWorkflowStateMachine_Success.png)

### State Machine Execution - Failure (Exception for lower threshold)

![MLWorkflowStateMachine_Failure.png](images/MLWorkflowStateMachine_Failure.png)

### Data Capture for Multiple Inferences

![Captured_Data.png](images/Captured_Data.png)

### Visualisation Plot

![Visualization.png](images/Visualization.png)

## License

[License](LICENSE.txt)

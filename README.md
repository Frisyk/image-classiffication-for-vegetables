
---

# **Project: Image Classification for Vegetables**  

## **Dataset**  
[Vegetable Identification Dataset](https://www.kaggle.com/datasets/jocelyndumlao/a-dataset-for-vegetable-identification)  

**Credits:**  
This dataset is provided by [jocelyndumlao](https://www.kaggle.com/jocelyndumlao) on Kaggle. Full credit goes to the original creator.  

## **Running Inference**  

To serve the model using TensorFlow Serving with Docker, follow these steps:  

1. Run the following command to start a container and mount the model directory:  
   ```bash
   docker run -it --rm \
     -v C:\Frisnadi\ML\image-classification-vegs\saved_model\models:/models \
     -p 8501:8501 \
     --entrypoint /bin/bash tensorflow/serving
   ```

2. Inside the container, start TensorFlow Model Server:  
   ```bash
   tensorflow_model_server --rest_api_port=8501 \
     --model_name=rps_model \
     --model_base_path=/models/rps_model/
   ```

3. Once the server is running, access the model’s REST API at:  
   ```
   http://localhost:8501/v1/models/rps_model
   ```

   
---

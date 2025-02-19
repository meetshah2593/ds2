# Welcome to DS2!

---

Hello 👋 Introduce the entire process of customized AI development, the DS2.ai solution.

DS2.ai is the MLOps platform that serves all processes of building your customized AI from automatic annotation, model training and deployment.


 - Manual & Auto Annotation Tools (Tableur, Text, Image, Recommeder system)

 - ML & DL Training (Pytorch, Tensorflow, XGboost, etc)

 - AI Aalytics (Prescriptive analysis and Data analytics with Metabase)

 - AI Model Deployment and monitoring

 - Use Active learning process
 
 - API & Python SDK Support


![Supported Frameworks](https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FdklUDntQ1Pl0m3eHCvN4%2Fuploads%2F4cquinURNdHEAHZr1i98%2FScreenshot%20from%202022-08-16%2015-43-37.png?alt=media&token=6fa686f3-f62a-4ca3-8775-73f8047b2462)


---
### Install

Proceed with the installation as follows:

```bash

wget https://assetdslab.s3.ap-southeast-1.amazonaws.com/ds2_install.sh
. ds2_install.sh 

```

[Extended documentation for DS2](https://docs.ds2.ai/)


### Start labeling data

Supports training data labeling tools needed to create artificial intelligence models. 
After clicking Labeling on the top menu, upload the dataset, and you can start labeling by selecting the desired function between manual labeling and auto-labeling tool.
[![Watch the video](https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FdklUDntQ1Pl0m3eHCvN4%2Fuploads%2FQVuhYB5hjxlHse63uM4v%2Fautolabeling_en.gif?alt=media&token=e368e1b1-d43f-4d04-929a-51246a5993d3)


### Training AI models

After labeling is complete, artificial intelligence can be developed using the learning data. Click the “Start AI Development” button on the dataset or labeling project screen to enter the setting screen for AI development. 
On the setting screen, three types of development environments are supported.
- Manual setting: Select the desired deep learning & machine learning library (Pytorch, Tensorflow, XGboost, etc.)
- Fast learning speed (AutoML): A function that creates a model by speeding up the learning rate among AutoML learning techniques
- High Accuracy (AutoML): A function that creates a model with high accuracy among AutoML learning techniques

After selecting the desired learning method, click the Start button on the right to start learning. If you click the "Model" tab at the bottom after starting, you can check the progress of the model being developed. It provides the function of "distribute" and the function of "analyzing" through the data set of the prediction result created by the model.

* Setting Training Options
![](https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FdklUDntQ1Pl0m3eHCvN4%2Fuploads%2FiTSJJ0Y7N8evuJlhSG4s%2FScreenshot%20from%202022-08-16%2016-55-26.png?alt=media&token=9858bd59-f47f-4c67-8cbc-ae6683e4c452)

* Confusion Matrix
![Confusion Matrix](https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FdklUDntQ1Pl0m3eHCvN4%2Fuploads%2FyLLLjg3AYBEkEfo7bRAI%2Fconfusion_matrix.png?alt=media&token=3cc0160b-bc35-4bdf-afa5-80bbf890df79)

* Feature Importance
![Feature Importance](https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FdklUDntQ1Pl0m3eHCvN4%2Fuploads%2FOi0m7F87Hvk4fz4sSNoI%2Ffeature_importance(1).png?alt=media&token=a8418d6c-1f51-46f6-b70c-e1e5eb25e940)


### Deploy AI models

You can use the Deploy Model function by completing training through DS2.ai or uploading a model you have already created to DS2.ai. (The ability to upload models directly supports Pytorch and Tensorflow2 models.)

You can upload by clicking the "Deploy" menu button at the top or distribute the developed model through the "Deploy" function in the "Learning" menu.
The deployed model can be managed through a separate endpoint, and the number of API calls can be monitored.

![](https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FdklUDntQ1Pl0m3eHCvN4%2Fuploads%2Fv8JfkiCs4YTajVEM7AvG%2Fdeploy.png?alt=media&token=437a4dda-5c58-40a6-8473-34e6e24c1e39)

After the model is deployed, the input and output values used for prediction are automatically stored in the dataset, helping to quickly and easily create AI with higher accuracy through active learning.

![](https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FdklUDntQ1Pl0m3eHCvN4%2Fuploads%2FxLiSO1F6CFFId6rjd6Hg%2FScreenshot%20from%202022-08-14%2011-28-30.png?alt=media&token=59d7eb64-36a5-42f2-8968-a4238a66225d)


### Use Python SDK 

One of the powerful features of DS2.ai is the manual setting function that can easily set up learning under various conditions to derive an optimal artificial intelligence model.
```bash
pip install ds2ai
```
After completing the installation of the ds2ai Python library, you can start learning using the example below.

```python
import ds2ai
ds2 = ds2ai.DS2("your-app-code")

project = ds2.train(
    "BankMarketing.csv",
    option="custom",
    training_method="normal",
    value_for_predict="is_charge",
    algorithm="keras_ann",
    hyper_params={
      "layer_width": [20,3,5],
      "layer_deep": [3],
      "epochs": [10],
      "loss_function": ["mean_squared_error"],
      "optimizer": [
        {
          "clipvalue": 0.5,
          "learning_rate": 0.001,
          "beta_1": 0.9,
          "beta_2": 0.9999,
          "epsilon": None,
          "decay": 0,
          "amsgrad": False,
          "function_name": "Adam"
        }
      ],
      "activation": ["relu"],
      "batch_size": [32],
      "output_activation": ["relu"]
    }
)
```

You can check the app code by clicking the user name in the upper right corner. You can start learning with the code above after putting this app code as shown below.
```python
ds2 = ds2ai.DS2("Your App code")
```
After the code is executed, the ability to predict or deploy the job situation and the trained model is available in ds2.ai as-is. For more information on how to use, refer to "SDK | PYTHON" in the left menu.

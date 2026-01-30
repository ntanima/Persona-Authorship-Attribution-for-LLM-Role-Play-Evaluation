# Qwen: Generation and Classification Experiments

## Computing Environment
Due to resource constraints, these experiments were conducted on the **Kaggle** platform using **T4 GPUs**. The code was last verified and run on January 15th.

## Data Availability
The cleaned dataset used for both training and testing is available here:  
[New Roles Dataset](https://kaggle.com/datasets/f4e93784dc77822e90b882e26cadc12edaf213748b4cfdfa208677102261caa5)

## Results
Detailed confusion matrices and various performance metrics are generated within the output of each individual notebook.

## Reproducibility Guide
To reproduce these experiments on Kaggle, follow these steps:

1.  **Setup** Upload the code notebooks to Kaggle.

2.  **Training** Add the dataset folder to the Kaggle **Input** directory.
    * Enable **T4 GPU** acceleration in the notebook settings.
    * **Note:** Execute the training notebooks for each folder first before attempting to run tests.
    * In case you don't want to train. The trained model is also provided as a zipfile in each folder.

3.  **Testing** Add the original dataset folder to the **Input** directory.
    * Add the output from the training step to the **Input** directory.
    * Run the test notebooks.

## Methodology

### 1. Classification (Multiple Choice)
The model is given a prompt including a specific list of potential authors. It is instructed to select the correct author strictly from the provided options. This is evaluated in two modes:

* **All Options:** The model must choose from the full list of 95 authors present in the training set.
* **Local Options:** The model must choose from a restricted subset of authors relevant to the specific test case.

### 2. Generation (Open-Ended Identification)
The model is given a prompt and asked to identify the author directly. Unlike the classification task, **no list of options is provided**. The model must generate the correct author's name via open-ended generation based on its training.

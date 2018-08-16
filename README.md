# Machine Learning Model Monitoring (MLMM)
---
## Why MMLM? 

MMLM is proposed and being developed due to various reasons:
- ML model development usually involves iterations, and it is non-trivial to keep track of the optimal parameters and model architectures.
- Training ML models is costly. Early termination of unnecessary training may lead to significant cost saving.
- Monitoring the training process is not efficient since practitioners could not spend all their time to watch out the training.
- The model may break and stop due to exceptions, such as overflow, leading to the loss of all training progresses.

## Blueprint of MMLM

To improve the training efficiency, I am working on developing a Python framework for effectively monitoring the ML model training process.

In a nutshell, MLMM should start with predefined configurations. There are three key elements:

- Parameters: a set of parameters to execute
- Inputs to your models
- Outputs from your models
- Evaluation metrics

Let us assume you are building a new KNN algorithm with 3 variations. You would like to compare their ROC on 4 datasets with 10 different K values ranging from 10-100.

First, you should encapsulate your KNN models as K1, K2 and K3 and specify the input APIs K1(X,y,k), etc. Then you should define the returns from your models like R_K1() and the evaluation metric ROC. MMLM is like glue to execute the evaluation with different settings, and save the results for debugging.

## MMLM's Value Proposition

I know there a few similar tools, such as gridsearch in Sklearn, and let me explain why MMLM could be different.

MMLM would be featured with a few key functionalities:
- **Flexibility to work with any models**, as long as the required elements are supplied, e.g., inputs and outputs.
- **Real-time monitoring by sending emails for status updates**, even you are away
- **Continuously save model performance logs** for debugging purpose.
- **Restart training from where the model breaks**, which is similar to resume a file downloading, which could decrease the loss due to an exception.
- **Preset triggers to stop training**. For instance, 10 iterations of  accuracy decrease could be defined to terminate the training process.

In the ideal case, MLMM could be used as a break-point tool to monitor the training in real time.

## Development Plan

As of Aug 16 2018, MLMM is still under active development and will be released gradually from simple functionalities to advanced ones.

**You are welcome to star/follow the project to see the progress**.

Happy ML!
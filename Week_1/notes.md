# Week 1 Study Notes 

## What is MLops

MLops is a set of best practices to deploy a ML model to production by managing the entire life-cycle flow efficiently, the main goal of MLOps is to ensure that ML models are developed, tested, integrated and deployed in a standardized, automated and reliable way. A MLOps workflow can be categorized in a maturity model, that helps clarify the objectives of said workflow, there are 5 levels of maturity for a workflow:

### Level 0 - No MLOps
The level 0 represents a workflow that doesn't contain any MLOps practice to deploy a model at all, it can be a simple Jupyter Notebook model, for example. In this level there is no automated training, testing, deploy, or tracking, in other words, there is no pipeline to help manage the model.

### Level 1 - DevOps but no MLOps
In this level, there is already some kind of model managing but it is not about the specifics of a ML model testing, but rather general like automation, where releases are automated, CI/CD, unit test, configuration test, etc, which are not ML aware.

### Level 2 - Automated Training
In this level, there is already a training environment that is fully managed and traceable, making the model easy to reproduce, train and have a low friction to release it. 

### Level 3 - Automated Model Deployment

In this level, the pipeline can gather data automatically, the results are tracked and versioned controled, the release is automatic and managed by CI/CD, the scoring script have tests and is version controled, but it still needs humans to implement a model and to check production result for new model development .

### Level 4 - Full MLOps automated Retraining
In the last maturity model level, the MLOps pipeline is able to use data from the production metrics to retrain itself, running the entire pipeline again and releasing a new version based on the metrics of the production, which will have a better score, reliability, etc. In this level, the human intervention is very low, so it need to be well developed and have a good trust of the possible outcomes, making it the highest maturity level.
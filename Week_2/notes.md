# Week 2 Study Notes 

## What is experiment tracking?
Experiment tracking is the process of keeping track of all the relevant experiment information from an ML experiment, that includes, for example:
- Source code;
- Environment;
- Data;
- Model;
- Hyperparameters;
- Metrics;
- etc.

The information will change depending on experiment you are doing, the informations that you consider relevant to track, etc.

Experiment tracking is important by a number of factors, which include; **Reproducibility**, **Organization** and **Optimization**, which would be much harder if there is no tracking of any experiment at all.

There are several ways to keep track of an experiment, you can use a Excel spreadsheet and manually insert data for each experiment, but it opens a door for human errors, if you don't have a standard format it will be messy, and it is hard to visualize and colaborate with other people. `MLflow` comes as a solution for this kind of problem.

## MLflow

MLflow is an open source platform for the machine learning lifecycle, it is a Python package, which contains four main modules: 

- Tracking;
- Models;
- Model Registry;
- Projects.

### Tracking

The MLflow Tracking module allows the organization of the experiments into runs, keeping track of:
- Paramenters;
- Metrics;
- Metadata;
- Artifacts;
- Models.

It will also log automatically extra information, which are:

- Source code;
- Version of the code (git commit);
- Start and end time;
- Author.

### Models
([source](https://MLflow.org/docs/latest/model))
An MLflow Model is a standardized format for packaging an ML model. It stores a model in different "flavors" that can be used by different tools.

### Projects 

The mlflow Project module is basically a way to organize data science projects in a way that other data scientists (or automated tools) can run it, it will have the `name of the project`, `Entry points` (commands that can be run within the project), and `environment`, that will be used to execute the project.

## Getting started with MLflow

To run the MLflow ui, we need to also set-up the database to store information, otherwise it will raise an error:

```Bash
mlflow ui --backend-store-uri sqlite:///mlflow.db
```
There are several backend options, but for this example sqlite is used. Now, it is possible to head to `http://127.0.0.1:5000` and see the UI.

Now we open a jupyter notebook `in the project folder`, if you try to run the following command in a subfolder, the experiment will not show:

```Python
import mlflow
mlflow.set_tracking_uri("http://127.0.0.1:5000/")
mlflow.set_experiment("zoomcamp_experiment")
```
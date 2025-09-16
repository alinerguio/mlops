# MLOps

Studies related to MLOps to be able to support innitiatives at B Lab and personal projects 

- [MLOps Zoomcamp](https://github.com/DataTalksClub/mlops-zoomcamp)

# MLOps steps 

## Introduction 

Main steps for MLOps are:

Design -> Train -> Operate

API is the way to deploy. App is connected to this API - deployment.

MLOPs is a set of practices to integrate the model, make sure it can be retrained and to monitor its quality. 

## Configure 

GitHub Codespaces 
- Create repo
- Click "Code" (same place where you find the link for cloning) and click Create Codespaces on Main 
- Open VSCode locally, install extension 


## MLOps maturity scale

0. No MLOps - no tracking, no automation, just experimenting with ML with a jupyter notebook. Good level for POCs, but once you pass this level you should have more maturity. Prove that the model is good first before putting more effort in it. 

1. DevOps, no MLOps - deploying a model, having engineering practices but not ML practices. Releases automated, unit testing, CI/CD, Ops Metrics. No experiment tracking, no reproducibility, data science separated from engineers. First time putting a model in production. 

2. Automated training - training pipeline, you don't need to manually retrain model. Experiment tracking, model registry (versioning models to know which is in production). Low friction deployment with data scientists working with engineering. Usually interesting to apply once you have more than one model in production. 

3. Automated deployment - easy to deploy model. A/B testing - testing versions. Model monitoring. Usually interesting if 4-6 models in production, or one super important model in production.  

4. Full MLOps automation - if this model fails, it automatically retrains itself and create a new version of the model without human interaction. Fully automated, fault prevention and carefully monitored. In time, companies that take machine learning seriously arrive to this level of maturity. 

## Experiment tracking
Concepts:
- ML experiment: the process of building an ML model
- Experiment run: each trial in an ML experiment
- Run artifact: any file that is associated with an ML run
- Experiment data

Experiment tracking is the process of keeping track of all relevant information from an ML experiment. Including:
- Source code
- Environment
- Data
- Model
- Hyperparameters 
- Metrics

Reasons to do that:
- Reproducibility
- Organization
- Optimization

### MLFlow

An open source platform for the machine learning lifecycle. 
- Tracking
- Models
- Model Registry
- Projects

```sh
pip install mlflow 
```

You can also have collaborative environment in a server.

Allows to keep track of every run with needed data.

```sh
mlflow ui --backend-store-uri sqlite:///mlflow.db --default-artifact-root ./artifacts 
```

This way, data will be stored in this file about the runs. For your Jupyter Notebooks, you need to setup one cell:

```python
import mlflow

mlflow.set_tracking_uri("sqlite:///mlflow.db")
mlflow.set_experiment("nyc-taxi-experiment")
```


## Model management
Versioning and model lineage.

By adding the log_model in your code, you'll be able to store the model to use again later. MLFlow shows it in its interface and you can re-use it.

```python
mlflow.xgboost.log_model(booster)
```

By adding the **--default-artifact-root ./artifacts ** param, you be able to set the artifact root that will be used when storing models as artifacts.
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
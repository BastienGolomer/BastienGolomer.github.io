---
layout: post
title:  "A dive into MLOps!"
date:   2023-10-13 14:16:55 +0200
---
This blog post sums up concepts and ressources I came across in my journey to learn MLOps. Feel free to check everything out for more in depth content, as this post will only contain my personal notes on core concepts and definitions (even the advanced ones).

**Note**: This blog post is on-going and could contain some mistakes! It is a markdown file of notes.


# Ressources

Here are free ressources I used to learn MLOps
- [Microsoft's guide to MLOps on Github](https://github.com/microsoft/MLOps)
- [Made with ML (platform)](https://madewithml.com/)
- [Machine Learning Engineering for Production (MLOps) Specialization](https://www.youtube.com/watch?v=NgWujOrCZFo&list=PLVd1sFtZgLA7gPFPB8nPVEgOG1a5BkmSR)


## Andrew Ng's Specialization 

### The steps from data to production 
1. Scoping = define project
2. Data Handling
   1. define data and establish baseline
   2. label and organize the data
3. Modelling 
   1. select and train model
   2. perform error analysis
4. Deployment
   1. deploy in production 
   2. monitor & maintain system

Tools for each of these steps (suppose you work with Python or Julia)

1. team meetings, paper review, discussion with client and product managers to define goals (no particular tool)
2. Multiple options :
   - Do we build a Database (relational, vector, document...)? 
   - Is there some data processing, augmentation, imputation, to do? 
     - Images : with python you can use
       - Pillow/PIL(Python Imaging Library)
       - OpenCV
       - Scikit-Image
       - SciPy
     - Signals
       - SciPy
       - PyAudioAnalysis
       - DSP.jl or SignalProcessing.jl (Julia language)
     - Tables
       - Pandas
       - NumPy
       - DataFrames.jl
     - General processing (splits, pipelines)
       - Scikit-Learn
       - Flux
   - Some Data Analysis? etc...
3. Use your favourite framework
   1. DL framework 
      - Tensorflow/Keras
      - PyTorch
      - mxnet 
      - Flux
   2. Use some frameworks for experiment tracking 
      1. Comet
      2. MLFlow
4. Several options again
   1. Docker
   2. Azure, AWS, Google Cloud






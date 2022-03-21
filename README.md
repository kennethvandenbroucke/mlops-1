# Introduction
Welcome to today's introductive course to MLOps (in the cloud).  
We only have a few hours together, so we'll be focussing on a couple of main topics, which are:

1. Restructuring/Refactoring your machine learning code to follow good devops practices
2. Creating an automated pipeline to train your model when new data comes in using Github Actions
3. Writing some simple but effective unit tests using Github Actions while learning about Docker
4. Tracking your models with MLFlow

# Restructure/Refactor your Machine Learning notebooks 
## Theory
All too often I encounter Data Scientists who write all of their data exploration, model training, and model inference code in a single Jupyter Notebook.
Even though this could be a good place to start to get a feel of the datasets, this can in no way be considered production ready code that can be used in an actual project.
Take a look at the *titanic.ipynb* notebook in this repository. What's wrong with this code?

You could argue that writing your code in this way:
1. **Reduces reusability**: What if we only want to test a different model and our input data hasn't changed. Does it then make sense to have to rerun your all of your exploration and preprocessing steps? Also, notebooks make it very difficult to write clear helper functions that will be used throughout the project.
2. **Reduces readability**: This notebook is still extremely simple but already reduces readability of our code. What if I'm only interested in reading the code on how the model is trained? Do I need to dig through an entire notebook to find that piece of code?
3. **Reduces maintainability**: Writing everything in a single file makes it difficult to write clear and concise unit tests which would help maintain the quality of our code.

These are all issues that ultimately will make it much more difficult to share your code with another data scientist who might be working on the same project (or maybe yourself in the future). If another data scientist can't run the code without worrying that he/she might break things, then it's not good code.

## Exercises

Go through the *titanic.ipynb* notebook, try to understand it, and think about how you could restructure this code. 
Clone this repository to your local machine and ensure that you can run the code.
If you forgot (or don't know) how to clone a repository, you can follow the instructions below.

```bash
# First, open a terminal and create a new folder where your repository should reside on your local machine
# Then, go into this new folder and clone the repository
mkdir new_folder
cd new_folder
git clone https://github.com/LukasMahieuArinti/mlops-1.git
```

Extra:
In this repositoy there is an environment.yml file. You can use this to create a Conda environment to ensure that you're using the correct packages to be able to run the code, and nothing more.

If you already have conda installed, you can run the following command to create a virtual environment with the correct packages.
```bash
conda env create -f environment.yml
```
It's not mandatory to install conda to be able to follow today's course. However, if you're interested, you can find more information here:
https://docs.conda.io/projects/conda/en/latest/user-guide/install/index.html?msclkid=20aed13fa7ca11ec9b24cc3005ca84d0

## Next up

If you're done, you can see an example of how I restructured this repository in the next repository: https://github.com/LukasMahieuArinti/mlops-2. 
We will continue our session there.

# Kickstarter machine learning project

This is our second project within the Data Science workshop of neuefische. As a group of three we chose a topic for which we were given a data set that we were supposed to clean, explore and ultimately use to train different machine learning algorithms. The hereby generated models were evaluated and the best one was used for an error analysis.

Our project was to develope a model that predicts the outcome of a Kickstarter campaign based on a large data set of previously ran campaigns. Kickstarter is a fundraiser website/application were anyone can present a project that they want to realise. If people like the project, they can back it, which means that they promise to pay a certain amount of money in case the project is successful. Each project has a certain goal of funding money that they want to reach in a set period of time. If at least that money is funded by backers, the project is successful. Only now the backers will pledge their money and receive the product when it is done.

We had three days, before we had to present our work to our cohort. During this time we organized ourselves with help of the `GitHub Kanban board`. Our basic schedule like this:

|Deadline|Topic|Subtopics|
|---|---|---|
|time|Come up with a baseline model|Access data, clean data, EDA, baseline model|
|time|Presentation draft|Decide for storytelling, have first graphs ready (introduction, EDA, modelling)|
|time|Decide for a model|Train different ML algorithms, optimise as much as possible, compare evaluations|
|time|Be ready to present|Error analysis on best model, polish presentation, practice presentation|

In this repository you will find the following files of relevance:
- `eda.ipynb`: Here we did the data cleaning and EDA of the data frame that we obtained via SQL from a webserver elsewhere
- `How to optimize my model.ipynb`: Our gathered ideas how each one of us should try to optimize the model that we were working on
- `final_presentation.pdf/key`: The final presentation that we gave for our cohort
- folder `ML models`: contains the individual ipynb files were we trained and optimized different ML algorithms. The best model was XGBoost

Since we were a group of three, we divided the workload, which means that each one of us had their own models that they worked on. The contributions were as following:

|Model|Contributors|
|---|---|
|Baseline model (logistic regression)|Dipali and Dominik (me)|
|KNN|Dominik (me)|
|random forest (RF)|Dipali|
|AdaBoost|Leander|
|XGBoost|Leander and Dominik (me)|

## Strategies to optimize our models

Since we worked as a group of three people on this project and we decided that each one of us would establish and optimize a different modeling algorithm we decided for the following guidelines when it comes to optimize the model:

- feature engineer (standardisation, normalisation, not on one-hot-encoded columns)
- cross validation
- gridsearch or randomsearch
- if overfitting: regularisation (Ridge Regression or Lasso Regression)

Furthermore, we decided to optimize for precision, because when we make a prediction on whether a new Kickstarter Project might be a success or not, we do not want false positives.

## Important files/folders in this repository

The first important file is the __eda.ipynb__. Here you will find all the EDA as well as the data cleaning that we did on the Kickstarter dataset that we received via SQL from postgres elsewhere. If you run the whole notebook from start to end, you will obtain the processed csv files that we used for our modelling notebooks.

Next, you may want to look into the folder __ML models__. Here, you find the notebooks, where we ran our modeling and their respective optimisation. Since, I mainly worked on the __XGBoost__, this is the file that I myself properly commented for display. This is also our best model that we chose for our presentation in the end.

In the folder __presentation__ you will find the PDF or keynote file of our final project presentation.

## Set up your Environment

### **`macOS`** type the following commands : 

- For installing the virtual environment you can either use the [Makefile](Makefile) and run `make setup` or install it manually with the following commands:

     ```BASH
    make setup
    ```
    After that active your environment by following commands:
    ```BASH
    source .venv/bin/activate
    ```
Or ....
- Install the virtual environment and the required packages by following commands:

    ```BASH
    pyenv local 3.11.3
    python -m venv .venv
    source .venv/bin/activate
    pip install --upgrade pip
    pip install -r requirements.txt
    ```
    
### **`WindowsOS`** type the following commands :

- Install the virtual environment and the required packages by following commands.

   For `PowerShell` CLI :

    ```PowerShell
    pyenv local 3.11.3
    python -m venv .venv
    .venv\Scripts\Activate.ps1
    pip install --upgrade pip
    pip install -r requirements.txt
    ```

    For `Git-bash` CLI :
  
    ```BASH
    pyenv local 3.11.3
    python -m venv .venv
    source .venv/Scripts/activate
    pip install --upgrade pip
    pip install -r requirements.txt
    ```

    **`Note:`**
    If you encounter an error when trying to run `pip install --upgrade pip`, try using the following command:
    ```Bash
    python.exe -m pip install --upgrade pip
    ```

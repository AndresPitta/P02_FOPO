# FOPO project

This document contains the requirements and instructions to be able to run the FOPO python script in Power BI. For this you need:

- Power BI Desktop Version: 2.87.923.0 64-bit (November 2020)
- Python 3.7.6 or higher
- Conda 4.9.2 or higher (This is python's package manager)
- Java version 8 

To download Python & Conda please go [here](https://docs.conda.io/en/latest/miniconda.html). To download power BI, please go [here](https://powerbi.microsoft.com/en-us/downloads/). Finally, to download java please go [here](https://www.java.com/en/download/ie_manual.jsp)

We are also going to use the terminal to access to jupyter and python. To get to know how to open the Anaconda powershell by looking for it at the start menu.

After installation, restart the terminal. If the installation was successful, you will see (base) prepending to your prompt string. To confirm that conda is working, you can ask it which version was installed:

```
conda --version
```

which should return something like this:

```
conda 4.8.2
```

Next, type the following to ask for the version of Python:

```
python --version
```

which should return something like this:

```
Python 3.8.3
```

## Essential packages 

We are going to use `conda` to install Python packages from different online repositories (or 'channels'). There is a community-driven effort called the conda-forge, which provides more up to date packages. To add the conda-forge channel by typing the following in the terminal:
  
```
conda config --add channels conda-forge
```

Now, we can use the command `conda install <package-name>` to install the required packages. Let's run this code, line by line individually, to install the essential packages for the project:

```
conda install jupyterlab=2.* 
conda install numpy=1.* 
conda install pandas=1.* 
conda install flake8=3.* 
conda install black=19.* 
pip install spacy==2.2.3 
conda install tika=1.24
conda install re=2.2.1
```
We are also going to install spacy english model by running:

```
python -m spacy download en_core_web_sm
```

A little overview of the packages:

- Jupyter lab is an interface which is going to make the code easier to read. To learn more about Jupyter, please [go here](https://jupyter.org/)

- Numpy is a very useful numeric computing package. We are going to use it for array manipulation and numerical operations. To learn more please [go here](https://jupyter.org/)

- Pandas will help us manipulating dataframes. To learn more [go here](https://pandas.pydata.org/)

- Flake8

- Black

- Spacy is a powerful text analytics tool. We are going to use it to process the text. It has many more uses, to learn more [go here](https://spacy.io/)

- Apache Tika is a tool that will allow us to read the data from word documents. It also permits PDF documents, and many more. The documentation is [here](https://tika.apache.org/)

- Re is a regular expression package for text processing.

## Text analysis

This project contains 2 notebooks:

- The first one is called [data_importing.ipynb](https://github.com/AndresPitta/P02_FOPO/blob/master/src/data_importing.ipynb). This notebook contains the documented process of reading in the data from word files.

- The second one is called [similarities.ipynb](https://github.com/AndresPitta/P02_FOPO/blob/master/src/similarities.ipynb). This notebook contains the process of finding the similar topics in the interviews. Due to how heavy this process is, it is recommended to use cloud services to run this code. I recommend using [google colab](https://colab.research.google.com/notebooks/intro.ipynb#recent=true). However, this requires uploading a dataset to google drive.
# Introduction to Data Science in Python

This repository contains Jupyter notebooks, code samples, and all other materials used in the Intro to Data Science in Python course taught at the [2018 UT Summer Statistics Institute](https://stat.utexas.edu/training/ssi). Links to new sections or resources will be added below as content is added.

## Course overview/links
Inactive links will be added the evening before the following day's class at the latest.

* [Test notebook](https://github.com/tyarkoni/SSI2018/blob/master/notebooks/test.ipynb)
* [Day 1: Data Science in Python](https://github.com/tyarkoni/SSI2018/blob/master/notebooks/Day%201%20-%20Data%20science%20in%20Python.ipynb)
* [Day 2: Data Wrangling](https://github.com/tyarkoni/SSI2018/blob/master/notebooks/Day%202%20-%20Data%20wrangling.ipynb)
* Day 3: Visualizing and Analyzing Data
* Day 4: Predictive Modeling

## Setup (Instructions for Mac)
Install Homebrew: `/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`

Install pipenv: `brew install pipenv`

Set environment variable in `~/.bash_profile`
```bash
echo "#When pipenv makes a virtual environment, it will create it in the same directory as the project instead of ~/.local/share/virtualenv/" >> ~/.bash_profile
echo "PIPENV_VENV_IN_PROJECT=true" >> ~/.bash_profile
echo "export PIPENV_VENV_IN_PROJECT" >> ~/.bash_profile
```

Close terminal, then repoen

Clone this repository: `git clone https://github.com/timgianitsos/SSI2018.git`

Navigate inside the repository: `cd SSI2018`

Enter virtual environment: `pipenv shell`

Install dependencies: `pipenv install`

Run a notebook while in the pipenv shell: `jupyter notebook notebooks/test.ipynb`

## Testing your environment

If you want to make sure you have a working scientific Python environment prior to the first day of class (recommended), you can try running the [test notebook](https://github.com/tyarkoni/SSI2018/blob/master/notebooks/test.ipynb) in this repository. You should be able to view the rendered notebook in your browser even if you don't run it, but I recommend downloading and executing the Jupyter notebook to make sure everything works. If you're familiar with GitHub, you can clone the entire repository and navigate to the notebook. If you're not familiar with GitHub, the easiest way to execute the notebook is to load the [raw notebook code available here](https://raw.githubusercontent.com/tyarkoni/SSI2018/master/notebooks/test.ipynb) in your browser, then save the file to a convenient location (by clicking "Save As..." or the equivalent option in your browser). Now, from the command line, navigate to the directory containing the saved notebook, and run:

> jupyter notebook test.ipynb

(If you saved the notebook under a different name, substitute for test.ipynb accordingly.)

After a few seconds, you should see a local version of the notebook open up in your browser. You should now be able to execute the entire notebook by selecting the "Run all" option from the dropdown "Cell" menu. If you run into problems, they'll almost certainly arise in the first code cell containing all of the import statements. The likely culprit is that you've failed to install one or more of the required Python packages, in which case you can go back to the previous section and make sure you've installed Anaconda as well as the other packages mentioned above. If you run into issues (and you're registered in the SSI course!), feel free to [email me](mailto:tyarkoni@gmail.com) with questions. If you don't run into any problems, congratulations! You're all set for the course.

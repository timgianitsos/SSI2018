# Introduction to Data Science in Python

This repository contains Jupyter notebooks, code samples, and all other materials used in the Intro to Data Science in Python course taught at the [2018 UT Summer Statistics Institute](https://stat.utexas.edu/training/ssi). Links to new sections or resources will be added below as content is added.

## Course overview/links
Inactive links will be added the evening before the following day's class at the latest.

* [Test notebook](https://github.com/tyarkoni/SSI2018/blob/master/notebooks/test.ipynb)
* [Day 1: Data Science in Python](https://github.com/tyarkoni/SSI2018/blob/master/notebooks/Day%201%20-%20Data%20science%20in%20Python.ipynb)
* [Day 2: Data Wrangling](https://github.com/tyarkoni/SSI2018/blob/master/notebooks/Day%202%20-%20Data%20wrangling.ipynb)
* [Day 3: Visualizing and Analyzing Data](https://github.com/tyarkoni/SSI2018/blob/master/notebooks/Day%203%20-%20Exploring%20and%20analyzing%20data%20in%20Python.ipynb)
* [Day 4: Predictive Modeling](https://github.com/tyarkoni/SSI2018/blob/master/notebooks/Day%204%20-%20Machine%20learning%20in%20scikit-learn.ipynb)

## Setup (Instructions for Mac)
1. Navigate to the project directory. All commands *must* be run in the project directory.
	```bash
	cd <this project directory>
	```
1. This project requires a certain version of `Python`. The following command should output the version number.
	```bash
	grep 'python_version' Pipfile | cut -f 2 -d '"'
	```
	Determine whether this version is already installed. If you are using `bash` or `zsh`, you can verify this with the following command:
	```bash
	command -v "python`grep 'python_version' Pipfile | cut -f 2 -d '"'`" &> /dev/null; if [[ $? -eq 0 ]]; then echo "$_ currently installed"; else echo "$_ NOT installed"; fi
	```
	If the version of `Python` is not installed, you can install it here: https://www.python.org/downloads/.
1. Ensure `pipenv`<sup id="a1">[1](#f1)</sup> is already installed. If you are using `bash` or `zsh`, you can verify this with the following command:
	```bash
	command -v pipenv &> /dev/null; if [[ $? -eq 0 ]]; then echo "$_ currently installed"; else echo "$_ NOT installed"; fi
	```
	If `pipenv` is not installed, then install it with:
	```bash
	pip3 install pipenv
	```
1. The following command will generate a virtual environment called `.venv/` in the current directory<sup id="a2">[2](#f2)</sup> that will contain all<sup id="a3">[3](#f3)</sup> the `Python` dependencies for this project.
	```bash
	PIPENV_VENV_IN_PROJECT=true pipenv install --dev
	```
1. Activate the virtual environment.
	```bash
	pipenv shell
	```  
1. Run a notebook while in the pipenv shell.
	```bash
	jupyter notebook notebooks/test.ipynb
	```

Using `exit` will exit the virtual environment i.e. it restores the system-level `Python` configurations to your shell. Whenever you want to resume working on the project, run `pipenv shell` while in the project directory to activate the virtual environment again.

## Testing your environment

If you want to make sure you have a working scientific Python environment prior to the first day of class (recommended), you can try running the [test notebook](https://github.com/tyarkoni/SSI2018/blob/master/notebooks/test.ipynb) in this repository. You should be able to view the rendered notebook in your browser even if you don't run it, but I recommend downloading and executing the Jupyter notebook to make sure everything works. If you're familiar with GitHub, you can clone the entire repository and navigate to the notebook. If you're not familiar with GitHub, the easiest way to execute the notebook is to load the [raw notebook code available here](https://raw.githubusercontent.com/tyarkoni/SSI2018/master/notebooks/test.ipynb) in your browser, then save the file to a convenient location (by clicking "Save As..." or the equivalent option in your browser). Now, from the command line, navigate to the directory containing the saved notebook, and run:

> jupyter notebook test.ipynb

(If you saved the notebook under a different name, substitute for test.ipynb accordingly.)

After a few seconds, you should see a local version of the notebook open up in your browser. You should now be able to execute the entire notebook by selecting the "Run all" option from the dropdown "Cell" menu. If you run into problems, they'll almost certainly arise in the first code cell containing all of the import statements. The likely culprit is that you've failed to install one or more of the required Python packages, in which case you can go back to the previous section and make sure you've installed Anaconda as well as the other packages mentioned above. If you run into issues (and you're registered in the SSI course!), feel free to [email me](mailto:tyarkoni@gmail.com) with questions. If you don't run into any problems, congratulations! You're all set for the course.

## Footnotes

<b id="f1">1)</b> The `pipenv` tool manages project dependencies. It works by making a project-specific directory called a virtual environment that holds the dependencies for that project. After a virtual environment is "activated", `Python` commands will ignore the system-level `Python` version & dependencies. Only the version & dependencies in the virtual environment will be recognized. Also, newly installed dependencies will automatically go into the virtual environment instead of being placed among your system-level `Python` dependencies. This precludes the possiblity of different projects on the same system from having dependencies that conflict with one another. It also makes it easier to clean up after deleting a project: instead of remembering to uninstall several dependencies from your system, you can just delete the virtual environment.[↩](#a1)

<b id="f2">2)</b> Setting the `PIPENV_VENV_IN_PROJECT` variable to true will indicate to `pipenv` to make this virtual environment `.venv/` within the project directory so that all the files corresponding to a project can be in the same place. This is [not default behavior](https://github.com/pypa/pipenv/issues/1382) (e.g. on Mac, the environments will normally be placed in `~/.local/share/virtualenvs/` by default). Note that the virtual environment `.venv/` should never be moved because some of the scripts it runs use absolute paths. Therefore, if the project directory that it is inside is ever renamed or moved, the virtual environment will no longer work correctly. This can be remedied by deleting the `.venv/` and generating it again with `PIPENV_VENV_IN_PROJECT=true pipenv install --dev` [↩](#a2)

<b id="f3">3)</b> Using `--dev` ensures that even development dependencies will be installed (dev dependencies may include testing and linting frameworks which are not necessary for normal execution of the code). `Pipfile.lock` specifies the dependencies and exact versions (for both dev dependencies and regular dependencies) for the virtual environment. After installation, you can find all dependencies in `<path to virtual environment>/lib/python<python version>/site-packages/`. [↩](#a3)

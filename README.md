# pyEVA 

[![Generic badge](https://img.shields.io/badge/pyEVA-1.0-brightgreen)](https://github.com/HuanLab)
![Version badge](https://img.shields.io/badge/Python-3.7.12-orange)
![maintainer](https://img.shields.io/badge/Maintainer%20-Huan%20Lab-blue)

<br/> pyEVA is a Python-based program developed for mass-spectrometry-based research, meant to aid in fidelity checking of EIC plots from feature tables.
Initially written in C# and published by Guo et al. in 2021 as EVA[^1], to aid in ease-of-use and multi-platform usage we have rewritten it in Python. Through pyEVA's use of
deep learning tools, the process of identifying EIC plots as true or false can be automated, greatly speeding up the mass spectrometry pipeline of work.
<br/><br/> While this is meant as a quick startup guide, we also feature a more detailed user setup guide in the repository, and a video guide for setup on [Youtube](https://youtu.be/DCJblQjpbmc).

## Necessary Programs

Several other programs are necessary to install pyEVA. They are listed below:
1. [Anaconda](https://www.anaconda.com/)
2. [PyCharm](https://www.jetbrains.com/pycharm/download/#section=windows) (Community or Professional editions both work)
3. R and [R Studio](https://posit.co/download/rstudio-desktop/)

## Set up Environment

After installing all the programs, open the Anaconda Navigator and through it, PyCharm. Open the EVA_Python-master folder in PyCharm as a new project. In the terminal for PyCharm, type in `conda env create --file environment.yml`.
When prompted, type `conda env activate`


Make sure that the version of PyCharm and VS Code used are the newest version as differences may occur with older versions.

## R Packages

In R Studio, install the related packages: "XCMS", "ggplot2", "scales", and "dplyr" (If you already have, please skip). Type the following code into R Studio as an R script, 
making sure that the version installed is up-to-date.

<br/>`if (!requireNamespace("BiocManager", quietly = TRUE))`
<br/>`install.packages("BiocManager")`
<br/>`BiocManager::install("xcms")`
<br/>`install.packages("ggplot2")`
<br/>`install.packages("scales")`
<br/>`install.packages("dplyr")`

## Installation of Required Packages

To ensure that all the necessary packages are properly installed, in the PyCharm terminal, type `pip install -r requirements.txt`, then run it.

## IDE Startup

When use PyCharm: In PyCharm, once the necessary packages are installed and the environment has been initialized, press `CTRL+ALT+S`, select the project,
then `Python Interpreter`. From there, click `Add Interpreter`, `Add Local Interpreter`, `Conda Environment`, `Use Existing Environment`, and select 
`pyEVA`. In the terminal there should be a (pyEVA) beside your project location. This indicates that the system is ready to run pyEVA.

When use VS Code: 1. Go to Command Palette (Ctrl + Shift + P), click Python: Select Interpreter, Create Virtual Environment, Venv, and select Python 3.7.9 from the drop-down
list. 2. In the terminal, run pip install -r requirements.txt. 3. Open RStudio and install R packages listed in README.md. 4. Place the sample data (feature table and .mzXML file) into the Input folder
9. Run the code by executing python main.py in the terminal. 5 Output files will be in the Output folder

## Running the Program 

In `input` place a .csv file with the first two columns being `m/z` and `rt` (followed by the relevant data in successive columns), along with the related .mzXML or .mzML files.

In the PyCharm terminal, type: `python main.py`. This should start your program. Choose the level of smoothing (0, 1, 2), and wait for the EICs to be output
to the `EICplots` folder under `classifier`. In `output` there should be a .csv named `FinalTable.csv` with the results of the analysis, and a .csv called `PredictionOutcomes.csv`
with  Boolean values for the data input.

## Demo Data

We offer a set of data used for the demonstrations in the video [here](https://drive.google.com/file/d/1oMzXr3YHDV_7FaV6SS6MrUFQPtSZwy3o/view?usp=sharing)

## Contacts and Credits

For any issues or suggestions, please contact Tao Huan (thuan@chem.ubc.ca) or Ethan Wong-Ma (ethan.wongma@gmail.com)

The utmost of thanks to Shaoyun Tong for developing the first version of pyEVA, which was debugged and improved upon to make this version. Without her help
this would not be possible. Additionally, thanks to Yukai Wang for aiding in teaching me Python, which enabled further development of this project.

## Citation

[^1]: [Jian Guo, Sam Shen, Shipei Xing, Ying Chen, Frank Chen, Elizabeth M. Porter, Huaxu Yu, and Tao Huan
Analytical Chemistry 2021 93 (36), 12181-12186
DOI: 10.1021/acs.analchem.1c0130](https://pubs.acs.org/doi/pdf/10.1021/acs.analchem.1c01309)

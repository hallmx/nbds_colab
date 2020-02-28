# nbds_colab
> Literate programming for data science using nbdev, jupytemplate and Google Colaboratory


Nbds_colab is a template repository for small to medium sized data science projects which use the nbdev programming system and Google Colaboratory. It combines the best features of the following to give a complete low friction workflow for your project, from first code to package release.:

* fastai.nbdev - exploratory programming, automated documentation generation, integrated testing and easy PyPi package release [nbdev](https://github.com/fastai/nbdev//) 

* Google Colaboratory & Drive - low cost cloud computing with acceleration [Colaboratory](https://colab.research.google.com/)

* jupytemplate - standardized notebooks for data science [Xstreamrl](https://github.com/xtreamsrl/jupytemplate)

* Full GitHub integration


## Getting started

The following assumes a working knowledge of the nbdev exploratory programming system, jupiter notebooks, Google Colaboratory (Colab), Google Drive and GitHub. For more information on nbdev view the [documentation](http://nbdev.fast.ai/) and on how nbdev works with Google Colaboratory [nbd_colab]((https://github.com/hallmx/nbd_colab).

* Make sure you are logged in to your GitHub account then create a new GitHub repo from our template repo:  [nbds_colab_template](https://github.com/hallmx/nbds_colab/generate). Fill in the requested info and click 'Create repository from template'. 

* From GitHub, edit the `settings.ini` file of the new repo with your own personal and package information as described in the nbdev [documentation](http://nbdev.fast.ai/) and [tutorial](http://nbdev.fast.ai/tutorial/). Add any dependencies to the 'requirements' setting (requirements = dep1, dep2 etc) also in settings.ini. A set of test_flags have already been added (tst_flags = test_flag_colab|test_flag_imports|test_flag_GPU|test_flag_slow|test_flag_large|test_flag_other), and which can be customized if needed. 

* Activate GitHub Pages to display automatic documentation: click on 'Settings', then scroll down to GitHub Pages and select 'master branch/docs folder'. Edit the repo description by adding the auto-generated GitHub Pages link to the box next to the repo description at the top of the page.

* Finally clone the new repo to your Google Drive. A detailed description of how, and helpful tools to accomplish this, are provided by nbds-colabs's sister library, nbd_colab. The nbd_colab [documentation](https://github.com/hallmx/nbd_colab) will guide you through library installation and then cloning the new repo to your Google Drive as well as configuring it for GitHub integration. 



## The cloned template repo is now a template for your project.

You should now have a project directory somewhere permanant on your Google Drive and linked to a remote repo on GitHub. You can open the project notebooks (.ipynb files with names prefixed with '00' to '16') in Google Colab and edit them as any other Colab notebook. 

The project notebooks are set up for integration with the nbdev programming environment and Google Colab/Google Drive. If you are not familiar with nbdev or how it works with Google Colab, take a look at the nbdev [documentation](http://nbdev.fast.ai/) and/or [tutorial](http://nbdev.fast.ai/tutorial/). Then read [here](https://github.com/hallmx/nbd_colab)about nbdev-Colaboratory-Drive-GitHub integration with nbds_colab's sister package nbd_colab. 

## Project template.

The project template is structured to allow small to medium sized data science projects to be broken down into manageable units, each with its own notebook. You can put anything anywhere but if you are going to run with the already established project structure,  our idea of what should go where is as follows: 

* `00_core`: core functionality for the project (optional). 

* `01_dstemplate1` - `03_`: data science templates to edit with the main project code. 

* `04_` - `07_` add more notebooks as required!

* `08_ensemble1` - `09_`: code to create model ensembles from the output of `01_dstemplate` to `03_`.

* `10_final`: bring it all togather in the final project model or result.

* `11_common`: code, classes and functions shared between template files.

* `12_vis`: shared code for data visualization

* `13_dataproc`: shared data processing , preprocessing and feature engineering functionality

* `14_data`: data aquisition, initial processing and source description(s)

* `15_refs`: place all the project references and citations in one place for quick lookup



## Customizing the project template

Before the first commit and push to GitHub is a good time to customize the template for your particular project. 

* Delete unwanted notebooks (simply remove them from Google Drive) and add new notebooks (see the nbd_colab documentation on how to do this) so that the repo has the desired project structure. 

* You can rename the 'dstemplate', 'ensemble' and 'final' notebooks to something more meaningful for your project but remember to keep the nbdev naming convention of progressive double digits following by the new name. If you work in a team, also including the authors initials - so something like, e.g. '00_AB_data_exploration.ipynb' or 'AB_00_data_exploration.ipynb'. Don't forget to ammend any associated import statements to the new nb name as well! 

* Update all `#default_exp` flags with the new notebook name and don't forget to update all local imports similarly. Remove unwanted imports and add new ones as required. 

* Uncomment the `%cd command` just below library installs and change the <placeholder> to your project name. You need to be in the project directory for imports etc to work. Run this cell every time you reload the notebook. 

* Customize test_flags for development. As well as the built in `all_flags` the template ships with the following custom test_flags: `test_flag_colab`, `test_flag_import`s, `test_flag_GPU`, `test_flag_slow`, `test_flag_large`, and `test_flag_other`. Use these or create your own by editing settings.ini.

Now you can build the project library and documentation as described in the nbdev [documentation](http://nbdev.fast.ai/)and [nbd_colab](https://github.com/hallmx/nbd_colab). Don't forget to check for any diffs with `nbdev_diffs_nbs` and run tests with `nbdev_test_nbs`. If all is well, push the customized template with 'init commit' message or the like to Github. 

## The data science templates

The jupyter notebook data science templates are adapted from [xstreamsrl's jupytemplate](https://github.com/xtreamsrl/jupytemplate) project, where the aim is to provide a greater degree of structure and standardization to data science projects. Here we take the natural next step and place them into a literate programming environment. Dive in and edit them as needed for your project. 



## The project life cycle

There is a certain life cycle to projects developed with nbdev and Google Colab. 

1. Edit notebooks as required. Each Colab notebook must install and import all it's own dependencies.

2. Write tests and documentation straight into the notebook alongside (well above or below!) related code.

3. Consider which cells should be exported as .py scripts, which should be included in the documentation etc and add  appropriate flags to the top of cells. 

4. Review cell outputs - some you will want to show in the documentation and some you will want to hide by collapsing the output box in Colab.

5. When done, check the notebook can run independently top to toe.

6. Build the library, build the documentation and check for diffs

7. Run tests with `nbdev_test_nbs`. Debug failing code and notebooks. Consider adding test_flags to notebook cells causing exception but where you don't want to ammend the code. An `all_flags` test_flag can be added to exclude whole notebooks from tests, for example if they are unfinished. 

8. Push the new version to GitHub. Check the GitHub Actions panel and review documentation on GitHub pages to ensure all is as expected. 

9. Repeat the cycle until the project is finished.

10. New package versions can be released on PyPi with a few simple commands

That is a very quick run though, and if anything is unclear the best place to go is the nbdev [documentation](http://nbdev.fast.ai/) and nbd_colab [guide](https://github.com/hallmx/nbd_colab) for more information and help getting started with your project. 

## Articles.

nbdev: use Jupyter Notebooks for everything, Jermy Howard, Dec 02 2019. [here](https://www.fast.ai/2019/12/02/nbdev/). 

Introducing jupytemplate: configurable templates for Jupyter, Emanuele Fabbiani. Feb 4th 2020. [here](https://towardsdatascience.com/stop-copy-pasting-notebooks-embrace-jupyter-templates-6bd7b6c00b94)






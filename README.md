# nbds_colab
> Literate programming template for data science projects using jupytemplate, nbdev and Google Colaboratory


nbds_colab is a template repository designed for data science projects that want to use with the fastai nbdev literate programming environment with jupytempates all on Google Colaboratory and Google Drive. It has been generated and adapted from the [fastai.nbdev_template](https://github.com/fastai/nbdev_template) and xstreamrl [jupytemplate]().

## Getting started

The folowing assumes you are familiar with fastai [nbdev](), [jupytemplates](), Google Colaboratory (Colab), Google Drive and have an active GitHub account.

* To begin a new data science project using nbds_colab you need to be logged in to your github account and then simply click here [nbdev-colab template](). Fill in the requested info and click 'Create repository from template', and a new GitHub repo with all the template code will be created in your GitHub. 

* From GitHub, edit the `settings.ini`file of the new repo with your own personal and package information as described in the nbdev [docs]() and [tutorial](). Additionally add any dependencies to the 'requirements' setting (requirements = dep1, dep2 etc) also in settings.ini. 

* Activate GitHub Pages to display automatic documentation: click on settings, then scroll down to GitHub Pages and select 'master branch/docs folder'. Edit the repo description by adding the auto-generated GitHub Pages link to box next to the repo description at the top of the page.

* Finally clone the new repo to your Google Drive. A detailed description of how, and helpful tools to accomplish this, are provided by nbds-colabs's sister package, `nbd_colab`. Go to [nbd_colab]() and follow the instructions on how to install nbd_colab, clone the new project repo to your Google Drive and then configure it for GitHub integration. 

* You're ready to go. 



## Using the Template repo

You should now have a project directory somewhere permanant on your Google Drive and linked to a remote repo on GitHub. Great that is the tricky bit!

You can now open the project notebooks (.ipynb files with names prefixed with '00' to '16') in Google Colab and edit them as normal. Nbdev enables literate programming through automatic documentation generation from jupyter notebooks. If you are not familiars with how this works read the nbdev [docs]() or the excellent get started [tutorial](). An approach, helpful code snippets and a troubleshooting guide all aimed at smooth workflow integration of nbdev, Colab, Drive and GitHub ar eprovided by [nbde_colab](). 

## The data science templates

The jupyter notebook data science templates are the work of [xstreamsrl jupytemplate](https://github.com/donlelef/jupytemplate). See xtreamsrl [blog post](https://towardsdatascience.com/stop-copy-pasting-notebooks-embrace-jupyter-templates-6bd7b6c00b94) for the rational behind the templates, but in brief, they aim to provide a greater degree of structure and standardization to data scioence projects. Here we take the natural next step and place them into a literate programming environment. 

Just dive in and edit them as needed. 



## Template repo structure

The template repo is structured to allow large data science projects to be broken down into manageable units, each with its own notebook. You can put anything anywhere but if you are going to run with the already established repo structure our idea of what should go where is as follows: 

* 00core: core functionality for the project (optional). 

* `01_dstemplate1` - `03_`: the data science templates to edit with the project code. Separate out different aspects - e.g. different approaches or models, into to different notebooks. These nbs import code from `11_common`, `12_vis`, `13_dataproc` and `14_data`. There is space from `04_` - `07_` to add more!

* `08_ensemble1` - `09_`: code to ensemble different models from `01_dstemplate` to '03_`.

* `10_final`: the final project outcome or model.

* `11_common`: code, classes and functions shared between template files.

* `12_vis`: plots, image manipulation and code required for data visualization

* `13_dataproc`: shared data processing , preprocessing and feature engineering functionality

* `14_data`: data aquisition, initial processing and source description(s)

* `15_refs`: place all the project references and citations in one place for quick lookup

You can rename the dstemplate, ensemble and final notebooks to something more meaningful for your project but remember to keep the nbdev naming convention of a double digit following by the name of your choice, e.g. `00_your_new_name.ipynb`. Don't forget to ammend associated import statements as well.

Notebooks can also be deleted and new ones added but the boilerplate code at the top must always be present fro smooth integration with Google Drive, nbdev and GitHub. The nbd_colab [docs]() describes how to add a new notebook as well as generally how to manage the project entirely from Google Colab. 


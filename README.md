# Using Apache SystemML for Machine Learning in a Data Science Experience (DSX) Notebook

In this developer journey we will use Apache SystemML running on IBM Data Science Experience (DSX) to perform a Machine Learning exercise. DSX is an interactive, collaborative, cloud-based environment where data scientists, developers, and others interested in data science can use tools (e.g., RStudio, Jupyter Notebooks, Spark, etc.) to collaborate, share, and gather insight from their data. Apache SystemML is a flexible machine learning platform that is optimized to scale with large data sets.

When you have completed this journey, you will understand how to:

* Use [Jupyter Notebooks](http://jupyter.org/) to load, visualize, and analyze data
* Run Notebooks in [IBM Data Science Experience](https://datascience.ibm.com/)
* Leverage [Apache SystemML](http://systemml.apache.org) as a machine learning library

The intended audience for this journey is both application developers and other stakeholders who wish to utilize the power of Data Science quickly and effectively to solve machine learning problems using Apache SystemML. Although Apache SystemML provides various out-of-the box algorithms to experiment with, this specific journey will provide a Linear Regression example to demonstrate the ease and power of Apache SystemML. Additionally, users can develop their own algorithms using Apache SystemML's Declarative Machine Language (DML) which has R or Python like syntax, or customize any algorithm provided in the package. For more information about additional functionality support, documentation, and the roadmap, please visit [Apache SystemML](http://systemml.apache.org).

![](doc/source/images/architecture.png)

## Flow

1. Load the provided notebook onto the IBM Data Science Experience platform.

2. The notebook interacts with an Apache Spark instance.

3. A sample big data dataset is loaded into the Jupyter Notebook.

4. To perform machine learning, Apache SystemML is used atop Apache Spark.

## Included Components

* [IBM Data Science Experience](https://www.ibm.com/bs-en/marketplace/data-science-experience): Analyze data using RStudio, Jupyter, and Python in a configured, collaborative environment that includes IBM value-adds, such as managed Spark.
* [IBM Analytics for Apache Spark](https://console.ng.bluemix.net/catalog/services/apache-spark): An open source cluster computing framework optimized for extremely fast and large scale data processing.
* [Bluemix Object Storage](https://console.bluemix.net/catalog/services/object-storage): Build and deliver cost effective apps and services with high reliability and fast speed to market in an unstructured cloud data store.

## Featured technologies

* [Jupyter Notebooks](http://jupyter.org/): An open-source web application that allows you to create and share documents that contain live code, equations, visualizations and explanatory text.
* [Apache SystemML](http://systemml.apache.org): An open source machine learning library. It allows data scientists to express machine learning algorithms through declarative language (DML) using R or Python like syntax.

### State of the art

![](doc/source/images/state-of-the-art.png)

# Watch the Video

[![](http://img.youtube.com/vi/cYUdXFEmxP4/0.jpg)](https://www.youtube.com/watch?v=i0pcqvSAAss)

# Steps

Follow these steps to setup and run this developer journey. These steps are described in detail below.

1. [Sign up for the Data Science Experience](#1-sign-up-for-the-data-science-experience)
2. [Create the notebook](#2-create-the-notebook)
3. [Run the notebook](#3-run-the-notebook)
4. [Save and Share](#4-save-and-share)

## 1. Sign up for the Data Science Experience

Sign up for IBM's [Data Science Experience](http://datascience.ibm.com/). By signing up for the Data Science Experience, two services will be created in your Bluemix account: ``DSX-Spark`` and ``DSX-ObjectStore``. If these services do not exist, or if you are already using them for some other application, you will need to create new instances.

To create these services:
* Login or create your [Bluemix](http://bluemix.net) account.
* Create your Spark service by selecting the service type [Apache Spark](https://console.bluemix.net/catalog/services/apache-spark). If the name has not already been used, name your service ``DSX-Spark`` so that you can keep track of it.
* Create your Object Storage service by selecting the service type [Cloud Object Storage](https://console.bluemix.net/catalog/infrastructure/object-storage-group). If the name has not already been used, name your service ``DSX-ObjectStorage`` so that you can keep track of it.

> Note: When creating your Object Storage service, select the ``Swift`` storage type in order to avoid having to pay an upgrade fee.

Take note of your service names as you will need to select them in the following steps.

## 2. Create the notebook

First you must create a new Project:
* From the [IBM Data Science Experience page](https://apsportal.ibm.com/analytics) either click the ``Get Started`` tab at the top or scroll down to ``Recently updated projects``.
* Click on ``New project`` under ``Recently updated projects``.
* Enter a ``Name`` and optional ``Description``.
* For ``Spark Service``, select your Apache Spark service name.
* For ``Storage Type``, select the ``Object Storage (Swift API)`` option.
* For ``Target Object Storage Instance``, select your Object Storage service name.
* Click ``Create``.

![](doc/source/images/create-project.png)

Create the Notebook:
* Click on your project to open up the project details panel.
* Click ``add notebooks``.
* Click the tab for ``From URL`` and enter a ``Name`` and optional ``Description``.
* For ``Notebook URL`` enter: https://github.com/IBM/SystemML_Usage/blob/master/notebooks/Machine-Learning-Using-Apache-SystemML.ipynb
* For ``Spark Service``, select your Apache Spark service name.
* Click ``Create Notebook``.

![](doc/source/images/create-notebook.png)

## 3. Run the notebook

When a notebook is executed, what is actually happening is that each code cell in
the notebook is executed, in order, from top to bottom.

Each code cell is selectable and is preceded by a tag in the left margin. The tag
format is `In [x]:`. Depending on the state of the notebook, the `x` can be:

* A blank, which indicates that the cell has never been executed.
* A number, which represents the relative order this code step was executed.
* A `*`, which indicates that the cell is currently executing.

There are several ways to execute the code cells in your notebook:

* One cell at a time.
  * Select the cell, and then press the `Play` button in the toolbar.
* Batch mode, in sequential order.
  * From the `Cell` menu bar, there are several options available. For example, you
    can `Run All` cells in your notebook, or you can `Run All Below`, that will
    start executing from the first cell under the currently selected cell, and then
    continue executing all cells that follow.
* At a scheduled time.
  * Press the `Schedule` button located in the top right section of your notebook
    panel. Here you can schedule your notebook to be executed once at some future
    time, or repeatedly at your specified interval.

## 4. Save and share

### How to save your work:

Under the `File` menu, there are several ways to save your notebook:

* `Save` will simply save the current state of your notebook, without any version
  information.
* `Save Version` will save your current state of your notebook with a version tag
  that contains a date and time stamp. Up to 10 versions of your notebook can be
  saved, each one retrievable by selecting the `Revert To Version` menu item.

### How to share your work:

You can share your notebook by selecting the “Share” button located in the top
right section of your notebook panel. The end result of this action will be a URL
link that will display a “read-only” version of your notebook. You have several
options to specify exactly what you want shared from your notebook:

* `Only text and output`: will remove all code cells from the notebook view.
* `All content excluding sensitive code cells`:  will remove any code cells
  that contain a *sensitive* tag. For example, `# @hidden_cell` is used to protect
  your dashDB credentials from being shared.
* `All content, including code`: displays the notebook as is.
* A variety of `download as` options are also available in the menu.

# License

[Apache 2.0](LICENSE)

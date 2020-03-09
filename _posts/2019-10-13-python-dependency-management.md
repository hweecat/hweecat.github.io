---
layout: post
title: "Understanding Python Dependency Management using pideptree"
description: "Learning about tree-based dependency management for a team project developed in Python using pipdeptree"
excerpt: "Dependency management is important, as packages depend on versions of other core packages in order to run as intended. Typically in a Python project, dependencies are downloaded using a requirements.txt file, which lists the packages and their dependencies as a flat file. While the package versions are included in the requirements.txt file, the dependency relationships are not explicitly stated."
tags: til python
---
---

Dependency management is important, as packages depend on versions of other core packages in order to run as intended. Typically in a Python project, dependencies are downloaded using a requirements.txt file, which lists the packages and their dependencies as a flat file. While the package versions are included in the requirements.txt file, the dependency relationships are not explicitly stated. Determining the dependency relationships between packages using requirements.txt often requires "reverse engineering" in the form of tracing the dependencies of each installed package and figuring out why pip installed certain packages (since pip does the work of resolving package dependencies when installing packages).

While searching for ways to resolve the multiple requirements.txt files from my colleages within a team project, I stumbled across `pipdeptree`, a command-line utility for displaying installed Python packages in the form of a dependency tree. The output is displayed in a tree-based format instead of a flat list, showing the dependency relationships between installed Python packages and their associated dependencies.

## Using pipdeptree for dependency management

To install pipdeptree, use the following command:

```bash
pip install pipdeptree
```

or, if you prefer to use conda:

```bash
conda install -c conda-forge pipdeptree
```

In order to be able to manage dependencies within virtual environments, `pipdeptree` has to be installed within each individual virtual environment. If you are starting a new virtual environment for a project and would like to use `pipdeptree` for dependency management, you would have to install `pipdeptree` in that new virtual environment.

### Dependency tree output

To view the dependency tree of every installed package within the virtual environment:

```bash
pipdeptree
```

To view the dependency tree of a particular package e.g. pandas, the flag `-p` or `--packages` is used:

```bash
pipdeptree -p pandas
```

To view the reverse dependency tree - the packages that are dependent on every installed package within the virtual environment, the flag `-r` or `--reverse` is used:

```bash
pipdeptree -r
```

Sometimes we may prefer to have the dependency tree displayed as json representation to be used as input to other external tools. In this case, the flag `j` or `--json` outputs a flat list of all packages with their immediate dependencies, while the flag `--json-tree` outputs a nested json representing the dependency relationships between packages.

```bash
pipdeptree --json       # for immediate dependencies

pipdeptree --json-tree  # for nested dependencies
```

To lay out the dependency graph, GraphViz is required in both the command-line interface and the virtual environment. The available output formats are dot, jpeg, pdf, png and svg. For example, if I would like to output my dependency graph in pdf, I use the following command:

```bash
pipdeptree --graph-output pdf > dependencies.pdf
```

#### Installing Graphviz in virtual environment

First, I installed Graphviz on Ubuntu 18.04 LTS Windows Subsystem for Linux (WSL) using `apt-get install` by using the following command:

```bash
sudo apt-get update

sudo apt-get install graphviz
```

Next, I installed graphviz for Python using conda:

```bash
conda install graphviz
```

As of now, I have yet to get Grahpviz running successfully on Windows + Anaconda, but I will try setting up Graphviz on Windows to work with pipdeptree when I have the time. Nevertheless, Graphviz works smoothly on Ubuntu 18.04 LTS WSL, so my current dependency management workflow is now on pip + venv + pipdeptree - and it works pretty smoothly without additional packages that conda installs in environments!

## References

1. [pipdeptree . PyPI](https://pypi.org/project/pipdeptree/)
2. [pipdeptree :: Anaconda Cloud](https://anaconda.org/conda-forge/pipdeptree)
3. [Using pipdeptree in a virtualenv](http://www.columbia.edu/~njn2118/journal/2016/3/24.html)
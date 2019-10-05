---
layout: post
title: "Understanding Python Dependency Management using pideptree"
description: "Learning about tree-based dependency management for a team project developed in Python using pipdeptree"
excerpt: "Dependency management is important, as packages depend on versions of other core packages in order to run as intended. Typically in a Python project, dependencies are downloaded using a requirements.txt file, which lists the packages and their dependencies as a flat file. While the package versions are included in the requirements.txt file, the dependency relationships are not explicitly stated."
---
---

Dependency management is important, as packages depend on versions of other core packages in order to run as intended. Typically in a Python project, dependencies are downloaded using a requirements.txt file, which lists the packages and their dependencies as a flat file. While the package versions are included in the requirements.txt file, the dependency relationships are not explicitly stated. Determining the dependency relationships between packages using requirements.txt often requires "reverse engineering" in the form of tracing the dependencies of each installed package and figuring out why pip installed certain packages (since pip does the work of resolving package dependencies when installing packages).


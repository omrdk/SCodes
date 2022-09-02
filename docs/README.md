# DoxygenConfig

This repo contains template for Doxygen configuration allowing to document C++ and QML code and generate nice looking documentation. To see how write documentation in Doxygen format, take a look on [Doxygen Website](https://www.doxygen.nl/manual/docblocks.html)

## Table of contents
* [Doxygen](#Doxygen)
* [Files](#Files)
* [Installing](#Installing)
* [Setup](#Setup)
* [Usage](#Usage)
* [Changing-UI](#Changing-UI)

## Doxygen

Doxygen is the tool we use to create documentation in our projects. Before you start generating documentation, you first need to comment your code properly. [Here](https://www.doxygen.nl/manual/docblocks.html) you can see how to do it. Remember to comment on all important elements so that someone who has not worked on the project knows what it is about.

## Files

* **Doxyfile** - configuration file for Doxygen

* **doxygen-awesome.css** - style sheet file describing the default appearance for Scythe Studio documentation

* **doxygen-awesome-sidebar-only.css** - style sheet changing navigation to more modern sidebar only

* **Scythe_Studio_logo.png** - our logo addded to documentation

## Installing

1. Download Doxygen from [Official Doxygen Site](https://www.doxygen.nl/download.html)

2. Add Doxygen to PATH variable in your system environment variables

3. Install Doxyqml through pip3 (need to install python first)
    
    ```pip3 install doxyqml```

4. Add Doxyqml to PATH variable in your system environment variables

5. Install graphviz from [Official Graphviz Site](https://www.graphviz.org/download/) (version > 1.8.10)

6. Add graphviz to PATH variable in your system environment variables

## Setup

The first thing is to place the files in the root folder of your current project. You can create a folder for this, e.g. *"documentation-config"*

Next you need to  modify the **Doxyfile** file. You can do this through build-in Doxygen program called **Doxywizard** (if you using this method, select expert mode) or use any text-editor (VSCode for example).

### Important fields to modyfy in _Doxyfile_!

* _PROJECT_NAME_ -> Set to the current project name

* _PROJECT_NUMBER_ -> Set to the  actual project version 

* _PROJECT_BRIEF_ -> Add a short description to your project

* _INPUT_ -> Sets the folders where the code for the documentation is located. So in 99% cases you should add **src** folder and **qml** folder. **IMPORTANT** -> Remember that if the folder you specify contains _build_ folder, doxygen will also scan it, which will generate an incorrect documentation. In that case, add this directory to _EXCLUDE_)

### Optional fields to modyfy in _Doxyfile_

* _PROJECT_LOGO_ -> If the current project has a logo, you can set it up. By default the Scythe Studio logo will be used

* _OUTPUT_DIRECTORY_ -> Sets the destination folder for the documentation. By default new folder "documentation-generated" will be created

Once these variables are set, your configuration file is ready. You can now proceed to create the documentation

## Usage

To generate the documentation you can use **Doxywizard** (open you **Doxyfile** and hit run) or the command line

`doxygen Doxyfile`

It may take a while because we also generating graphs and diagrams. Documentation should be generated inside output directory. To view it, find _index.html_ file and open in browser

## Changing-UI 

If you need to change the graphic style of the documentation, you can do it by editing the _doxygen-awesome.css_ file
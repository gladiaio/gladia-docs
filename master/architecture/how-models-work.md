# Model

## Model Definition

For a given AI Task multiple Models can be applied.

Usually researchers are trying to outperform existing models by comparing Quantitatively. A great resource to compare tasks and quantitative performance is [paperswithcode.com](https://paperswithcode.com).

However, so far, nobody is focussing on qualitative results. One of the reason of the creation of UnifAI was to be able to compare models Apple to Apple qualitatively. Persived quality is what users will face compared to Quantative theorical results.

A model represents a specific implementation of a given task over a [combination of INPUT/OUTPUT](../../aipi-basics/input-ouput-tasks.md).

## Creating your first model

The folder and file structure should be the following:

![Example of the directory structure for a custom model named "my_model" for an IMAGE to TEXT combination for the image recognition task](<../../.gitbook/assets/Capture d’écran 2021-10-12 à 14.35.54.png>)

## Core Model Files

As presented above :

1. a folder with the name of your model should be created within the associated task folder (image_recognitions in the example).
2. a python file with the name of your model should be placed in your model folder. The only thing the framework needs if a predict function inside this python file. Below is an example for a sentiment analysis model named _nlptown-bert-base-multilingual-uncased-sentiment_

{% embed url="https://gist.github.com/jqueguiner/03229ca66a2718621b33c11bdcb15259" %}

## Additionnal environment files

1. a \___init\_\__.py file should also be placed in your model folder to indicate to the system that it's a python package directory.
2. you can add as many files/folders you want in this directory it's yours ! However keep in mind that it's better to store your model file (that can be huge) outside of the framework (see the Storing and retrieving your model files [section](storing-and-retrieving-your-model-files.md))
3. If you want your model folder/package directory to behave independently relating to import (importing files and folder within this folder) use the following configuration for your \___init\_\_.py file:_

{% embed url="https://gist.github.com/jqueguiner/4a7371a38a3ccd5d276c07bb954ad408" %}

{% hint style="info" %}
We are planning to improve this onboarding in the future with a dynamic scafolding generated from a cli-utils.
{% endhint %}

##

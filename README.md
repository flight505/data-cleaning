# Data Cleaning (V1.0)

This repository shows off regularly encountered **Data Cleaning** tasks in the context of Data Science and Machine Learning projects. I want to expose a set of techniques I found out while learning Data Science throughout my personnal experience, and illustrate them thanks a randomly generated dataset, intentionally inserting errors and wrong data format.  
The following code in written in Python and mainly uses [Pandas](https://pandas.pydata.org/) and [Numpy](http://www.numpy.org/) libraries.

## 1) Dataset generation

In order to show a few Data Cleaning techniques, I needed to find a *"messy"* dataset, but messy in the way I could apply all the cleaning methods I wanted, while being sure I could show all of them, and explain them in an understandable way. Thus, I tried to look for an appropriate dataset but I could not find one of my taste. Therefore, I decided to **create my own dataset**, combining randomly generated elements with randomly introduced errors inside it.

Here is a subset of my randomly generated messy dataset, with its set of inherent problems :
![Initial messy dataset](images/initial_messy_dataset.png)

As you can see in this portion of the dataset, there are simply a lot of problems, missing values, wrong formats, useless data, etc. Thus I am going to use this awful dataset to illustrate some methods in my Data Cleaning process to cleanse it, and make it more appropriate for further use.

## 2) Dataset transformation

Here are all the methods I used to work on this dataset. I tried to cluster them with colors depending whether they are **deletion**, **filling** or **fixing** methods.

The exhaustive list of methods, that you can see in the image below, is the following : `strange_feature_deletion`, `missing_value_as_special_category`, `known_value_spelling_correction`, `mean_value_filling`, `useless_observation_deletion`, `useless_feature_deletion`, `median_value_filling`, `good_format_spelling_correction`, and `strange_observation_deletion`.

![Data Cleaning methods](images/data_cleaning_methods.png)

## 3) Data Cleaning pipeline

My Data Cleaning pipeline will consist in a tenth or less steps to mainly : delete useless observations or features, consider missing values differently, fill numerical features with the mean or the median of the corresponding feature, correct spelling mistakes, fix bad formatting, and so on... I am then describing below the errors or inconveniences I could face with this data, and how to solve them.

### a/ Strange feature deletion

There is a feature in my dataset that I voluntarily created and called `Strange`. Sometimes, it happens there are a few **strange features** that do not well understand, you cannot interpret the values in it, you even do not know what the values mean and how they were generated. These features can be deleted to protect yourself against attacks, system penetration or these kind of security problems (`strange_feature_deletion`).

![Strange : Strange feature deletion](images/strange_feature_deletion.png)

### b/ Missing/invalid category value

In the dataset I am handling here, the `Category` feature of my data can take normal values, or values that look like **missing/invalid information**. I need to clean them up and consider them as a single and same value representing the notion of "missing category" (`missing_value_as_special_category`).

![Category : Missing/invalid category value](images/missing_category_value.png)

### c/ Misspelled values

The `Country` feature of the dataset contains a certain number of countries. However, a few of them are sometimes **misspelled**. Uniformisation of the values is an important step because it will protect you against wrong interpretations in your future data analysis step (`known_value_spelling_correction`).

![Country : Misspelled values](images/misspelled_values.png)

### d/ Mean filling missing values

There are some cases when a feature has pretty homogeneous values but a **few missing ones**. If this feature is numerical, like my `Height` dataset feature, it can be clever to replace the missing values by the mean of this feature (`mean_value_filling`).

![Height : Mean filling missing values](images/mean_filling_value.png)

### e/ Useless observations deletion

Some feature like `Name` permit to identify data points in the dataset. However, this value can be **missing** soometimes, and analysis that requires identification or relationships are difficult to proceed in these cases. Then, deleting these single observations help you narrow your dataset to only useful information and individuals (`useless_observation_deletion`).

![Name : Useless observations deletion](images/useless_observations_deletion.png)

### f/ Useless feature deletion

In my dataset, the `Missing` feature voluntarily **lacks a very large amount of data**. Therefore, this feature does not bring any consequent interest to the whole dataset, and the potential analysis that are to be made on it. Deleting this feature will helps analysis to be focused on interesting features only (`useless_feature_deletion`).

![Missing : Useless feature deletion](images/useless_feature_deletion.png)

### g/ Median filling for erroneous values

A specific feature `Salary` has been enhanced with a few **outliers** that could perturbate analysis. For this numerical feature, it can be interesting to replace these outliers with the median of the feature, to analyse data further on without getting wrong on the whole dataset interpretations (`median_value_filling`).

![Salary : Median filling for erroneous values](images/median_filling_value.png)

### h/ Wrongly formatted dates

There are numerous cases where dates and **wrongly formatted** accross datasets, and I made the voluntary mistake in mine on the `Date` feature. Dates shall always, and absolutely, have a consistent format throughout the dataset in order to be analysed properly (`good_format_spelling_correction`).

![Date : Wrongly formatted dates](images/wrongly_formatted_dates.png)

### i/ Strange observations deletion

Sometimes, there are some features that contain very strange information, and **Email** is often a good aim. This could come from potentially harmful users, systems or interactions with our dataset, and we want to be able to filter out these information in the best manner, usually by deleting suspect observations (`strange_observation_deletion`).

![Email : Strange observations deletion](images/strange_observations_deletion.png)

---

### ROADMAP

1. Refactoring
   - [ ] Create a dedicated file to agregate Data Cleaning methods
   - [ ] Add comments in dataset generation and errors generation modules

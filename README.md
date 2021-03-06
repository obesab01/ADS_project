# Applied Data Science Project

## Introduction
This project is part of the course Applied Data Science. The goal is to use certain data
science tools to create a Neural Network. This project wants to scrape the bestsellers of three
Amazon pages and put them all in one dataframe. Then this data is used to train a Deep Network
and in the end we want to predict a new entry with this trained model. As a fun feature we
also implemented an API for Donald Trump quotes. Donald will give you a personal quote for
the book you chose.

## Table of contents
* [Technologies](#technologies)
* [Pre Settings](#pre-settings)
* [Data Collection](#data-collection)
* [EDA](#eda)
* [Data Cleaning](#data-cleaning)
* [Data Visualization](#data-visualization)
* [Data Model](#data-model)
* [Test your Book](#test-your-book)
* [Donald API](#donald-api)
* [GitHub](#github)

### Technologies
Project is created with:
* Python
* Google Colab

### Pre Settings
The project starts with mounting the personal google drive. You might want to create the same
folder structure like we did. Go to your MyDrive/Colab Notebooks folder and create the following:
* CSV
* data
* GitHub
In the CSV folder, create the following folders:
* INDIA
* UK
* USA
Now you should be able to run the code without problems.
The Removing all files in advance section does not need to be runned the first time!

### Data Collection
This part is devided in 3 different sections, so that Amazon USA, India and UK are scraped. The code in this section is inspired by this [datacamp tutorial](https://www.datacamp.com/community/tutorials/amazon-web-scraping-using-beautifulsoup?utm_source=adwords_ppc&utm_campaignid=898687156&utm_adgroupid=48947256715&utm_device=c&utm_keyword=&utm_matchtype=b&utm_network=g&utm_adpostion=&utm_creative=332602034352&utm_targetid=aud-392016246653:dsa-429603003980&utm_loc_interest_ms=&utm_loc_physical_ms=1003165&gclid=CjwKCAjwtJ2FBhAuEiwAIKu19gH-cv1X6FOiMwKr5Stfx_dAr48p095QWwbVgIzhW71ErBNqtV1U0RoCrwUQAvD_BwE).

### EDA
EDA is performed for each dataset individually.

### Data Cleaning
The goal is to combine all separate datasets to one only. Since we have different currencies,
we need to first remove the currency symbol and then convert everything to US dollars.
The exchange rate is copied manually. So if you want to have the most recent one, you need to
update the variables Exchange_USD_UK und Exchange_USD_INR first.


### Data Visualization
After cleaning we perform another EDA report with sweetviz. If you also work with Google Colab
the reports are saved in your Drive and you have to open them there.
In a last step we merge all data to one frame.
We perform a last visualization before actually creating the NN model.

### Data Model
Since we have a lot of categorical data, we need to encode them to numerical values first. 
We save the used encoders for later.
We want to predict the Rating in the end, so we set this feature for y. Our model is build with
one input layer, four hidden layers and one output layer. This is a regression model, so our
loss function is the mean absolute error and our optimizer is the adam algorithm.
After we have trained the model, we save it for later.
We establish two checkpoints and train the model again. Then we draw our learning curves, to see
if we experience over- or underfitting.

### Test your book
Now we want to see, what our model would predict with an actual new entry. Here comes the tricky
part. So that our encoder works again, it needs a value for rating. Therefor after we have done the
encoding again, we drop the value for rating again.
Then we let the model predict for our new entry.

### Donald API
We establish the API to the Donald Trump databank and let them say an individual message for
the testing person and for the new entry book.

### Github
The last section uploads the most current version to our public Github repository.
If it does not work doublecheck and update the variables username, token and repository to your own. 
To get the actually repository you can use the download code to get the most current file from Github. 




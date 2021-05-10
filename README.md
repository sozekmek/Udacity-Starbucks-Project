# Udacity-Starbucks-Project
## Udacity Data Science Nanodegree Program project

### Introduction
This data set contains simulated data that mimics customer behavior on the Starbucks rewards mobile app. Once every few days, Starbucks sends out an offer to users of the mobile app. An offer can be merely an advertisement for a drink or an actual offer such as a discount or BOGO (buy one get one free). Some users might not receive any offer during certain weeks.

Not all users receive the same offer, and that is the challenge to solve with this data set.

Your task is to combine transaction, demographic and offer data to determine which demographic groups respond best to which offer type. This data set is a simplified version of the real Starbucks app because the underlying simulator only has one product whereas Starbucks actually sells dozens of products.

Every offer has a validity period before the offer expires. As an example, a BOGO offer might be valid for only 5 days. You'll see in the data set that informational offers have a validity period even though these ads are merely providing information about a product; for example, if an informational offer has 7 days of validity, you can assume the customer is feeling the influence of the offer for 7 days after receiving the advertisement.

You'll be given transactional data showing user purchases made on the app including the timestamp of purchase and the amount of money spent on a purchase. This transactional data also has a record for each offer that a user receives as well as a record for when a user actually views the offer. There are also records for when a user completes an offer.

Keep in mind as well that someone using the app might make a purchase through the app without having received an offer or seen an offer.

### Libraries and Dependencies

Main library that I have used on this project was Pandas library. Then of course the Numpy library. For the visualizations, mMtplotlib was used and for the correlation map Seaborn was used. Lastly, for the prediction model ScikitLearn was used for test-train split, Classifier model creation and evaluation purposes.

### Data Sets
The data is contained in three files:

* portfolio.json - containing offer ids and meta data about each offer (duration, type, etc.)
* profile.json - demographic data for each customer
* transcript.json - records for transactions, offers received, offers viewed, and offers completed
Here is the schema and explanation of each variable in the files:

#### portfolio.json

* id (string) - offer id
* offer_type (string) - type of offer ie BOGO, discount, informational
* difficulty (int) - minimum required spend to complete an offer
* reward (int) - reward given for completing an offer
* duration (int) - time for offer to be open, in days
* channels (list of strings)

#### profile.json

* age (int) - age of the customer
* became_member_on (int) - date when customer created an app account
* gender (str) - gender of the customer (note some entries contain 'O' for other rather than M or F)
* id (str) - customer id
* income (float) - customer's income

#### transcript.json

* event (str) - record description (ie transaction, offer received, offer viewed, etc.)
* person (str) - customer id
* time (int) - time in hours since start of test. The data begins at time t=0
* value - (dict of strings) - either an offer id or transaction amount depending on the record

### Summary of the Documents
#### data
Under this folder, raw data is stored as json formats.
* portfolio.json
* profile.json
* transcript.json

#### Starbucks_Capstone_notebook-zh.ipynb
Template for the initial stage of the notebook at the start of the project.

#### Starbucks_Capstone_notebook.ipynb
Notebook where I have made all my coding on. All the pictures and results on the blogpost are taken from my work on this notebook.

#### data\bogo.json : JSON file to store bogo(buy one get one) dataframe that I have created on the notebook. It took a very long time to process and create the dataframe so I have saved it as JSON in case I need them for further use.
#### data\disc.json : JSON file to store disc(discount) dataframe that I have created on the notebook. It took a very long time to process and create the dataframe so I have saved it as JSON in case I need them for further use.
#### data\info.json : JSON file to store info(informational) dataframe that I have created on the notebook. It took a very long time to process and create the dataframe so I have saved it as JSON in case I need them for further use.

#### pic1.png : Picture uploaded by Udacity to define conda update process.
#### pic2.png : Picture uploaded by Udacity to define conda update process.

### Conclusions
I had three hypothesis at the start of the project:
* With Age, Gender and Income and Type of Offer information I can obtain a satisfactory model.
* With lower Age, I am expecting higher effect of the offers.
* With lower Income, I am expecting higher effect of the offers.

For the first one, I was able to accomplish, at least with a certain level of performance but of course it needs improvement.
According to my prediction model, age doesn't have any significant effect on the outcome so this hypothesis can be rejected.
According to my prediction model, income doesn't have any significant effect on the outcome so this hypothesis can be rejected.

However, my prediction model needs improvement and common sense says age and income will be effecting the behavior so I am not ready to reject the last two points. Upon further improvement on the model, these shall be tested again.

For understanding how the work has been done, please check my blogpost at the below link:
https://learndatascy.blogspot.com/2021/05/analysis-of-effectiveness-of-starbucks.html

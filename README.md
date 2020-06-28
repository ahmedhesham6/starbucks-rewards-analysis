# Starbucks Simulation Analysis

Detailed analysis of simulated data that mimics customer behavior on the Starbucks rewards mobile app, along with a machine learning model that predicts whether a customer will respond to an offer. There is also a [blog post](https://medium.com/@ahmedetcho16/starbucks-rewards-app-a-gateway-to-customers-buying-patterns-617e4e360570) that describes the findings of the analysis.

## Table of contents

- [Quick Start](#quick-start)
- [Project Motivation](#project-motivation)
- [File Description](#file-description)
- [Data Sets](#data-sets)
- [Summary](#summary)
- [Author](#author)
- [Copyright and License](#copyright-and-license)

## Quick Start

There are 2 options available:

- Clone the repo: `git clone https://github.com/ahmedhesham6/starbucks-rewards-analysis.git`
- [Download the latest release](https://github.com/ahmedhesham6/starbucks-rewards-analysis/archive/master.zip)

## Project Motivation

Once every few days, Starbucks sends out an offer to users of the Starbucks rewards mobile app. An offer can be merely an advertisement for a drink or an actual offer such as a discount or a buy one get one free.

Using the datasets our objective is combining these datasets after cleansing and use this information to determine the best offer reward for each demographic group and deterimne users that does not need an offer to make a purchase so using CRISP-DM we can state multiple statments that can help with the requirments which needed to be studied

* Characteristics of users that view offers and there persentage.
* The contribution of advertisement in user transactions
* Responding to an offer percentage & completion of offers percentage
* Predicting whether the user will respond to an offer according to his demographic group.

## File Description

The file `Starbucks_Capstone_notebook.ipynb` is written in a Jupyter Notebook, and follows the `CRISP-DM` process.

- First we state the questions that we need to answer.
- Next we explore the data.
- Then we perform some `Data wrangling` to gain insights in order to answer our questions.
- After that we model the data using a LinearSVC model combined with a pipeline to utilize gridsearch optimization to predict whether a user will respond to a sent offer or not.
- Finally we summarize our findings.

## Data Sets

The data is contained in three files:

### portfolio.json

- id (string) - offer id
- offer_type (string) - type of offer ie BOGO, discount, informational
- difficulty (int) - minimum required spend to complete an offer
- reward (int) - reward given for completing an offer
- duration (int) - time for offer to be open, in days
- channels (list of strings)

### profile.json

- age (int) - age of the customer.
- became_member_on (int) - date when customer created an app account
- gender (str) - gender of the customer (note some entries contain 'O' for other rather than M or F)
- id (str) - customer id
- income (float) - customer's income

### transcript.json

- event (str) - record description (ie transaction, offer received, offer viewed, etc.)
- person (str) - customer id
- time (int) - time in hours since start of test. The data begins at time t=0
- value - (dict of strings) - either an offer id or transaction amount depending on the record

## Summary

Throughout the notebook we viewed how customer demographics and offer reward has an effect on their response, we identified that
13% of customers do not like to share there personal data and would like to be anonymous.we used this information to exclude them from demographic analysis.

Males customers are about 57% of total customers while females take up 41%. Age distribustion of customers has a mean of 60 years age where most of the users are within that range.but age have a slight effect on user attraction to offer rewards but we noticed that the 3$ offeres are the least attactive offers. As the age increase the amount of money spent in transaction increase.

Most of the customers annual income are bellow 80000\\$ where the majority are in the range between 50000\\$ ans 75000\\$ and fewer users as the income increase.but also as the income increase the amount of money spent in transaction increase.

75% of all the received offers were actually viewed while 71% of them are completed intentionaly, 29% are completed unintentionally.

Transactions related to advertisments have 93% reach and It was also seen that offers has influence on the total transactions or completed offers that occured by 19%, which is pretty big,Social media has a higher rate of viewing offers than any other channel.

Males is attacted to 2,3 and 5 dollar rewards while women tends to go to 10 dollars rewards and on average females spend more than males.

A model to predict a customer response towards an offer based on reward and customer demographic was built with accuracy of 87% and F1-score for those who will respond and those who won't equals to 0.65 & 0.92 respectively

## Author

### Ahmad Hesham Abdelkader

- [linkedin.com/in/ahmedhesham16/](https://www.linkedin.com/in/ahmedhesham16/)
- [github.com/ahmedhesham6](https://github.com/ahmedhesham6)

## Copyright and License

Code is released under the [MIT License](https://github.com/ahmedhesham6/starbucks-rewards-analysis/blob/master/LICENSE).
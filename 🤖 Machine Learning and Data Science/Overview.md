
## Why ML?
### "To turn data from useless to useful"  
To use machines to predict results based on incoming data. In other words, to get insights from massive amount of data so that we can make better decisions. As the accumulation of data is getting massive and massive, we give the data to machines in order to optimize and automate the process and avoid human errors.
<br/>


## Modelling
1. Problem definition : What probles are we trying to solve?
2. Data : What data do we have?
3. Evaluation : What defines success?
4. Features : What features should we model?
5. Modelling : What kind of model should we use?
6. Experiments : What have we tried/what else can we try?

#### Types of ML Problems
* Supervised learning : Using data to predict a label, when you have inputs and ouputs.
  * Classification : Binary classification, Multi-class classification
  * Regression : Trying to predict if a number would go up or down 
* Unsupervised learning : using data to predict a pattern, when you only have inputs.
  * Clustering 
  * Association 
  * Rule learning
* Transfer learning : leverages what other machine learnings have learnt in another machine learning
* Reinforcement learning : Teaching machines through rewards and punishments. 
  * Skill acquisition
  * Real time learning
<br/>

#### Types of Data
* Structured data : can be organised in tabular format and data in the same column has the same type
* Unstructured data : typically come in varying formats like images, audios, videos, natural language text
<br/>

* Static data : data that doesn't change over time. e.g.) CSV(Comma Seperated Values) data
* Streaming data : data that changes constantly over time. e.g.) a stock price
##### +) NoSQL : Not Only SQL, Non-relational DataBase
NoSQL is used to store huge amounts of unstructured data in a different format than relational database.
###### Types of NoSQL Database 
* Document databases
* Key-value databases
* Wide-column stores
* Graph databases
[Reference](https://www.mongodb.com/nosql-explained)

#### Features in Data
Feature variables(x) are the data used to predict the label or pattern, which is called a target variable(y).  
* Numerical features
* Categorical features
* Derived features : a new feature discovered in feature engineering, the process to derive a new feature from existing ones 

#### Spliting Data : The 3 Sets
* Training set : the data to choose and train the model on / 70-80% of the entire data
* Validation set : the data to tune the model on / 10-15% of the entire data
* Test set : the data to test and compare models on / 10-15% of the entire data  
Keep the sets of date separate at all time!

#### Testing a model
* Balanced : when the result is in goldilocks zone
* Overfitting : Great performance on training data but poor performance on test data, or better performance on test data than training data. The model doesn't generalise well.
* Underfitting : Poor performance on training data. The model hasn't learned properly.

<br/><br/>

## Useful Materials
https://www.elementsofai.com/  
https://teachablemachine.withgoogle.com/



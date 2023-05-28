# customers_sales

Exercise with goal to predict target variable as best as possible.

Dataset contains data about customers (each record represents a customer). 
All the variables contains info about what type of business this customer do and how looks his web position.
Target variable is expected sales to that customer and goal is to predict how customer with given characteristics can impact sales of a company.

As this data is without any particular context this is not necessarily the best way to answear business problems (e.g. from business perspective we don't need to identify mediocre customers - we want to identify outliers, best ones).

To answear the given problem I just performed an EDA to quickly see relationships between variables and their distrubutions.
Then I just used 2 most common and in most cases best algorithms - XGBoost and LightGBM to model target variable. 
Considering that dataset is not that big, probably I could try to use more simple algorithm, but because there was majority of discrete variables I decided to only include these.

As the dataset had a lot of discrete variables and the categories between variables were not very different I decided to perform K-Means clustering on those high dimensional variables to simplify them. This improved model performance, but not significantly. 

In the end LightGBM happen to generalize a bit better - but this is not particularly correct as this model just "misses" a bit less at outliers which probably should be excluded if we decide that our goal is to predict as best as possbiel majority of the population. While XGBoost is a bit better at most of the dataset and just error of prediction is higher at outliers - that means that XGBoost probably understood better the problem and ignored those outliers during the training.

Of course this is just very simple answear to the problem and there is a lot of room for improvment.

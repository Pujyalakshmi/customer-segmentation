# customer-segmentation
CW Hackathon

A Documentation on Customer Segmentation

What is Customer Segmentation?
Customer Segmentation is the subdivision of a market into discrete customer groups that share similar characteristics. Customer Segmentation can be a powerful means to identify unsatisfied customer needs. Using the above data companies can then outperform the competition by developing uniquely appealing products and services.

The most common ways in which businesses segment their customer base are:
•	Demographic information, such as gender, age, familial and marital status, income, education, and occupation.

•	Geographical information, which differs depending on the scope of the company. For localized businesses, this info might pertain to specific towns or counties. For larger companies, it might mean a customer’s city, state, or even country of residence.

•	Psychographics, such as social class, lifestyle, and personality traits.

•	Behavioral data, such as spending and consumption habits, product/service usage, and desired benefits.

Advantages of Customer Segmentation

•	Determine appropriate product pricing.

•	Develop customized marketing campaigns.

•	Design an optimal distribution strategy.

•	Choose specific product features for deployment.

•	Prioritize new product development efforts. 
 
The Challenge
 
You are owing a supermarket mall and through membership cards, you have some basic data about your customers like Customer ID, age, gender, annual income and spending score. You want to understand the customers like who are the target customers so that the sense can be given to marketing team and plan the strategy accordingly.
 
Data
 
This project is a part of the Mall Customer Segmentation Data competition held on Kaggle.
The dataset can be downloaded from the kaggle website.
 


Environment and tools
 
1.	scikit-learn
2.	seaborn
3.	numpy
4.	pandas
5.	matplotlib


K Means Clustering Algorithm
 
1.	Specify number of clusters K.
2.	Initialize centroids by first shuffling the dataset and then randomly selecting K data points for the centroids without replacement.
3.	Keep iterating until there is no change to the centroids. i.e assignment of data points to clusters isn’t changing.

      ![k means](https://user-images.githubusercontent.com/65363515/101751340-2b6f1c80-3af6-11eb-812c-ae847a0efe4a.png)
  K Means Clustering
        
We started with loading all the libraries and dependencies. The columns in the dataset are customer id, gender, age, income and spending score.

 ![1](https://user-images.githubusercontent.com/65363515/101751915-e13a6b00-3af6-11eb-894e-6dc328510081.png)

 We dropped the id column as that does not seem relevant to the context. Also, we plotted the age frequency of customers.

Graph:

 ![2](https://user-images.githubusercontent.com/65363515/101751920-e26b9800-3af6-11eb-96be-c9bc6b1f07f8.png)


(This thing is perfomed in jupyter notebook. Code for same is attached below)

data.drop(["CustomerID"], axis = 1, inplace=True)
plt.figure(figsize=(10,6))
plt.title("Ages Frequency")
sns.axes_style("dark")
sns.violinplot(y=data["Age"])
plt.show()                                                             
 

Next we made a box plot of spending score and annual income to better visualize the distribution range. The range of spending score is clearly more than the annual income range.

Box Plot:

 ![3](https://user-images.githubusercontent.com/65363515/101751932-e5ff1f00-3af6-11eb-834a-9976147741db.png)

We made a bar plot to check the distribution of male and female population in the dataset. The female population clearly outweighs the male counterpart.

 Bar Plot:
 
 ![4](https://user-images.githubusercontent.com/65363515/101751933-e7c8e280-3af6-11eb-8989-1902e18afc73.png)


Next, we made a bar plot to check the distribution of number of customers in each age group. Clearly the 26–35 age group outweighs every other age group.

Bar Plot:

![5](https://user-images.githubusercontent.com/65363515/101751941-e8fa0f80-3af6-11eb-96cd-db0d5ea26a02.png)
 

We continued with making a bar plot to visualize the number of customers according to their spending scores. The majority of the customers have spending score in the range 41–60.

 ![6](https://user-images.githubusercontent.com/65363515/101751945-ea2b3c80-3af6-11eb-98ef-fc54342906d1.png)

Also, we made a bar plot to visualize the number of customers according to their annual income. The majority of the customers have annual income in the range 60000 and 90000.

![7](https://user-images.githubusercontent.com/65363515/101751948-eb5c6980-3af6-11eb-98d8-d530eeb65f12.png)


Next, we plotted Within Cluster Sum Of Squares (WCSS) against the number of clusters (K Value) to figure out the optimal number of clusters value. WCSS measures sum of distances of observations from their cluster centroids which is given by the below formula.

 ![8](https://user-images.githubusercontent.com/65363515/101751961-ee575a00-3af6-11eb-9d74-b25009182c9b.png)

where Yi is centroid for observation Xi. The main goal is to maximize number of clusters and in limiting case each data point becomes its own cluster centroid.

   ![9](https://user-images.githubusercontent.com/65363515/101751965-ef888700-3af6-11eb-9ad5-e965d876d745.png)
 
The Elbow Method
 
Calculate the Within Cluster Sum of Squared Errors (WSS) for different values of k, and choose the k for which WSS first starts to diminish. In the plot of WSS-versus k, this is visible as an elbow.
The optimal K value is found to be 5 using the elbow method.
Finally, we made a 3D plot to visualize the spending score of the customers with their annual income. The data points are separated into 5 classes which are represented in different colours as shown in the 3D plot.
 
Results
 
   ![10](https://user-images.githubusercontent.com/65363515/101751971-f1524a80-3af6-11eb-8637-a2bbb7418dbf.png)
 
 
Conclusions
 
K means clustering is one of the most popular clustering algorithms and usually the first thing practitioners apply when solving clustering tasks to get an idea of the structure of the dataset. The goal of K means is to group data points into distinct non-overlapping subgroups. One of the major application, of K means clustering is segmentation of customers to get a better understanding of them which in turn could be used to increase the revenue of the company.

      
 







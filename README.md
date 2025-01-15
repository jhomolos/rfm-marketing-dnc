# **Challenge - Creating a RFM Metrics analysis model for marketing strategies by using a Machine Learning clustering algorithm**

**Disclaimer:** This project was a challenge carried out at the DNC School as a prerequisite for completing the Data Science Degree.

**Context**

An e-commerce company is trying to better understand the behavior of its customers in order to personalize its marketing campaigns. To do this, the company has made available a csv database containing data on customers, products and store transactions carried out between 2010 and 2011. The data provided contains purchase transaction information from an e-commerce store in 38 countries and territories, with more than 4,000 unique customers and more than 540,000 transactions.

Based on this data, customers will be grouped into clusters based on their purchasing behavior using the K-Means algorithm. This will make it possible to identify patterns and characteristics in common between customers, such as:

    *Customers who buy the same products;
    *Customers who make the same number of purchases;
    *Customers who spend more money on their purchases.

From these clusters, insights should be generated so that the company can better segment its customer base and personalize its marketing campaigns, targeting promotions and offers to customers based on their purchasing behavior.

## **About the data**

The data is also available at https://www.kaggle.com/datasets/carrie1/ecommerce-data


### **Variables**

**InvoiceNo:** Transaction ID;

**StockCode**: Product stock code;

**Description**: Product description;

**Quantity**: Quantity of products per transaction;

**InvoiceDate**: Date of transaction;

**UnitPrice**: Unit price of the product;

**CustomerID**: Customer ID;

**Country**: of origin of the transaction.


## **Objectives**

* Develop a clustering model capable of grouping customers according to their purchasing behavior, taking the RFM into account.
* Analyze the clusters obtained to identify the customer profile, such as patterns and characteristics in common to determine their purchasing behavior.
* Use graphs and visualizations to aid analysis.
* Document each stage, justifying the choices made and reporting the insights gained, as well as recommendations for future action, so that the company can put them into practice.

## **Development**

The CRISP-DM methodology was used as the basis for this case, going through the stages of Business Understanding, Data Understanding, Data Preparation and Modelling.
Initially, an analysis of the available data was carried out, using grouping, descriptive/statistical analysis and also graphics, with a view to better approaching the problem and identifying possible problems in the data. In the data preparation stage, null values, duplicated ones, inconsistencies, outliers and type changes were dealt with, where applicable

The RFM analysis, which stands for Recency, Frequency, and Monetary value, is a technique that helps identifying the most valuable customers by studying their behavior and creating an assertive marketing strategy. Recency means how recently a customer has made a purchase, frequency indicates how often a customer makes a purchase and Monetary Value   points out how much a customer spends. Features that do not contribute to the RFM analysis were deleted and the remaning ones were used for computing a new dataset containing the RFM analysis for each client. Next, the RFM metrics were normalized using the PowerTransformer function. 

The modeling was carried out using the K-Means algorithm. To apply K-Means, we need to estimate an optimum number of clusters (k), since it is an unsupervised algorithm, and for this we have the Silhouette Score metric, which returned k = 5. Thus, from the centroids we can classify each cluster, and consequently identify the main patterns among the customers contained in them. So we have:

*    **Cluster 0:** customers with high frequency, medium ticket and low recency, i.e. they are always buying;
*    **Cluster 1:** customers with high recency, very low frequency and low ticket, probably churn customers;
*    **Cluster 2:** high value customers, i.e. high average ticket, with little recency. These are customers who buy large sums of money, but sporadically;
*    **Cluster 3:** customers with a very low average ticket, with some frequency and low recency. These are occasional customers, who have recently bought products of very low value; and
*    **Cluster 4:** customers with a medium ticket, extremely low frequency and low recency, indicating that they are customers who have only recently made one purchase or another. They are probably new customers.

## **Interpretation of the Results Obtained**
Based on the results obtained, the best marketing strategies were developed for each of the niches (clusters) identified.

**Cluster 0**

Cluster 0 customers tend to be quite frequent, make purchases of a medium value and have only been buying for a short time. Although they don't have a high monetary value, the high frequency with which they buy makes these customers compensate for this deficiency and make them strategic. A marketing strategy based on recommendation systems would also be interesting, so that customers continue to make new purchases. In recommendation systems, we could start suggesting higher-value items mixed with items with similar prices to those they already buy, in order to increase their average ticket. Allied to this, a follow-up system could be a fundamental strategy for understanding their needs, although it would increase the e-commerce company's costs.

**Cluster 1**

They are churn customers. As they have little history, little is known about their behavior, so that a strategy can be devised to attract them again. It would be up to the stakeholders to analyze whether it's worth trying to convert this churn customer, because as well as having a low ticket, it would represent an increase in the company's operating costs. It's probably not worth investing in attracting this customer segment.

**Cluster 2**

Customers in this cluster are valuable to the company. Although they are not as frequent, the high value of their average ticket compensates for the period without purchases. Like the customers in cluster 0, this is also a strategic and valuable customer. Therefore, the e-commerce company must also make efforts to retain and consolidate them, as well as adopting marketing strategies to get them to buy more often. It is necessary to know their profile, as they may be a legal entity that makes purchases in order to replenish its physical stock, or individual customers who focus on high value-added items, and for these reasons go a considerable time without making new purchases.

**Cluster 3**

They are ordinary customers. They don't bring in significant returns either in terms of the frequency of their purchases or the value of their average ticket. Their average ticket is the lowest of all the segments. For them, it would be worth analyzing whether it is worth adopting a marketing strategy due to the costs involved. Perhaps a more simplified marketing strategy that wouldn't cost the e-commerce company too much, such as sending them electronic messages with recommendations based on their history, launches, best-selling items and low costs.

**Cluster 4**

They are new customers. Little is known about their behavior, so more personalized recommendation systems would be ineffective. It would then be up to the e-commerce company to build customer loyalty through discount vouchers, a gift or promotion,   offering items on the upward trend and launches, as well as a marketing campaign aimed at strengthening the company's branding. A well-executed after-sales service following their first purchase could also help build loyalty. Although their ticket is average, they may be able to purchase higher value items in the future or return to make new purchases if they gain confidence in the e-commerce company. So, together with this segment, the marketing department should coordinate and devise strategies to strengthen the brand with the customer and make the customer gain confidence.

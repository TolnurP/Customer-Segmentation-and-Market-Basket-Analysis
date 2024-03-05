# Customer-Segmentation-and-Market-Basket-Analysis
## Introduction
This project aims to identify trends in purchasing behavior through customer segmentation and market basket analysis. Utilizing the Online Retail dataset from a UK-based non-store online retailer, the analysis covers transactions recorded between December 1, 2010, and December 9, 2011. Our objectives are to enhance marketing strategies and increase revenue by understanding customer behaviors and product relationships.

## Installation and Setup
Before running the analysis, ensure you have the necessary Python environment and packages installed. You can install the required packages using the following command:

!conda install -y orange3 numpy pandas scikit-learn matplotlib seaborn 

## Environment Setup
It is recommended to use a virtual environment for this project to manage dependencies effectively. You can create and activate a virtual environment using:

python -m venv myenv source myenv/bin/activate # On Windows use `myenv\Scripts\activate` 

## Dependencies
•	Python 3.8+
•	pandas
•	numpy
•	scikit-learn
•	matplotlib
•	seaborn
•	Orange3 (optional for additional data visualization and analysis)

Ensure all dependencies are installed using pip:

pip install numpy pandas scikit-learn matplotlib seaborn Orange3

## Usage
The project is structured as follows:

### Data Preprocessing:
In the preprocessing phase, the code aims to clean and prepare the dataset for further analysis. It starts by importing necessary libraries and configuring the environment to suppress unnecessary warnings. The data is loaded from an online_retail.csv file into a DataFrame. Key steps include:

**1.	Data Inspection and Cleaning:**

•	Removing records without customer IDs.

•	Excluding transactions with negative quantities (returns) or zero unit prices, as they do not contribute to typical purchasing behavior analysis.

•	Addressing inconsistencies in product descriptions and ensuring data quality.

**2.	Data Transformation:**

•	Resolving multiple descriptions for the same stock code.

•	Aggregating transactional data to a suitable format for analysis, including the correction of invoice dates and calculation of total purchase amounts.

**3.	Visualization:**

•	Initial data exploration through various visualizations, such as sales by country and internal market analysis, to understand the distribution and trends within the data.

#### RFM Analysis:

RFM (Recency, Frequency, Monetary value) analysis involves categorizing customers based on their transaction history to understand their purchasing behavior:

**1.	Recency:**

Calculation of the number of days since each customer's last purchase. The data is then plotted and analyzed to understand the distribution and identify any outliers.

**2.	Frequency:**

Determination of how often each customer makes purchases within a given period.

**3.	Monetary Value:**

Calculation of the total amount spent by each customer.

The variables derived from RFM analysis are then used to segment customers, often involving logarithmic transformations to normalize the data distribution.

#### Customer Segmentation:

This phase involves applying K-Means clustering to segment the customers based on their RFM metrics:

**1.	Standardization:**

Normalizing the RFM variables to ensure equal weighting during the clustering process.

**2.	Clustering:**

Using the K-Means algorithm to cluster customers into groups based on their RFM characteristics. The Elbow method and silhouette analysis are employed to determine the optimal number of clusters.

**3.	Analysis and Visualization:** 

Examining the characteristics of each cluster and visualizing their differences to understand distinct behavioral groups.

#### Market Basket Analysis:

Market Basket Analysis is performed using the Apriori algorithm to find frequent itemsets and derive association rules among products:

**1.	Transaction Encoding:**

Transforming the dataset into a format suitable for market basket analysis, typically a list of transactions where each transaction contains items that were purchased together.

**2.	Rule Generation:** 

Identifying frequent itemsets and generating association rules with confidence and support metrics.

**3.	Analysis:** 

Interpreting the rules to uncover patterns, such as which items are often purchased together, which can inform cross-selling strategies.

## Findings
Through our Customer Segmentation and Market Basket Analysis, we have discovered distinct clusters within our market, enabling targeted marketing campaigns and strategies to prevent customer churning. Key insights include:
1.	Customer Segmentation: By performing RFM analysis, we identified various customer groups with unique purchasing behaviors. This segmentation allowed us to tailor our marketing efforts more effectively, despite the lack of extensive demographic information.
2.	Market Basket Analysis: Our application of the Apriori algorithm unveiled significant rules regarding product placements, highlighting combinations of items that frequently co-occur in transactions. This has paved the way for optimizing our product placement and promotional strategies to boost sales.
3.	Seasonal Impacts: Analysis revealed that sales surged in November, likely influenced by events such as Thanksgiving. This highlights the importance of understanding seasonal trends in consumer behavior.
4.	Product Insights: Specific products, such as 'JUMBO BAG RED RETROSPOT' and 'LUNCH BAG VINTAGE DOILY', were identified as significant contributors to cross-selling opportunities, suggesting that targeted promotions involving these items could lead to increased sales.

## Evaluation
Reflecting on the outcomes of our analyses:
1.	Segment Analysis: We've reviewed each customer segment's characteristics and purchasing behaviors, identifying targeted strategies for engagement. This review has proven essential in understanding how different customer groups contribute to overall sales and how we can better serve their needs.
2.	Rule Evaluation: The association rules generated through market basket analysis were critically evaluated for their effectiveness and relevance. We determined that while some rules provided clear paths to improved product placement and promotional activities, others required further investigation to ensure applicability across different market segments.
3.	Strategic Recommendations: Based on our findings, we recommend the following strategic actions:
•	Tailor marketing messages and promotions to the specific needs and behaviors of each customer segment.
•	Prioritize product placement and inventory stocking based on insights gained from market basket analysis, focusing on high-confidence item pairs.
•	Leverage seasonal trends to anticipate and meet customer demand, thereby maximizing sales potential during peak periods.
By following these strategies and continuously collecting and analyzing additional demographic and transactional data, we can further refine our marketing approaches and enhance our overall sales performance.

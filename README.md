# Clustering-books-based-on-annual-sales
'Portenghal' is a publisher of children's books in Iran. They were looking to find specific patterns of behavior for their titles over a course of 5 years. I clustered Porteghal titles based on sales performance in order to determine whether there is a general “sales behavior” that can be utilized for automated price recommendation, determining the size of print orders, etc. 
## Project Brief, Operation and Results:

### Objective:
'Portenghal' is a publisher of children's books in Iran. They were looking to find specific patterns of behavior for their titles over a course of 5 years. I clustered Porteghal titles based on sales performance in order to determine whether there is a general “sales behavior” that can be utilized for automated price recommendation, determining the size of print orders, etc. 

### Description of data:
Data consists of sales volumes per year over a course of 5 years when the brand was first conceived.

### Data Wrangling and Methodology:
An additional column calculating the sum of books sold were added prior to initiating the analysis. The titles were sorted in a descending order based on total volumes sold. Primary observations include:

- “Purple Gummies” is a best seller with total sales of 75448 over 5 years. Statistically speaking, this book is an outlier and was excluded from the analysis in order to better reflect statistical redundancies within data.
- Titles which were not released or had not completed a complete sales year (Year 0, 1), were dropped as well in order to eliminate their impact on weighted average and correlation analysis.

The total sales volume was used to label titles according to performance. These labels were NOT used in clustering the books based on their annual performance figures. Clustering was done in an unsupervised manner and the labels were later used to determine how each cluster performed.

- Very Strong: Titles where total sales surpasses 80% of maximum sales
- Strong: Titles where total sales are between 20% and 80% of maximum sales
- Moderate: Titles where sales are more than 1000 but less than 20% of maximum sales
- Weak: Title were sales were less than 1000.

### Exploratory Data Analysis over Results:
- Number of books: 672
- Average market lifespan of books: 2.85
- Minimum number of books sold for a title: 77
- Maximum number of books sold for a title: 38628
- Average sales per title: 4007

### Analysis of Correlation:
- There is a very strong correlation between the number of books sold in the second and third years and the total volumes sold for a title. (Over 90%) i.e.: The expected total volume sold for a book could potentially be estimated using sales number in the second and third years as predictive features.
- There is a very strong correlation between the number of books sold in the third and fourth years.
- There is a very strong correlation between the number of books sold in the third and fourth years. Predicting a pattern for subsequent sales in 3rd and 4th years may also be possible.

### Dimension reduction:
The elbow method was used to determine the optimal number of clusters which was 3. Each title had 5 distinctive dimensions (sales in Year 1, Year 2, Year 3, Year 4, Year 5) The derived correlations were used for a principle component analysis. The titles were clustered into 3 distinctive categories as follows:

- Cluster 0: Consisting of 67 strong titles and 85 moderately performing titles. Maximum number of total sales in this cluster is 14947. A majority of titles clear 6000 in sales in their lifespan.
- Cluster 1: Consisting of 393 moderately performing titles and 103 titles that are weak.  Maximum number of sales in this cluster is 5168.
- Cluster 2:  Consisting of 1 very strong title and 24 strong title. The books in this category exceed 30,000 in sales over 5 years and need to be cherished further.

Data Transformation Excellence:  

This project focuses on the cleaning and formatting of flat file data sources using a Jupyter Notebook environment. It incorporates Python libraries such as pandas, numpy, and matplotlib to manipulate data and possibly prepare it for further analysis or visualization, indicating an emphasis on data preprocessing and exploratory data analysis as foundational steps in a larger data science or analytics project.

Within the warranty business, the process of claims is approaching real time acceptance and denial. The certificate to replace a product, service a product and pay any associated costs with the claim needs to happen within a set time frame according to contract terms. Usually within 72 hours. An example within this project case with appliances would be to determine if the product is serviceable, start the process to get a tech out to the house.  If determined to be a total loss, send certificate for full replacement and any associated costs with that replacement such as food loss. I began with EDA on my data sets, determining if I have sufficient volume with 3 years of sales and claims historical.  I then calculated the ultimate loss ratio to determine if the premiums outweigh the loss projections. With this information I then conducted a correlation exercise to determine what data point has the most impact on the ultimate loss ratio. These steps lead to the regression analysis on how the products will perform in the future and whether the business model is sustainable.

The earnings pattern of the warranties sold should more than cover the cost to service the product over the life of the warranty. My approach addressed many aspects of what determines to be a good profit margin (15% or greater) and an ultimate loss ratio of 73%.  I can not say it will be fully addressed as there may be factors outside of my approach that I can address in future project work. When complete, a recommendation can be given as to the areas that need to be addressed to improve the products performance within the pricing model, claims costs and cost sharing.

+------------------+----------------------+-------------+------------------------+-----------------+---------------------+
|     Product      | Net Adjusted Premium | Paid claims | Future Claim Liability | Ulitmate Losses | Ultimate Loss Ratio |
+------------------+----------------------+-------------+------------------------+-----------------+---------------------+
|  Refridgerators  |     $13,027,882      |  $1,025,254 |      $11,777,503       |   $12,802,756   |        98.3%        |
|     Washers      |      $6,552,717      |   $463,709  |       $4,942,869       |    $5,406,578   |        82.5%        |
| Other Appliances |     $14,911,779      |   $836,660  |       $9,090,615       |    $9,927,275   |        66.7%        |
|    Television    |       $495,786       |   $70,009   |        $335,904        |     $405,912    |        81.9%        |
|      TOTAL       |     $34,988,163      |  $2,395,632 |      $26,146,890       |   $28,542,521   |        81.6%        |
+------------------+----------------------+-------------+------------------------+-----------------+---------------------+

We can see here from the summary table above that the Ultimate Loss Ratio is above the target 73% for the book of business. The formula = Ultimate Losses/Net Adjusted Premium = Ultimate Loss Ratio.

There are several further investigations to determine next steps but we can conclude:  

1. Refrigerators are number one in all categories:  total premium sold, total claims and loss ratio. Followed by washers, number 2 in sales and number 3 in loss ratio. These 2 products make up more than 50%      of the top 15 product groups in terms of number sold, premium collected and losses incurred.   
2. Whirlpool and Frigidaire are the lowest performing manufacturers in these product groups.   
3. Bray & Scarff followed by Good Deals are lowest performing dealers in the top 15.   
4. Sales and claims concentration fall in 2 states, CA followed by FL.   
5. The product retail price correlates to the loss amount incurred, meaning the higher the price of the item, the higher the loss claim amount is. 

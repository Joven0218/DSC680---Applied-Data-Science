Warranty Analytics

Introduction

I currently work for a holding company with many subsidiaries. My functions include finance manager, data warehousing and management, risk analysis, and claims reserve projections on ultimate loss ratios. 
Claims are the leading expense on an insuring business's profit statement outside of salaries and related costs. Much emphasis is placed on predicting how a product will perform, evaluating the reasonableness 
of the warranty cost, and claims experience to present loss reserves.

The subsidiary focused on in this project is a warranty group specializing in servicing extended warranties on appliances (refrigerators, washers, dryers, stoves, small home appliances), TVs, and other electronics (audio equipment, home wine coolers, portable air conditioners, mobile phones). These products can have different warranty periods from 12 months to 5 years. The reason for choosing this subsidiary is due to the fact that their operating income has fallen in the past couple of years. The assumption is that this is due to an increase in claims experience since bringing on a large client. 
This particular buying group (many dealers under the same contract) product mix consists of 99% of refrigerators, washers, TVs, and small home appliances.

Data

Data Set 1: Sales
Source: Internal system of record for warranty group
This data set contains all sales information for the last 5 years, including contract number, product sold, manufacturer, dealer name, warranty terms, sale date, warranty costs, and retail costs.

Data Set 2: Claims
Source: Internal system of record for warranty group
This data set contains all claims information for the last 5 years, including contract number, loss date, payment date, total claim amount, parts amount, labor amount, and servicing company.

Data Set 3: Dealers
Source: Internal system of record for warranty group
This data set contains all dealer information for the largest buying group within the warranty companies' book of business, including dealer location and demographics.
Problem Statement

The main question addressed is: How can we make dealers and products more profitable?

    Can a predictive model help project claims assumptions using historical data and trends?
    Has there been an increase in claims volume, or a decrease?
    Are there regional concentrations of dealers that are performing under contract terms?
    Can we pinpoint ill-performing dealers with the model?
    Are the claims increasing or decreasing in a certain product group?
    Are the claims increasing or decreasing in relation to a certain product and manufacturer?
    Is there sufficient reserves for future claims?
    Are the warranty products priced correctly?

Approach

Within the warranty business, the process of claims is approaching real-time acceptance and denial. The certificate to replace a product, service a product, and pay any associated costs with the claim needs to happen within a set time frame according to contract terms, usually within 72 hours. An example within this project case with appliances would be to determine if the product is serviceable, start the process to get a tech out to the house. If determined to be a total loss, send a certificate for full replacement and any associated costs with that replacement such as food loss.

I began with EDA on my data sets, determining if I have sufficient volume with 5 years of sales and claims historical data. I then calculated the ultimate loss ratio to determine if the premiums outweigh the loss projections. With this information, I conducted a correlation exercise to determine what data point has the most impact on the ultimate loss ratio. These steps led to the regression analysis on how the products will perform in the future and whether the business model is sustainable.

Implications
Product	Net Adjusted Premium	Paid Losses	Future Claim Liability	Ultimate Losses	Ultimate Loss Ratio
Refrigerators	$13,027,882	$1,025,254	$11,777,503	$12,802,756	98.3%
Washers	$6,552,717	$463,709	$4,942,869	$5,406,578	82.5%
Other Appliances	$14,911,779	$836,660	$9,090,615	$9,927,275	66.7%
Television	$495,786	$70,009	$335,904	$405,912	81.9%
Total	$34,988,163	$2,395,632	$26,146,890	$28,542,521	81.6%

We can see from the summary table above that the Ultimate Loss Ratio is above the target 73% for the book of business. The formula = Ultimate Losses/Net Adjusted Premium = Ultimate Loss Ratio.

Several further investigations are needed to determine next steps, but we can conclude:

    Refrigerators are number one in all categories: total premium sold, total claims, and loss ratio. Followed by washers, number 2 in sales and number 3 in loss ratio. These 2 products make up more than 50% of the top 15 product groups in terms of number sold, premium collected, and losses incurred.
    Whirlpool and Frigidaire are the lowest-performing manufacturers in these product groups.
    Bray & Scarff followed by Good Deals are the lowest-performing dealers in the top 15.
    Sales and claims concentration fall in 2 states, CA followed by FL.
    The product retail price correlates to the loss amount incurred, meaning the higher the price of the item, the higher the loss claim amount is.

Limitations

There were a few limitations on how the overall operating income performance is scored. The largest being, I did not have access to the overhead expenses on servicing these dealers and products. The assumption is that as long as the Ultimate Loss Ratio remains at or below 73%, the company will be profitable. This is a big assumption as salaries and related is the second largest expense for this business model outside of losses.
Concluding Remarks

After reviewing all the data and performing the analysis above, the buying group in question is performing below the contractual expectation. The next steps will be to take a deeper dive into the lowest-performing dealers and their product mix to either drop coverage on certain manufacturers' products or instill loss sharing within the contract per dealer. If their ultimate loss ratio goes above a certain threshold, such as 73%, they will share the cost of those claims. We will also review the pricing models to ensure the warranty premium is adjusting with current inflation models.

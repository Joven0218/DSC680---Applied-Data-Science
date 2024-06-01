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

Final Project - Step 3
Introduction

I currently work for a holding company with many subsidiaries. My functions include finance manager, data warehousing and management, risk analysis, and claims reserve projections on ultimate loss ratios. Claims are the leading expense on an insuring business's profit statement outside of salaries and related costs. Much emphasis is placed on predicting how a product will perform, evaluating the reasonableness of the warranty cost, and claims experience to present loss reserves.

The subsidiary focused on in this project is a warranty group specializing in servicing extended warranties on appliances (refrigerators, washers, dryers, stoves, small home appliances), TVs, and other electronics (audio equipment, home wine coolers, portable air conditioners, mobile phones). These products can have different warranty periods from 12 months to 5 years. The reason for choosing this subsidiary is due to the fact that their operating income has fallen in the past couple of years. The assumption is that this is due to an increase in claims experience since bringing on a large client. This particular buying group (many dealers under the same contract) product mix consists of 99% of refrigerators, washers, TVs, and small home appliances.
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
Analysis

All tables show the top 15 in each group.
Total Contract Warranty Sales by Product Description

r

df_sales <- df_sales_original %>%
  separate(DealerNumber, into = c("Dealer Number", "Dealer Letter"), sep = " ") %>%
  group_by(ProductDescription) %>%
  summarize(`ContractCostAmount` = sum(`ContractCostAmount`)) %>%
  arrange(desc(`ContractCostAmount`))

knitr::kable(head(df_sales, 15), caption = "Total Sales by Product")

Total Claims Incurred by Product Description

r

df_sales <- df_sales_original %>%
  group_by(ProductDescription) %>%
  summarize(`ClaimAmount` = sum(`ClaimAmount`)) %>%
  arrange(desc(`ClaimAmount`))

knitr::kable(head(df_sales, 15), caption = "Total Claims by Product")

Total Sales and Claims by Year

Summarizing the claims and premium totals by year sold shows there has been an increase year over year. Per the claim data, most claims are incurred within years 2 and 3 of the contract term.

r

df_summary_product_description <- df_sales_original %>%
  group_by(Year) %>%
  summarise(`ClaimAmount` = sum(`ClaimAmount`), `ContractCostAmount` = sum(`ContractCostAmount`)) %>%
  arrange(desc(`Year`))

knitr::kable(df_summary_product_description, caption = "Total by Year")

Loss Ratio by Product Description

Summarizing by product description and calculating the loss ratio. The Loss Ratio indicates the likelihood of a loss happening on a product. For instance, Refrigerators have a Loss Ratio of 0.1954, indicating that a loss will happen at least 20% of the time within the first 3 years of the gross written premium. The desired gross loss ratio is around 0.15 or lower.

r

df_summary_product_description <- df_sales_original %>%
  group_by(ProductDescription) %>%
  summarise(`ContractCostAmount` = sum(`ContractCostAmount`), `ClaimAmount` = sum(`ClaimAmount`)) %>%
  mutate(LossRatio = `ClaimAmount`/`ContractCostAmount`) %>%
  arrange(desc(`ContractCostAmount`))

knitr::kable(head(df_summary_product_description, 15), caption = "Loss Ratio by Product")

Loss Ratio by Dealer

r

df_summary_product_description <- df_sales_original %>%
  group_by(DealerName) %>%
  summarise(`ClaimAmount` = sum(`ClaimAmount`), `ContractCostAmount` = sum(`ContractCostAmount`)) %>%
  mutate(LossRatio = `ClaimAmount`/`ContractCostAmount`) %>%
  arrange(desc(`ContractCostAmount`))

knitr::kable(head(df_summary_product_description,15), caption = "Total by Dealer")

Loss Ratio by Manufacturer

r

df_summary_product_description <- df_sales_original %>%
  group_by(ManufacturerDescription) %>%
  summarise(`ContractCostAmount` = sum(`ContractCostAmount`), `ClaimAmount` = sum(`ClaimAmount`)) %>%
  mutate(LossRatio = `ClaimAmount`/`ContractCostAmount`) %>%
  arrange(desc(`ContractCostAmount`))

knitr::kable(head(df_summary_product_description, 15), caption = "Loss Ratio by Manufacturer")

Loss Ratio by Model

r

df_summary_product_description <- df_sales_original %>%
  group_by(ModelNumber, ManufacturerDescription, ProductDescription) %>%
  summarise(`ContractCostAmount` = sum(`ContractCostAmount`), `ClaimAmount` = sum(`ClaimAmount`)) %>%
  mutate(LossRatio = `ClaimAmount`/`ContractCostAmount`) %>%
  arrange(desc(`ClaimAmount`))

knitr::kable(head(df_summary_product_description, 15), caption = "Loss Ratio by Model")

Totals by State

r

df_summary_product_description <- df_sales_original %>%
  group_by(StateCode) %>%
  summarise(`ClaimAmount` = sum(`ClaimAmount`), `ContractCostAmount` = sum(`ContractCostAmount`)) %>%
  mutate(LossRatio = `ClaimAmount`/`ContractCostAmount`) %>%
  arrange(desc(`ContractCostAmount`))

knitr::kable(head(df_summary_product_description, 15), caption = "Totals by State")

Visualization of Premium Totals by State

r

plot_usmap(data = dat, values = "Premium", color = "black") +
  scale_fill_continuous(low = "white", high = "green", name = "Premium Totals in Thousands", label = scales::comma) +
  theme(legend.position = "right")

Visualization of Claims Totals by State

r

plot_usmap(data = dat, values = "Premium", color = "black") +
  scale_fill_continuous(low = "white", high = "red", name = "Claims Totals in Thousands", label = scales::comma) +
  theme(legend.position = "right")

Linear Regression Model for Loss Ratio

r

lossratio_lm <- lm(`ClaimAmount` ~ `ContractCostAmount`, data = df_summary_product_description)
summary(lossratio_lm)

lossratio_predict <- data.frame(ClaimAmount = predict(lossratio_lm, df_summary_product_description), ContractCostAmount=df_summary_product_description$ContractCostAmount)

ggplot(data = df_summary_product_description, aes(y = `ClaimAmount`, x = `ContractCostAmount`)) + 
  geom_point(color = "blue") +
  geom_line(color = "red", data = lossratio_predict, aes(y = `ClaimAmount`, x = `ContractCostAmount`))

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

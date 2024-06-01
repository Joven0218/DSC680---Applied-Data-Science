Salary Forecasting and Predictions

Introduction
Problem Statement

The project seeks to address a critical challenge faced by our organization: forecasting salary projections related to total human capital. To achieve this, I utilized a comprehensive payroll salary dataset spanning from January 2021 to May 2023. The ultimate objective was to leverage the power of data-driven insights to enhance the accuracy and effectiveness of forecasting human capital salary expense. As our organization incurs substantial expenses in salaries and related costs, which amount to over $40M on a revenue book of $550M+, accurate salary predictions are significant. By obtaining reliable projections of future payroll expenses, we can make well-informed financial decisions, optimize resource allocation, and strategically plan.
Importance of the Problem

This endeavor holds significant implications for our company's success. Effective salary forecasting empowers us to engage in efficient budgeting and resource allocation, ensuring we remain competitive in the market. Moreover, it enables us to adopt proactive workforce planning strategies, fostering compensation equity and career development paths for our valued employees. By leveraging historical payroll data and applying advanced predictive modeling techniques, I aimed to build a robust model capable of making accurate and precise salary projections. The success of this project will empower our organization with data-driven insights, enabling us to drive optimal business outcomes, attract and retain top talent, and align our compensation practices with industry standards and market conditions.
Target Audience

The project's insights and findings will be important to key stakeholders within our organization, including those responsible for financial planning, human resources, and executive decision-making. By having access to accurate salary projections and comprehensive human capital insights, these stakeholders can make well-informed and data-driven decisions based upon our actual expense experience. Additionally, external parties, such as investors, analysts, and consultants, will find value in the project's outcomes. The ability to assess the organization's financial health and strategic direction based on reliable salary forecasting and human capital analysis will enable them to make informed investment decisions, evaluate our long-term sustainability, and offer valuable recommendations for further growth and success.
Data Source

The primary data source for this project is the Human Resources Information System (HRIS) platform provided by ADP (Automatic Data Processing). The dataset comprises comprehensive payroll salary data spanning from January 2021 to May 2023, capturing essential information such as payroll dates, amounts, employee attributes, and job characteristics. The HRIS platform ensures the data's accuracy, reliability, and compliance with data privacy regulations, making it a trustworthy and robust source for my analysis. By leveraging this extensive and well-organized dataset, I can extract meaningful insights and develop predictive models that will enhance our understanding of salary projections.

Methods/Results
Exploration of Data

During the initial phase of data exploration, I conducted a thorough examination of the dataset to gain insights into its structure and quality. Missing values were identified in some uncoded payroll entries, which were subsequently removed from the dataset due to their minimal impact on the overall data integrity. The remaining data proved to be well-organized, with each row representing a distinct employee, creating an ideal foundation for analysis.

Data Preparation

Data preparation played a pivotal role in ensuring the dataset's suitability for predictive modeling. I meticulously cleaned the dataset, removing redundant columns that contributed little to the model's predictive power. Essential categorical variables, such as Title, Job Class, Address State, and Gender, were retained, as they proved to be influential factors in salary forecasting. By optimizing the dataset, I streamlined the modeling process, leading to more accurate predictions.
Visualizations

Various exploratory visualizations were employed to gain deeper insights into the data. Box plots and bar plots were utilized to identify potential salary distribution disparities and discern the compensation hierarchy among different job classes. These visualizations revealed valuable patterns and trends, aiding in the formulation of data-driven decisions. Additionally, feature engineering techniques and a correlation matrix were applied to uncover potential correlations and dependencies within the data, enhancing our understanding of the factors influencing salaries.
Modeling

In pursuit of the most accurate predictive model, I explored three different algorithms: Linear Regression, Random Forests, and Gradient Boosting Models (specifically XGBoost). Each model was evaluated based on its performance, accuracy, and ability to handle complex patterns within the data. After comprehensive evaluation, XGBoost emerged as the optimal choice, surpassing the other models in terms of accuracy and performance. Its ability to handle intricate relationships within the data and effectively prevent overfitting made it the most suitable algorithm for our salary forecasting task.

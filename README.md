# Food Sale Predictions
## Modeling outlet sales to predict future sales based on outlet and product attributes
**Author:** Joshua Lensing
### Business Problem:
Outlet stores of various types are trying to gain an understanding of what contributes best to their sales numbers. By using attributes of the outlets and the products that they sell, they want to understand how that affects current sales and how it will be able to predict future sales. If various aspects can be improved, maybe sales can be increased as well.

The source of this dataset can be found [here](https://datahack.analyticsvidhya.com/contest/practice-problem-big-mart-sales-iii/).

Here is the data dictionary for this dataset:

| Variable Name |	Description |
|---------------|-------------|
Item_Identifier	| Unique product ID
Item_Weight |	Weight of product
Item_Fat_Content | Whether the product is low fat or regular
Item_Visibility |	The percentage of total display area of all products in a store allocated to the particular product
Item_Type |	The category to which the product belongs
Item_MRP |	Maximum Retail Price (list price) of the product
Outlet_Identifier |	Unique store ID
Outlet_Establishment_Year |	The year in which store was established
Outlet_Size |	The size of the store in terms of ground area covered
Outlet_Location_Type |The type of area in which the store is located
Outlet_Type |	Whether the outlet is a grocery store or some sort of supermarket
Item_Outlet_Sales |	Sales of the product in the particular store. This is the target variable to be predicted.

## Methods
- There were 2 columns that contained missing values: Item_Weight and Outlet_Size. For Item_Weight, I chose to fill in the missing values with the mean as the column contained floats, and the mean would not skew the overall average of the column. I chose to use mode for the Outlet_Size, as choosing the most common value in the column seemed to have the best chance at reducing error. The column contained only 3 different catergorical values, so imputing the mode was the logical choice since there were so few unique values.
- I deleted the 'Item_Identifier', 'Item_Visibility', 'Outlet_Identifier', 'Outlet_Location_Type' columns. Item_Identifier contained unique values to each row, so they were deleted. I also deleted Outlet_Identifier for the same reason, and although it was present in more than one row, it was not prevalent enough to keep it. Outlet_Location_Type did not seem necessary as we already have information on the types of outlets. And for the final column Item_Visibility, the data did not seem identify anything of importance with the data, and the values of each were very different from one another, so it was deleted as well.

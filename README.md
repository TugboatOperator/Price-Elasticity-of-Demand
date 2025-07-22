# Price Elasticity of Demand

This Analysis exercises the core idea of Price Elasticity of Demand using a UK based Retail log for one year.

## Business Objective
Identify top products that, regardless of their price, are proven to remain in demand. This particular attiribute means an item is "inelastic". As Prices goes up Demand remains more consistent, allowing these items to remain at a higher cost and increase profit. 

Identifying these products is crucial because prices can be kept consistent to increase revenue and items that are more elastic should be dynamically priced for the market.

## Methodology
To determine the Price Elasticity of Demand (PED) we use the following formula on a single product.<br><br>
$$E_d = \frac{\%\ \text{change in quantity demanded}}{\%\ \text{change in price}} = \frac{\Delta Q / Q}{\Delta P / P}
$$ 
<br>
This formula is the theoretical application of Elasticity, but for this particular analysis we take it a step further by using the Log-Log Linear Regression to model Elasticity of a product.

$$\ln(Q) = \beta_0 + \beta_1 \ln(P) + \varepsilon$$
Here $\ln(Q)$ is the log Quantitiy of all demand, $\beta_0$ is the intercept, $\beta_1$ is the coefficient for log Price, and $\varepsilon$ is the error term.
<br>
<br>
The power of Linear regression in this use case is that we can use the coefficient of price to see exactly how a 1% change affects the demand and use the Log-Log to manage non-linear relationships.
<br>
<br>
This formula was looped through for each of the top ten categories and saved in a dataframe to identify the products with the least amount of elasticity. Below are the top 5 results:

| Product  | Elasticity |
|------------|------------|
| Hot Water Bottle (Style 1)     | -0.803     |
| Hot Water Bottle (Style 2)     | -0.922     |
|Metal Lantern| -0.989     |
| Children's Playhouse      | -1.408     |
| Nesting Doll      | -1.496     |

The ten categories have been trimmed down for the exercise of inelastic products given the following criteria:

$$PED\begin{cases}
E_d = 0 & \text{Perfectly inelastic (no response to price)} \\
0 < |E_d| < 1 & \text{Inelastic (low sensitivity to price)} \\
|E_d| = 1 & \text{Unit elastic (proportional response)} \\
|E_d| > 1 & \text{Elastic (high sensitivity to price)} \\
\end{cases}$$


## Final Conclusion
As expected the products line up with the the concept of elasticity, the more an item is necessary it will be inelastic and lean towards consistent demand at higher prices (a common example is Fuel). In this case Hot water bottles which are used for warming your hands in cold environments are more inelastic because they fall closer to a necessity. While other top sellers like a Child's playhouse are elastic, therefore as price increases demand decreases. Specifically for every 1% increase in price the demand shrinks by 1.4% for a childs playouse. Alternatively, demand shrinks .8% for the hot water bottle for every 1% increase in price. <br><br>

### Business Takeaway
The first and most important takeaway is that elastic items need to be dynamically priced. A Child's playset will be a significant cost if not priced and stocked in correlation to sales trends. Second, an inelastic item like the hot water bottle can be priced consistently through much of the year. Price plays a small factor in the sales of the hot water bottle while seasonality affects it more. When this item sells out of season the price can remain non-negotiable according to this elasticity rule of thumb.

🔒 Lock in Prices for Inelastic Hot Water Bottles, and Lanterns (Optionally reduce stock in down seasons if stock comes at a cost or for perishable goods)

📈 Dynamically price Elastic Items that are top sellers like the Childrens Playhouse, and the Nesting Doll using Forecasting based on historical data.
 
# Order Brushing

[[Students] Shopee Code League - Order Brushing](https://www.kaggle.com/c/students-order-brushing-1)

## **Order Brushing Detection**

Abnormal user behaviors on e-commerce platforms can be detected in various ways. For example, if an item in a shop is a best seller but many of its orders come from the same buyer, we have reason to suspect that the seller is conducting order brushing. Order Brushing is a technique that may be employed by sellers to create fake orders in order to inflate the seller’s or a particular item’s rating, which may likely push that seller’s items up the search results on Shopee. To maintain the integrity of our online shopping experience, we consistently monitor and flag any possible cases of order brushing on Shopee.

## **Task**

1. Identify all shops that are deemed to have conducted order brushing.

2. For each shop that is identified to have conducted order brushing, identify the buyers suspected to have conducted order brushing for that shop.

For the purpose of this question, **shops are deemed to have conducted order brushing** if their **concentrate rate is greater than or equal to 3 at any instance**

```
Concentrate rate = 
Number of Orders within 1 hour / Number of Unique Buyers within 1 hour
```

For the purpose of this question, **suspicious buyers** are deemed as the **buyer that contributed the highest proportion of orders to a shop** that is deemed to have conducted order brushing.

For calculation of the **highest proportion of orders to a shop**, only include the orders that occured in instances when order brushing has been deemed to have taken place.

In the case where multiple users share the same highest proportion of orders for a specific shop, all those users are deemed to be suspicious buyers.

**Please refer to the Examples page for more specific cases of order brushing**

## **Basic Concepts**

Each orderid represents a distinct transaction on Shopee.

Each unique shopid is a distinct seller on Shopee.

Each unique userid is a distinct buyer on Shopee.

Event Time refers to the exact time that an order was placed on Shopee.

Concentrate rate is a possible measure that we use to determine whether a shop is likely to have conducted order brushing. For this question, the threshold for concentrate rate is 3. Any concentrate rate value equal to or greater than 3 is deemed to be an occurence of order brushing.

## **Submission Format**

Check each shop and determine whether it is deemed to have conducted order brushing. If a shop conducted order brushing, list the userid(s) that are identified as suspicious for the corresponding shopid.

Two columns required:

- shopid
- userid
- If a shop is not deemed to have conducted order brushing, assign the value 0Else, list the userid(s) that are identified as suspicious for the corresponding shopidIf there is more than 1 userid identified as suspicious, list all the userids separated by “&”, with the smaller numerical userid first.

[my python code](Orderbrushing.ipynb)  
[my solution](solution.csv)

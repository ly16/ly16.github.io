---
layout:     post
title:      LeetCode Stock questions template
subtitle:   UnionFind in Java and relevant questions
date:       2022-01-08
author:     Clover
header-img: img/leetcode.jpg
catalog: true
tags:
    - LeetCode

---

#### Best Time to Buy and Sell Stock
#### Best Time to Buy and Sell Stock II
#### Best Time to Buy and Sell Stock III
#### Best Time to Buy and Sell Stock IV

#### 309. Best Time to Buy and Sell Stock with Cooldown

> sell --> cooldown --> Buy --> sell
> buy = Math.max(preBuy, sellBeforeCooldown - currentPrice)
> sell = Math.max(preSell, preBuy + currentPrice)

- time = O(n)
- space = O(1)

```Java
class Solution {
    public int maxProfit(int[] prices) {
        int sell = 0;
        int buy = Integer.MIN_VALUE;
        int preSell = 0;

        for (int p : prices) {
            int prePreSell = preSell;
            preSell = sell;
            int preBuy = buy;
            buy = Math.max(preBuy, -p + prePreSell);
            sell = Math.max(preSell, preBuy + p);
        }
        return sell;
    }
}
```

#### 714. Best Time to Buy and Sell Stock with Transaction Fee

> buy --> sell --> buy
> only add transaction fee when sell out
> sell = Math.max(preSell, preBuy + currentPrice - transactionFee)
> buy = Math.max(preBuy, preSell - currentPrice)

- time = O(n)
- space = O(n)

```Java
class Solution {
    public int maxProfit(int[] prices, int fee) {
        int buy = -prices[0];
        int sell = 0;

        for (int p : prices) {
            int preBuy = buy;
            int preSell = sell;
            buy = Math.max(preBuy, preSell - p);
            sell = Math.max(preSell, preBuy + p - fee);
        }
        return sell;
    }
}
```


#### Relevant questions & reference

* https://leetcode.com/problems/best-time-to-buy-and-sell-stock-with-cooldown/
* https://leetcode.com/problems/best-time-to-buy-and-sell-stock-with-transaction-fee/

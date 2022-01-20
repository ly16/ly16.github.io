---
layout:     post
title:      LeetCode Stock questions template
subtitle:   Stock templates in Java and relevant questions
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

- time = O(n)
- space = O(1)

```java
class Solution {
    public int maxProfit(int[] prices) {
        int hold1 = Integer.MIN_VALUE, sold1 = 0, hold2 = Integer.MIN_VALUE, sold2 = 0;
        for (int p : prices) {
            hold1 = Math.max(hold1, -p);
            sold1 = Math.max(sold1, hold1 + p);
            hold2 = Math.max(hold2, sold1 - p);
            sold2 = Math.max(sold2, hold2 + p);
        }
        return Math.max(sold2);
    }
}
```

#### Best Time to Buy and Sell Stock IV

- time = O(nk)
- space = O(k)

```java
class Solution {
    public int maxProfit(int k, int[] prices) {    
        if (k >= prices.length / 2) {
            int res = 0;
            for (int i = 1; i < prices.length; i++) {
                if (prices[i] > prices[i - 1]) {
                    res += prices[i] - prices[i - 1];
                }
            }
            return res;
        }
        int[] buy = new int[k + 1], sell = new int[k + 1];
        Arrays.fill(buy, Integer.MIN_VALUE);
        for (int price : prices) {
            for (int i = 1; i <= k; i++) {
                buy[i] = Math.max(buy[i], sell[i - 1] - price);
                sell[i] = Math.max(sell[i], buy[i] + price);
            }
        }
        return sell[k];
    }
}
```

#### 309. Best Time to Buy and Sell Stock with Cooldown

```
 sell --> cooldown --> Buy --> sell 
 buy = Math.max(preBuy, sellBeforeCooldown - currentPrice) 
 sell = Math.max(preSell, preBuy + currentPrice) 
```


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

```
buy --> sell --> buy
only add transaction fee when sell out
sell = Math.max(preSell, preBuy + currentPrice - transactionFee)
buy = Math.max(preBuy, preSell - currentPrice)
```

- time = O(n)
- space = O(1)

```Java
class Solution {
    public int maxProfit(int[] prices, int fee) {
        int buy = -prices[0];
        int sell = 0;

        for (int p : prices) {
            buy = Math.max(buy, sell - p);
            sell = Math.max(sell, buy + p - fee);
        }
        return sell;
    }
}
```


#### Relevant questions & reference

* https://leetcode.com/problems/best-time-to-buy-and-sell-stock-iii/
* https://leetcode.com/problems/best-time-to-buy-and-sell-stock-iv/
* https://leetcode.com/problems/best-time-to-buy-and-sell-stock-with-cooldown/
* https://leetcode.com/problems/best-time-to-buy-and-sell-stock-with-transaction-fee/


---
layout:     post
title:      Lambda Expression
subtitle:   Sort function, Compare function
date:       2021-02-02
author:     Clover
header-img: img/leetcode.jpg
catalog: true
tags:
    - LeetCode

---
### Collections sort

> compare must return int when override
> For example, we define a new class `Book`

- Use lambda expression

```java

Collections.sort(listBooks, (b1, b2) -> (int) (b1.getPrice() - b2.getPrice()));

```

- Create new comparator for `Book` class

```java
class SortbyPrice implements Comparator<Book>
{
  public int compare(Book b1, Book b2) {
    return (int)(b1.getPrice() - b2.getPrice());
  }
}

Collections.sort(listBooks, new SortbyPrice());
```

- Use inner class of Comparator

```java

Collections.sort(listBooks, new Comparactor<>(){
  @Override
  public int compare(Book b1, Book b2) {
    return (int)(b1.getPrice() - b2.getPrice());
  }
});
```



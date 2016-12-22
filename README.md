# Refatoring Exercise

## 背景
欢迎来到镀金玫瑰团队。我们是坐落在一个大城市繁华街区的一家小旅馆，由 Allison 这位好店主来经营。除了为旅客提供住宿，我们还出售品质绝佳的商品。不幸的是，这些商品随着其销售期限的临近，品质会逐渐变差。我们拥有一套软件系统，来为我们更新这些商品的库存情况。这套系统是由一位名叫 Leeroy 的高手开发出来的，开发完成后，她就云游四方去了。你的任务是为这套系统添加新功能，使得我们能开始出售新商品。

## 库存计算系统基本功能
1. 所有的商品都有一个用整数表示的 SellIn 销售期限值，来表示这件商品必须在这个值所表示的天数之内售出，否则商品的品质就会变化。
2. 所有的商品都有一个 Quality 整数值，来表示这个商品的品质。
3. 每天下班的时候， SellIn 会固定减1， 商品品质会根据商品类型而变化。
4. 大部分普通商品的品质每天都会减1。
5. 一旦商品过了销售期限，普通商品的品质每天会减2。
6. 一件商品的品质绝不会是负数。
7. “Aged Brie” 这种“法式陈年布理干酪”的品质变化跟普通商品完全相反，它会随着时间推移而增加，其上限是50。
8. “Sulfuras” 这种商品的品质和销售期限永远不会发生改变。
9. 小镇有一个剧院，每逢剧目演出前，旅馆会销售“Backstage pass”这种商品，供粉丝们去剧院后台找明星合影。像“Aged Brie”一样，其品质随着销售期限的临近，会逐渐提升。当在销售期限前 10 天及以内时，其品质每过一天就会增2;当在销售期限前 5 天及以内时，其品质每过一天就会增3;但是当该剧目演出结束时，其品质会下降到 0。

## 待添加的功能
1. 现在有一种名叫 “Conjured” 新商品等待出售，这种魔法召唤器比普通商品的品质下降要快两倍。

## Example
```
  -------- day 0 --------
  name, sellIn, quality
  +5 Dexterity Vest, 10, 20
  Aged Brie, -1, 0
  Elixir of the Mongoose, 5, 7
  Sulfuras, 0, 80
  Sulfuras, -1, 80
  Backstage pass, 15, 20
  Backstage pass, 10, 49
  Backstage pass, 5, 49
  Conjured Mana Cake, 3, 6

  -------- day 1 --------
  name, sellIn, quality
  +5 Dexterity Vest, 9, 19
  Aged Brie, -2, 2
  Elixir of the Mongoose, 4, 6
  Sulfuras, 0, 80
  Sulfuras, -1, 80
  Backstage pass, 14, 21
  Backstage pass, 9, 50
  Backstage pass, 4, 50
  Conjured Mana Cake, 2, 5
```

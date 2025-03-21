## 什么时候想到用哈希法，当我们遇到了要快速判断一个元素是否出现集合里的时候，就要考虑哈希法。

当我们要使用集合来解决哈希问题的时候，优先使用unordered_set，因为它的查询和增删效率是最优的，如果需要集合是有序的，那么就用set，如果要求不仅有序还要有重复数据的话，那么就用multiset。

在C++中，set 和 map 分别提供以下三种数据结构，其底层实现以及优劣如下表所示：

|集合|底层实现|是否有序|数值是否可以重复|能否更改数值|查询效率|增删效率|
|---|---|---|---|---|---|---|
|std::set|红黑树|有序|否|否|O(log n)|O(log n)|
|std::multiset|红黑树|有序|是|否|O(logn)|O(logn)|
|std::unordered_set|哈希表|无序|否|否|O(1)|O(1)|

std::unordered_set底层实现为哈希表，std::set 和std::multiset 的底层实现是红黑树，红黑树是一种平衡二叉搜索树，所以key值是有序的，但key不可以修改，改动key值会导致整棵树的错乱，所以只能删除和增加。

|映射|底层实现|是否有序|数值是否可以重复|能否更改数值|查询效率|增删效率|
|---|---|---|---|---|---|---|
|std::map|红黑树|key有序|key不可重复|key不可修改|O(logn)|O(logn)|
|std::multimap|红黑树|key有序|key可重复|key不可修改|O(log n)|O(log n)|
|std::unordered_map|哈希表|key无序|key不可重复|key不可修改|O(1)|O(1)|


总结一下，**当我们遇到了要快速判断一个元素是否出现集合里的时候，就要考虑哈希法**。

但是哈希法也是**牺牲了空间换取了时间**，因为我们要使用额外的数组，set或者是map来存放数据，才能实现快速的查找。

如果在做面试题目的时候遇到需要判断一个元素是否出现过的场景也应该第一时间想到哈希法！



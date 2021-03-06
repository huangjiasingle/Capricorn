
### TOP N问题

1. 如何在海量数据中找出重复最多一个。

- 通过hash映射为小文件
- 通过hash_map统计各个小文件重读最多的并记录次数
- 对每个小文件重复最多的进行建立大根堆

2. 上亿有重数据，统计最多前N个。

- 内存存不下
  - 通过hash映射为小文件
  - 通过hash_map统计各个小文件重读最多的并记录次数
  - 对每个小文件重复最多的进行建立大根堆并重复N次取走堆顶并重建堆操作
- 内存存得下
  - 直接内存通过hash_map统计并建大根堆
  - 重复N次取走堆顶并重建堆操作

3. 海量日志数据，提取出某日访问百度次数最多的那个IP（同1）。

- 将IP % 1000映射到1000个小文件中
  - 相同IP会被映射到同一个文件
  - 不会出现累加和更大情况
- 分1000次在内存处理小文件，得到频率最大IP（使用map统计）
- 对这1000个IP建立大根堆

4. 1000w查询串统计最热门10个（同2）。

同上

5. 1G的文件，里面1行1个不超过16字节的词。内存限制1M，返回频数最高前100（同2）。

- 将单词 % 5000存入5000小文件
- 平均各文件约200K
- 对超过1M的文件继续分割直到小于200K
- 使用map统计各个词出现的频率
- 对5000词使用堆排序或归并排序

### 分布式TOP N问题

1. 分布在100台电脑的海量数据，统计前十

- 各数据只出现在一台机器中
  - 先在独立机器得到前十
    - 若可以放入内存直接堆排序
    - 若不可全放入内存：哈希分块 -> map统计 -> 归总堆排
  - 再将100台计算机的TOP10组合起来堆排序
- 同一元素可同时出现在不同机器中
  - 遍历所有数据，重新hash取模，使同一个元素只出现在单独的一台电脑中，然后采用上面方法先统计每台电脑TOP10再汇总起来

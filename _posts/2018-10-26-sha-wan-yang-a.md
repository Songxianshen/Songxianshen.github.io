---
title: 【奇奇怪怪】高性能的神奇作业
date: 2018-10-26 21:20:31
---


```python
import nltk
import jieba
import re

raw = open(r'***/xx.txt', error='ignore').read()
strtxt = re.findall("class .* {|new .*\(", raw)

for i in strtxt:
    pi = nltk.text.Text(jieba.lcut(i))
    for j in pi:
        if j == 'class':
            print("类：")
        elif j == 'new':
            print("包含函数：", end='')
        elif j == '<':
            print("函数泛型为：", end='')
        elif j != '{' and j != '(' and j != '>':
            print(j)
```
---
代码结果：<br/>
![jupter notbook](/images/DL-images/qiqiguaiguai-result.png)

# NLP_Hongloumeng
NLP

# Issue1 - pip3 install jieba

$```pip3 install jieba```, ```sudo pip3 install jieba```

-> ImportError: module 'pip' has no attribute 'main'

Try 1: ✘pip version rollback 9.0.3

```python3 -m pip install --user --upgrade pip==9.0.3```


Answer:

**python3 -m pip install jieba**


# Issue 2 - zip(*[sentence[i:] for i in range(n)])
**zip 기분**
```
>>> a = [1,2,3] #此处可迭代对象为列表
>>> b = [4,5,6]
>>> c = [4,5,6,7,8]
>>> zipped = zip(a,b)
>>> zipped
<zip object at 0x02B01B48> #返回的是一个对象
>>> list(zipped)
[(1, 4), (2, 5), (3, 6)] #使用list()函数转换为列表
>>> list(zip(a,c))
[(1, 4), (2, 5), (3, 6)]
>>> zipped = zip(a,b)
>>> list(zip(*zipped)) #解压也使用list进行转换
[(1, 2, 3), (4, 5, 6)]
```
-----
**코드 분석**
```python
generate_ngram = lambda sentence,n:zip(*[sentence[i:] for i in range(n)])
generate_ngram(['何', '我', '堂堂', '须眉', '诚不若'],2)
```
=>
```python
for i in range(2):
i = 0,sentence[0:] 
    => ['何', '我', '堂堂', '须眉', '诚不若']
i = 1,sentence[1:]
    => ['我', '堂堂', '须眉', '诚不若']

zip( ['何', '我', '堂堂', '须眉', '诚不若']  , ['我', '堂堂', '须眉', '诚不若'] )
    => 
        ('何', '我')
        ('我', '堂堂')
        ('堂堂', '须眉')
        ('须眉', '诚不若')

```

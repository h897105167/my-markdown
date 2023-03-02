# numpy

## 1. np.array

​	numpy中的类型为ndarray，一个类似list的数组，也可以是一个矩阵

### 1.1 创建一个指定的数组

```python
import numpy as np

print(np.array([[1, 2, 3], [4, 5, 6]]))

'''
array([[1, 2, 3],
       [4, 5, 6]])
'''
```



### 1.2 np.empty

​	创建一个空数组

```python
arr = np.empty([2,3])

print(arr)
>>
[[9.94013390e-312 9.94013386e-312 9.94013390e-312]
 [9.94013390e-312 9.94013390e-312 9.94013390e-312]]
```



### 1.2 np.zeros

​	创建一个全0的数组

```python
import numpy as np

print(np.zeros(2,3))  #指两行三列

'''
array([[0, 0, 0],
       [0, 0, 0]])
'''
```

### 1.3 np.ones

​	创建一个全1的数组

```python
import numpy as np

print(np.ones(2,3))

'''
array([1, 1, 1],
	  [1, 1, 1])
'''
```

### 1.4 np.arange

​	创建一个递增的数组

```python
import numpy as np

print(np.arange(3,7))

'''
array([3, 4, 5, 6])
'''
```

### 1.5 np.linspace

​	创建一个等间距分布的数列

```python
import numpy as np

print(np.linpace(0, 1, 5))

'''
array([0. , 0.25, 0.5, 0.75, 1. ])
'''
```

### 1.6 np.random.rand

1. random.rand() 生成一个随机数组，服从0~1均匀分布

```python
import numpy as np

print(np.random.rand(2,4))

'''
array([[0],
	   []])
```

2. random.randn() 生成一个随机数组，服从标准正态分布

3. random.randint(low,high=None, size=None, dtype='I')

   low:最小值

   high：最大值

   size：数组维度

   dtype：数据类型，默认为np.int64，这里可以改为

   high没有填写时，默认生成的随机数范围是[0,low)

   ```python
   arr = np.numpy.randint(1,12,size=(3,4))
   print(arr)
   
   '''
   [[ 3  2 10 10]
    [ 7  1  1  2]
    [ 5  6  6  6]]
   ```

   

### 1.7 dtype

```
np.int8/16/32/64 整型
np.unit8/16/32/64 无符号整型
np.float32/64 浮点数
bool 布尔值
str 字符串
```

### 1.8 np.astype

​	转换类型，返回值为转换后的数组，不会改变原有数组类型

```python
arr = np.array([1, 2, 3])
arr1 = arr.astype(float)
print(arr1)
print(arr)

'''
[1. 2. 3.]
[1 2 3]
'''
```

---

## 2. 数组运算

### 2.1 四则运算

​	相同规格的数组可以进行加减乘除，其结果是各个对应位置相加减乘除的数组

```python
a = np.array([[1, 2], [3, 4]])
b = np.array([[2, 4], [6, 8]])

a + b >> [[ 3  6]
          [ 9 12]]

a - b >> [[-1 -2]
          [-3 -4]]

a * b >> [[ 2  8]
          [18 32]]

a / b >> [[0.5 0.5]
          [0.5 0.5]]
```

​	当不同规格的数组进行四则运算时，会先将两个数组扩展至同一规格，再进行四则运算，称为==广播==（broadcasting）

```python
a = np.array([[1, 2, 3]])
b = np.array([[2], [4], [6]])
print(a * b)
>> [[ 2  4  6]
    [ 4  8 12]
    [ 6 12 18]]
```



### 2.2 求和

 np.sum(array) 求数组所有元素的和

```python
a = np.array([[1, 2, 3],[4, 5, 6], [7, 8, 9]])

print(np.sum(a))
>> 45
```

可以加入参数axis，axis=0代表第一个维度，此时返回一个其他维度依次求和，按该维度索引的总和的一维数组

​    axis=1代表第二个维度，以此类推

```python
a = np.array([[1, 2, 3],[4, 5, 6], [7, 8, 9]])

print(np.sum(a,axis=0))
print(np.sum(a,axis=1))
>>[12 15 18]
>>[ 6 15 24]
```



### 2.3 np.dot

作用于两个数组，当两个数组都为一维数组时（维度相同），将两个一维数组视为向量，返回内积结果

```python
a = np.array([1, 2])
b = np.array([2, 4])

print(np.dot(a, b))
>> 10
```

作用于两个多维数组时，返回的是数组相乘的结果

```python
a = np.array([[1, 2], [3, 4]])
b = np.array([[2, 4], [6, 8]])

print(np.dot(a,b))
>> [[14 20]
    [30 44]]
```

@(或者np.matmul)也可以做矩阵乘法运算，但高维数组相乘时与np.dot有差异，详情见[python中@和np.dot的区别 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/482738400)

```python
a = np.array([[1, 2], [3, 4]])
b = np.array([[2, 4], [6, 8]])

print(a @ b)
>> [[14 20]
    [30 44]]
```

### 2.4 平方根、三角函数、对数、指数运算

1. np.sqrt(array)对数组中的数依次求平方根

```python
a = np.array([[1, 2], [3, 4]])

print(np.sqrt(a))
>> [[1.         1.41421356]
    [1.73205081 2.        ]]
```



2. np.sin(array), np.cos(array) 对数组中的数依次求正弦、余弦值

   ```python
   a = np.array([[1, 2], [3, 4]])
   
   print(np.sin(a))
   >> [[ 0.84147098  0.90929743]
       [ 0.14112001 -0.7568025 ]]
   ```



3. np.log(array), np.exp(array) 返回相同规格的对应对数、指数数组

   ```python
   a = np.array([[1, 2], [3, 4]])
   
   print(np.exp(a))
   >> [[ 2.71828183  7.3890561 ]
       [20.08553692 54.59815003]]
   ```



### 2.5 最大值/最小值

1. np.min(array) np.max() 返回数组中的最大值或/最小值

```python
a = np.array([[1, 2], [3, 4]])

print(np.min(a))
>> 1
```

2. np.argmin(array) np.argmax(array) 返回数组中最小值/最大值所在的索引，但会先将数组转化为一维，再返回一维索引

   ```python
   a = np.array([[[1, 2], [0, 4]],
                 [[-1, 6], [7, 8]]])
   
   print(np.argmin(a))
   >> 4
   ```



### 2.6 平均值、中位数

1. np.mean(array) 返回数组的算术平均值

   ```python
   a = np.array([[[1, 2], [0, 4]],
                 [[-1, 6], [7, 8]]])
   
   print(np.mean(a))
   >> 3.375
   ```

   还有np.nanmean(array) 也能返回算术平均值，但会忽略数组中的NaN



2. np.median(array) 返回数据的中位数

   ```python
   a = a = np.array([[1, 2, 3],[4, 5, 6]])
   
   print(np.median(a))
   >> 3.5
   ```



### 2.7 方差、标准差

1. numpy.var(array) 返回数组的方差

   ```python
   a = np.array([[1, 2, 3],[4, 5, 6], [7, 8, 9]])
   
   print(np.var(a))
   >> 6.666666666666667
   ```

   

2. numpy.std(array) 返回数组的标准差（有偏）

   ```python
   a = np.array([[1, 2, 3],[4, 5, 6], [7, 8, 9]])
   
   print(np.std(a))
   >> 2.581988897471611
   ```

   

### 2.8 比较运算

​	使用array  > aNum ，可以获得数组中全部元素与aNum的比较结果

```python
a = np.arange(10)

print(a>3)
>> [False False False False  True  True  True  True  True  True]
```

​	

## 3. 获取数组中的元素

### 3.1 按索引获取

与list不同，按索引获取的索引为array[d0, d1,...]

```python
a = np.array([[1, 2, 3],[4, 5, 6], [7, 8, 9]])

print(a[2,2])
>> 9
```



### 3.2 按范围获取

array[范围表达式，用数组名做变量]，如a[(a > 3) & (a % 2 == 0)]

```python
a = np.arange(10)

print(a[(a > 3) & (a % 2 == 0)])
>> [4 6 8]
```

还可以使用切片，如a[0, 0:2]

```python
a = np.array([[1, 2, 3],[4, 5, 6], [7, 8, 9]])

print(a[0, 0:2])
>> [1 2]
```

或使用切片跨度，如a[0:9:2]，其中2为跨度

```python
a = np.arange(10)

print(a[0:9:2])
>> [0 2 4 6 8]


```

跨度可以为负数，表示从右往左逆向返回，但要调换索引的位置，如翻转数组a[::-1]

```python
a = np.arange(10)

print(a[9:0:-2])
>> [9 7 5 3 1]

print(a[::-1])
>> [9 8 7 6 5 4 3 2 1 0]
```



## 4. 拼接

### 4.1 np.dstack

​	按深度顺序堆叠arrays。当数组为二维数组(M,N)或1维数组(N,)时，先改变其维度为(M,N,1)和(1,N,1)，然后沿着第三根轴进行拼接。

​	(M,N,O),其中排在最前面的为新出现的维度

```python
# 一维
a = np.array([1, 2])
b = np.array([3, 4])
print(np.dstack((a,b)))

# 二维
a = np.array([[1, 1],
              [2, 2],
              [3, 3]])
b = np.array([[4, 4],
              [5, 5],
              [6, 6]])
print(np.dstack((a,b)))

# 运行结果
[[[1 3]
  [2 4]]]
  
[[[1 4]
  [1 4]]
 [[2 5]
  [2 5]]
 [[3 6]
  [3 6]]]
```

### 4.2 np.hstack

​	用于水平顺序堆叠

```python
import numpy as np

# 一维
a = np.array([1, 2])
b = np.array([3, 4])
print(np.hstack((a,b)))

# 二维
a = np.array([[1, 1],
              [2, 2],
              [3, 3]])
b = np.array([[4, 4],
              [5, 5],
              [6, 6]])
print(np.hstack((a,b)))

# 运行结果
[1 2 3 4]

[[1 1 4 4]
 [2 2 5 5]
 [3 3 6 6]]
```

### 4.3 np.vstack

​	用于垂直堆叠

```python
# 一维
a = np.array([1, 2])
b = np.array([3, 4])
print(np.vstack((a,b)))

# 二维
a = np.array([[1, 1],
              [2, 2],
              [3, 3]])
b = np.array([[4, 4],
              [5, 5],
              [6, 6]])
print(np.vstack((a,b)))

# 运行结果
[[1 2]
 [3 4]]
 
[[1 1]
 [2 2]
 [3 3]
 [4 4]
 [5 5]
 [6 6]]
```

### 4.4 np.concatenate

​	拼接函数，np.concatenate(a1, a2, a3,...,axis=0)，axis指拼接的维度，默认为0

```python
x1 = np.random.normal(1,1,(5,4))
x2 = np.random.normal(1,1,(3,4))
 
print(x1)
print(x1.shape)
print(x2)
print(x2.shape)
 
con = np.concatenate([x1,x2],axis=0)
print(con)
print(con.shape)
 
输出结果为：
[[ 2.22806658  0.15277615  2.21245262  1.63831116]
 [ 1.30131232 -1.09226289 -0.65959394  1.16066688]
 [ 1.52737722  0.84587186  1.53041503  0.4584277 ]
 [ 1.56096219  1.29506244  3.08048523  2.06008988]
 [ 1.79964236  0.95087117  1.30845477 -0.2644263 ]]
(5, 4)
[[0.89383392 1.49502055 2.90571116 1.71943997]
 [1.44451535 1.87838383 1.4763242  0.82597179]
 [0.72629108 1.42406398 1.35519112 0.58121617]]
(3, 4)
[[ 2.22806658  0.15277615  2.21245262  1.63831116]
 [ 1.30131232 -1.09226289 -0.65959394  1.16066688]
 [ 1.52737722  0.84587186  1.53041503  0.4584277 ]
 [ 1.56096219  1.29506244  3.08048523  2.06008988]
 [ 1.79964236  0.95087117  1.30845477 -0.2644263 ]
 [ 0.89383392  1.49502055  2.90571116  1.71943997]
 [ 1.44451535  1.87838383  1.4763242   0.82597179]
 [ 0.72629108  1.42406398  1.35519112  0.58121617]]
(8, 4)
```

## 5. 拆分

### 5.1 np.split

```python
# np.split(arr,indices_or_sections,axis=0)，返回值为一个装有多个数组的list
# 其中indices_or_sections:如果是一个整数，就用该数平均切分，如果是一个数组，为沿轴切分的位置（左开右闭，从1开始）
# 如果是数字，不均分会报错

# 不均分报错
arr = np.array([2, 3, 4, 5, 6, 7, 8, 9])

arr2 = np.split(arr,3)

print(arr2)
>> error

# 均分
arr = np.array([2, 3, 4, 5, 6, 7, 8, 9])

arr2 = np.split(arr,4)

print(arr2)
>> [array([2, 3]), array([4, 5]), array([6, 7]), array([8, 9])]

# 用数组分割
arr = np.array([2, 3, 4, 5, 6, 7, 8, 9])

arr2 = np.split(arr,[1, 3, 5, 7])

print(arr2)
>> [array([2]), array([3, 4]), array([5, 6]), array([7, 8]), array([9])]


```

### 5.2 np.array_split

​	可以进行不均等分割，靠前的数组占有更多元素，返回一个list

```python
# np.array_split(arr, sections, axis=0)
arr = np.array([2, 3, 4, 5, 6, 7, 8, 9])

arr2 = np.array_split(arr,3)

print(arr2)
>> [array([2, 3, 4]), array([5, 6, 7]), array([8, 9])]
```


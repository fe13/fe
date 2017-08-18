# 深度学习 Deep Learning

## 神经网络 Neural Network
神经网络是一种运算模型，由大量的节点（或称神经元）之间相互联接构成。
### 监督学习 Supervised Learning
监督学习是从**已标记**的训练数据中推断出一个函数(功能)的机器学习任务。

| 输入    | 输出       | 应用       | 神经网络类型                                     |
|--------|------------|-----------|------------------------------------------------|
| 房屋信息 |  房屋价格   | 房价预测   | 标准神经网络 Standard Neural Network             |
| 图片    |            |  图片标记  | 卷积神经网络 `CNN` Convolutional Neural Network  |
| 英文文本 | 中文文本    | 机器翻译   | 循环神经网络 `RNN` Recurrent Neural Network      |

* 结构化数据 - 表格
* 非结构化数据 - 图片，语音，文本

## Python & Vectorization
```python
import time
import numpy as np

a = np.random.rand(10000000)
b = np.random.rand(10000000)

beg = time.time()
c = np.dot(a, b)
end = time.time()

print('result: ' + str(c))
print('time:   ' + str((end - beg) * 1000))

d = 0
beg = time.time()
for i in range(10000000):
  d += a[i] * b[i]
end = time.time()

print('result: ' + str(d))
print('time:   ' + str((end - beg) * 1000))
```

计算每样成分的百分比

| 含量/100克 | 宫保鸡丁 | 红烧牛肉面 | 广州文昌鸡 | 红烧猪蹄筋 |
|:---------:|--------:|---------:|---------:|----------:|
| 碳水化合物  | 12.70   |     62.60|      2.04|       2.20|
| 脂肪       | 15.00   |     17.90|      9.08|       2.83|
| 蛋白质     |  14.24  |     10.20|     15.11|      18.63|
| 纤维素     |   1.95  |      1.40|      0.35|       0.44|

```python
import numpy as np

data = np.array([
  [12.70, 62.60,  2.04,  2.20],
  [15.00, 17.90,  9.08,  2.83],
  [14.24, 10.20, 15.11, 18.63],
  [ 1.95,  1.40,  0.35,  0.44]
])

sumv = data.sum(axis = 0)

print(data / sumv * 100)
```

## Numpy 入门
实现 `sigmoid(x)` 函数
```python
import numpy as np

def sigmoid(x):
  return 1 / (1 + np.exp(-x))

print(sigmoid(np.array([1, 2, 5])))
```
实现 `sigmoid(x)` 的导数函数
```python
def sigmoid_derivative(x):
  s = sigmoid(x)
  return s * (1 - s)
  
print(sigmoid_derivative(np.array([1, 2, 3])))
```


## 在线课程
* [人工神经网络 - 百度百科](https://baike.baidu.com/item/%E4%BA%BA%E5%B7%A5%E7%A5%9E%E7%BB%8F%E7%BD%91%E7%BB%9C/382460?fr=aladdin)
* [监督学习 Supervised Learning - Wikipedia](https://en.wikipedia.org/wiki/Supervised_learning)
* [斯坦福大学 CS 20SI: Tensorflow for Deep Learning Research](https://web.stanford.edu/class/cs20si)
* http://www.fast.ai
* https://www.coursera.org/specializations/deep-learning



# Python

## 向量化 Vectorization
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

## Numpy
`sigmoid(x)`
```python
import numpy as np

def sigmoid(x):
  return 1 / (1 + np.exp(-x))

print(sigmoid(np.array([1, 2, 5])))
```
`sigmoid_derivative(x)`
```python
def sigmoid_derivative(x):
  s = sigmoid(x)
  return s * (1 - s)
  
print(sigmoid_derivative(np.array([1, 2, 3])))
```
`image2vector(image)`
```python
def image2vector(image):
  return image.reshape(image.shape[0] * image.shape[1] * image.shape[2], 1)
```
`normalizeRows(x)`
```python
def normalizeRows(x):
  return x / np.linalg.norm(x, ord = 2, axis = 1, keepdims = True)
```
`softmax(x)`
```python
def softmax(x):
  x_exp = np.exp(x)
  return x_exp / np.sum(x_exp, axis = 1, keepdims = True)
```

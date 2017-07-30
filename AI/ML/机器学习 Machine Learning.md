# 机器学习 Machine Learning

安装 `scikit-learn`
```bash
$ pip install --upgrade scikit-learn
```

| 球员         | 身高 | 体重 | 位置         |
|-------------|-----|------|-------------|
| 斯蒂芬·库里   | 191 |  84  | 后卫 Guard   |
| 克莱·汤普森   | 201 |  93  | 后卫 Guard   |
| 凯文·杜兰特   | 211 | 107  | 前锋 Forward |
| 勒布朗·詹姆斯 | 203 | 113  | 前锋 Forward |

```python
from sklearn import tree

features = [[191, 84], [201, 93], [211, 107], [203, 113]]
labels = ['Guard', 'Guard', 'Forward', 'Forward']

clf = tree.DecisionTreeClassifier()
clf = clf.fit(features, labels)

print clf.predict([[191, 88], [208, 114]])   # ['Guard' 'Forward']
```

## Youtube 视频教程
* [Hello World - Machine Learning Recipes #1](https://www.youtube.com/watch?v=cKxRvEZd3Mw&t=312s)

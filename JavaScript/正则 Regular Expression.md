# 正则 Regular Expression

正则(表达式)是查找特定模式字符串的强大工具，JavaScript 通过内置的 `RegExp` 提供正则支持。

## 创建正则
正则有如下两种创建方式
```javascript
> new RegExp('JavaScript')
→ /JavaScript/

> /JavaScript/
→ /JavaScript/
```

## 匹配测试
```javascript
> /JavaScript/.test('JavaScript')
→ true

> /JavaScript/.test('javascript')
→ false
```
## 匹配集合
匹配中括号 `[]` 里的任意一个字符
```javascript
> /[0123456789]/.test('2017 NBA Finals')
→ true

> /[0-9]/.test('2017 NBA Finals')
→ true

> /\d/.test('2017 NBA Finals')
→ true
```
```javascript
> /[abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ]/.test('Tiger')
→ true

> /[a-zA-Z]/.test('Monkey')
→ true
```
### 字符集合
| 符号  | 含义              |
|------|-------------------|
| `.`  | 任意字符除了换行符   |
| `\d` | `[0-9]`           |
| `\w` | `[a-zA-Z_]`       |
| `\s` | 空格，Tab，换行符   |
| `\D` | 非数字 `/[^0-9]/`  |
| `\W` | `[^a-zA-Z_]`      |
| `\S` | 非空白字符          |

## 匹配重复

| 符号     | 说明          |
|---------|:--------------|
| `*`     | 重复 0+ 次     |
| `+`     | 重复 1+ 次     |
| `?`     | 重复 0 或 1 次 |
| `{n}`   | 重复 n 次      |
| `{n,}`  | 重复 n+ 次     |
| `{n,m}` | 重复 n 到 m 次 |

## 在线工具
* http://regexr.com

## 演讲视频
* [Best of Fluent 2012: /Reg(exp){2}lained/: Demystifying Regular Expressions](https://www.youtube.com/watch?v=EkluES9Rvak)

## 参考链接
* [正则表达式30分钟入门教程](https://deerchao.net/tutorials/regex/regex.htm)
* [常用正则表达式](http://laifh.com/blog/post/123)
* http://eloquentjavascript.net/09_regexp.html
* http://www.regular-expressions.info/tutorial.html
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions
* https://stackoverflow.com/questions/3075130/what-is-the-difference-between-and-regular-expressions

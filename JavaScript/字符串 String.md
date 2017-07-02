# 字符串 String

JavaScript 通过字符串存储文本。字符串的内部格式是 [UTF-16](https://en.wikipedia.org/wiki/UTF-16)，与文档格式无关。

## 声明字符串
字符串可以用一对双引号 `"` 或者单引号 `'` 括起来。
```javascript
"但愿人长久，千里共婵娟。"

'其实我是一个演员。'

"I'm fine, thank you, and you?"  // 如果文本内容包含单引号，那就用 "" 括起来，反之亦然。

"老师说，JavaScript 字符串用单引号 ' 或者双引号 \" 括住都行，那我应该用单引号还是双引号呢？"
'老师说，JavaScript 字符串用单引号 \' 或者双引号 " 括住都行，那我应该用单引号还是双引号呢？'
// 如果文本内容既有单引号又有双引号，那你需要在其中一种前面加 \ 进行转义。
```

## 拼接字符串
可以通过 `+` 拼接字符串，如
```javascript
> "唧唧复唧唧，" + "木兰当户织。"
→ "唧唧复唧唧，木兰当户织。"
```


## 字符串长度 length
```javascript
> "Are you OK?".length
→ 11
> "举头望明月，低头思故乡。".length
→ 12
> "好好Study，天天Happy。".length
→ 16
```

## 参考链接
* https://javascript.info/string
* https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/Strings

# 运算符 Operator

## 算术运算符

| 运算符 | 操作 | 🌰            |
|:-----:|:---:|---------------| 
|  `+`  | 加  | `3 + 5`       |
|  `-`  | 减  | `20 - 7`      |
|  `*`  | 乘  | `4 * 8`       |
|  `/`  | 除  | `100 / 8`     |
|  `%`  | 模  | `50 % 7` 得 1 |

💡 运算符具有优先级，如 `*` 比 `+` 具有更高的优先级，可通过添加 `()` 优先进行某些运算。
```javascript
> 2 + 8
→ 10

> 9 - 3
→ 6

> 3 * 7
→ 21

> 10 / 8
→ 1.25

> 67 % 10
→ 7

> (3 - 5) * 8
→ -16

> 5 * 8 % (9 - 2)
→ 5

> -3 * 7 - -5 * 8
→ 19
```

## 赋值运算符
```javascript
var x = 7;
var y = 8;
var z = x * y;   // z is 56

y += 2;          // y is 10

z *= y;          // z is 560

z /= x;          // z is 80

x -= 2;          // x is 5
```

## 比较运算符
```javascript
> 8 > 6
→ true

> 5 < -2
→ false

> 6 == 7
→ false

> 99 != 100
→ true

> 99.99 >= 99.99
→ true

> 2.3 <= -3
→ false
```

## 参考链接
* https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/A_first_splash
* 🇨🇳 https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Operators/Comparison_Operators

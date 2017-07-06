# 递归 Recursion


```javascript
function appearance(content, search) {
  var index = content.indexOf(search);
  if (index === -1) return 0;
  return 1 + appearance(content.slice(index + 1), search);
}
```

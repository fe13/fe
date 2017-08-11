# 二分搜索 Binary Search

二分搜索是常用的搜索算法，适用于在**已排序**的元素序列中查找元素。

## 参考实现
```javascript
function binarySearch(numbers, target) {
  if (!numbers || numbers.length === 0) return -1;

  let left = 0;
  let right = numbers.length;
  
  while (left <= right) {
    let mid = left + Math.floor((right - left) / 2);

    if (target === numbers[mid]) return mid;

    if (target < numbers[mid]) {
      right = mid - 1;
    } else {
      left = mid + 1;
    }
  }

  return -1;
}
```
```javascript
> binarySearch([1, 3, 5, 7, 9], 5)
→ 2

> binarySearch([1, 3, 5, 7, 9], 6)
→ -1

> binarySearch([7], 7)
→ 0

> binarySearch([6], 7)
→ -1
```

## 视频教程
* https://www.youtube.com/watch?v=P3YID7liBug

## 参考链接
* http://www.jiuzhang.com/solution/classical-binary-search
* https://www.hackerearth.com/practice/algorithms/searching/binary-search/tutorial

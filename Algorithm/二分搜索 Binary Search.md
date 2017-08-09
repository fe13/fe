# 二分搜索 Binary Search

```javascript
function binarySearch(numbers, target) {
  if (!numbers || numbers.length === 0) return -1;

  let left = 0;
  let right = numbers.length;
  
  while (left <= right) {
    let mid = left + Math.ceil((right - left) / 2);

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

## 视频教程
* https://www.youtube.com/watch?v=P3YID7liBug

## 参考链接
* https://www.hackerearth.com/practice/algorithms/searching/binary-search/tutorial

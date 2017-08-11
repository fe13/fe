# 快速排序 Quick Sort 

快速排序(Quick Sort)是非常流行和高效的排序算法。

## 参考实现
```javascript
function quickSort(numbers) {

  quicksort(numbers, 0, numbers.length - 1);
  
  function quicksort(list, left, right) {
    if (left >= right) return;  
    let index = partition(list, left, right);
    quicksort(list, left, index - 1);
    quicksort(list, index, right);
  }

  function partition(list, left, right) {
    let pivot = list[left + Math.floor((right - left) / 2)];
    while (left <= right) {
      while (list[left] < pivot) left += 1;
      while (list[right] > pivot) right -= 1;

      if (left <= right) {
        [list[right], list[left]] = [list[left], list[right]];
        left += 1;
        right -= 1;
      }
    }
    return left;
  }
}
```

## 视频教程
* https://www.youtube.com/watch?v=WaNLJf8xzC4

## 参考链接
* https://www.hackerearth.com/practice/algorithms/sorting/quick-sort/tutorial

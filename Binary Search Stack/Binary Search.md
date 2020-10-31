## <center><font color=#5C4033>Binary Search</font></center>

### <font color=#FF7F00>Java代码</font>
```java
public int binarySearch(int[] arr, int value){
    int low = 0;
    int high = arr.length - 1;
    while(low <= right){
        int mid = low + (((high - low)) >> 1);
        if(arr[mid] == value){
            return mid;
        } else if (arr[mid] > value){
            high = mid - 1;
        } else {
            low = mid + 1;
        }
    }
    return -1;
}
```

[参考链接](https://blog.csdn.net/cedarjo/article/details/88971505)
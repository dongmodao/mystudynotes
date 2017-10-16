## VBA 中的一些坑

1. Application.WorkSheetFunction.Index
 Application.WorkSheetFunction.Index\(array, rowindex, colindex\)，其中，如果要获得二维数组正确的某行或者某列，要转换成第几行、第几列，而不是下标，虽然下标 0 他也不会报错，给的是第一行的数据。也就是说，0 和 1 得到的都是第一行的数据。
 
 比如，arr\(2, 1\) 表示 3 行 2 列的数组，最高行坐标到 2，使用上面的 Application.WorkSheetFunction.Index\(arr, 1, 0\) 得到数组第一行的数据，Application.WorkSheetFunction.Index\(arr, 3, 0\) 得到的是第三行的数据。
 
2.  Application.WorkSheetFunction.Match
 跟上面的情况是一样的，得到的也是匹配元素是第几个，而不是得到下标，要注意，不能直接把结果当做下标来使用。







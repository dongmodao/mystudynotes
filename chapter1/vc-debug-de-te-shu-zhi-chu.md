## VC debug过程中值得注意之处

1. 未初始化的栈内存指针填充 `0xcccccccc`，对应为中文“烫烫烫烫……”

2. 未初始化的堆内存指针填充 `0xcdcdcdcd`，对应为中文“屯屯屯屯……”

3. 堆内存中已经释放内存填充 `0xfeeefeee`

4. debug跟release在初始化变量时所做的操作是不同的，debug是将每个字节位都赋成0xcc，而release的赋值近似于随机
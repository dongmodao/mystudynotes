## ECharts 的使用
本片文章来自于官方教程 [5 分钟上手 Echarts](http://echarts.baidu.com/tutorial.html#5%20%E5%88%86%E9%92%9F%E4%B8%8A%E6%89%8B%20ECharts) 以及自己的使用提炼而来，可戳原网址查看官方教程自行学习。

1. 首先，获取 Echarts：[官网下载](http://echarts.baidu.com/download.html)、[GitHub 下载](https://github.com/ecomfe/echarts)、npm 使用 ``npm install echarts --save`` 下载、cdn 引入（cdnjs、npmcdn、bootcnd 等渠道）。
2. 新版 Echarts 引入方式和普通的 JavaScript 引入方式一样，在网页源码中使用 ``<script src="echarts.min.js"></script>`` 引入。``echarts.min.js`` 放置在源代码同文件夹下。
3. 绘制图表：在源码中添加一个具有宽高的 DOM 容器 ``<div id="main" style="width: 600px;height:400px;"></div>``，通过  echarts.init 初始化一个 ECharts 实例 ``var myChart = echarts.init(document.getElementById('main'));``，随后通过实例的 setOption(option) 生成图表。其实，个人认为，定义 option 才是最关键的一步，涉及了图表的样式以及数据。以下是官网给出的例子：
``` html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>ECharts</title>
    <!-- 引入 echarts.js -->
    <script src="echarts.min.js"></script>
</head>
<body>
    <!-- 为ECharts准备一个具备大小（宽高）的Dom -->
    <div id="main" style="width: 600px;height:400px;"></div>
    <script type="text/javascript">
        // 基于准备好的dom，初始化echarts实例
        var myChart = echarts.init(document.getElementById('main'));

        // 指定图表的配置项和数据
        var option = {
            title: {
                text: 'ECharts 入门示例'
            },
            tooltip: {},
            legend: {
                data:['销量']
            },
            xAxis: {
                data: ["衬衫","羊毛衫","雪纺衫","裤子","高跟鞋","袜子"]
            },
            yAxis: {},
            series: [{
                name: '销量',
                type: 'bar',
                data: [5, 20, 36, 10, 10, 20]
            }]
        };

        // 使用刚指定的配置项和数据显示图表。
        myChart.setOption(option);
    </script>
</body>
</html>
```
![](/assets/echarts.PNG "效果图")

后续会加入更多东西，今天暂时入门。

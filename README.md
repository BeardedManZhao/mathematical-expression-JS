# mathematical-expression-JS

通过 JavaScript 中调用公共后端API 的方式实现数学表达式解析！

![文章的封面](https://user-images.githubusercontent.com/113756063/203919312-dcec4a61-2136-4af2-a361-66b2ed4e6a54.png "文章的封面")

## 介绍

ME 数学表达式计算组件是一种针对数学公式解析的有效工具，其提供了 Java python 和 C++ 版本的API，如果我们要是希望在 JS 中调用这个库该怎么办呢？ 其实我们可以直接使用后端接口来实现此功能，ME
数学表达式解析库已经集成到了网站计算服务中的公共API 中，您可以通过调用公共的 API 接口并按照适当的方式传递参数实现 JS 中调用 数学表达式的需求，接下来就是相关的处理。

### 调用示例

您可以在这里通过 axios 等框架来实现访问后端接口，在这里我们提供了一个调用示例，下面就是具体的例子。

```html
<!-- 请将此处 的 axios 替换为您的 js 文件路径 -->
<script rel="script" type="text/javascript" src="js/lib/axios.min.js"></script>
<script>
    axios(
            {
                // 在这里指定计算接口，请确保链接不要输错
                url: "http://lsc.lingyuzhao.top/LS-WebBackEnd/API/Mathematical_Expression_Run",
                params: {
                    // 设置需要计算的数学表达式 表达式中的空格可以不规范 且支持嵌套括号计算
                    f: "1+2+(2 *(1 - 2))"
                }
            }
    ).then(
            (res) => {
                console.info(res.data)
            }
    )
</script>
```

下面就是打印结果，在这里可以看到打印出的 json 对象，以及每个参数的解释。

|          参数名称           |                       参数解释                       |
|:-----------------------:|:------------------------------------------------:|
|           url           |                    项目的开源仓库地址                     |
|            f            |                 计算操作进行时使用的数学表达式                  |
|  calculationSourceName  |                 计算时使用的计算组件的型号/名称                 |
|         result          |                    计算结果，是数值类型                    |
|           RES           |  计算结果，如果计算操作没有出现错误，此数值为 `ok!!!!` 如果出现错误则返回错误信息。  |

```
{
    "url": "https://github.com/BeardedManZhao/mathematical-expression-JS.git",
    "f": "1+2+(2 *(1 - 2))",
    "calculationSourceName": "bracketsCalculation2",
    "result": 1,
    "RES": "ok!!!!"
}
```

### 在线调试

您可以在 [数学表达式 API 工具](http://www.lingyuzhao.top/LS-WebFront/MeTool.html "《数学表达式 API 工具》") 中去在线调用此框架！！！

## 在其它编程语言中调用 ME 组件库的 API

[《mathematical-expression 实现 数学表达式解析 C++ 篇》](http://www.lingyuzhao.top/?/linkController=/articleController&link=22700148 "《mathematical-expression 实现 数学表达式解析 C++ 篇》")

[《mathematical-expression 实现 数学表达式解析 Java 篇》](http://www.lingyuzhao.top/?/linkController=/articleController&link=94267819 "《mathematical-expression 实现 数学表达式解析 C++ 篇》")



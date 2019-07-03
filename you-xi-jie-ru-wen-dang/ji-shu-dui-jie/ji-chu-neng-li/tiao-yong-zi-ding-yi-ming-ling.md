# 调用自定义命令

```javascript
    callCustomCommand(Object object, ...)
```

_**支持版本: \(core 版本 &gt;= 1.1.1\)**_ 具体功能需要由宿主应用提供, Runtime 本身默认不支持任何自定义命令, 任何调用都会返回失败.

_参数_

* Object object

| 属性 | 键值类型 | 是否必填 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- | :--- |
| success | function | 否 |  | 接口调用成功的回调函数 |
| fail | function | 否 |  | 接口调用失败的回调函数 |
| complete | function | 否 |  | 接口调用结束的回调函数（调用成功、失败都会执行） |

* ...

传递给宿主的不定参数, 支持基本类型、TypedArray 和基本数组:

| 基本类型 | 说明 |
| :--- | :--- |
| null | 空类型 |
| boolean | 布尔类型 |
| number | 数字类型。如果数字是整数，底层当成64位有符号数处理，否则当成64位浮点数处理 |
| string | 字符串类型 |

| TypedArray类型 | 说明 |
| :--- | :--- |
| Int8Array | 单字节数组 |
| Int16Array | 双字节数组 |
| Int32Array | 4字节数组 |
| Float32Array | 单精度浮点数数组 |
| Float64Array | 双精度浮点数数组 |

对于基本数组, 要求数组中的所有元素的类型要求一致；基本数组支持以下数据形式:

| 元素类型 | 说明 |
| :--- | :--- |
| boolean | 布尔值数组。底层做为布尔数组处理 |
| number | 数字数组。数组中所有数字按双精度浮点数处理 |
| string | 字符串数组 |

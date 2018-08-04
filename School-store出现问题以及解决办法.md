Q1：**运行onLoad函数时报错thirdScriptError**

错误代码：![1533345001156](C:\Users\12157\AppData\Local\Temp\1533345001156.png)

**问题所在**：qcloud.request，没有加载相应SDK

参考文档：https://github.com/tencentyun/wafer2-client-sdk/blob/master/README.md 

**阅读得之，请求服务时，调用request之前还没登陆，则需要用login方法于请求之前自动登录**

```javascript
// 使用 login 参数之前，需要设置登录地址
qcloud.setLoginUrl('https://199447.qcloud.la/login');
qcloud.request({
    login: true,
    url: 'http://199447.qcloud.la/user',
    success: function (response) {
        console.log(response);
    },
    fail: function (err) {
        console.log(err);
    }
});
```

代码片段：wechatide://minicode/bXpnVpm5731X

解决如下：

![1533345386955](C:\Users\12157\AppData\Local\Temp\1533345386955.png)

问题：https://cloud.tencent.com/developer/ask/150788/answer/262054




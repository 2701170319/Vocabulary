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



Q2：![1533353319840](C:\Users\12157\AppData\Local\Temp\1533353319840.png)

```javascript
SET @IMAGE_BASE_URL = "https://product-1256871806.cos.ap-shanghai.myqcloud.com/"; -- FOR EXAMPLE: https://*****.ap-shanghai.myqcloud.com/
```

报错渲染层网络层错误，查看数据库，发现上述代码少符号"/"所以无法访问

所以导入数据库的时候整体会缺少“/”符号

解决办法：需重新导入，或手动修改



Q3：

在pages中添加detail报错

原因：前期理解不透彻（可直接在detail右键新建page即可生成js/json/wxml/wxss文件，此步过后直接在app.json中发现已经加入detail）

解决方法：添加detail时确保在app.json也已经添加



Q4：

出现thirdScriError错误

![1533604881847](C:\Users\12157\AppData\Local\Temp\1533604881847.png)

错误代码：user.js中

```javascript

onTapAddress() {
  
} //错误为少加逗号

  /**
   * 生命周期函数--监听页面加载
   */
  onLoad: function (options) {
  
  },

```

原因：少加逗号
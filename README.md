# js-copy-and-send-image

最近有一个需求是把聊天窗口中的图片复制并发送给其他人。

但是，很不幸，chrome自从2012年以后就不支持JS复制网页图片，这个[issue](https://bugs.chromium.org/p/chromium/issues/detail?id=150835)挂在chromium上很多年了，似乎并不打算支持了。

社区上比较著名的clipboard.js也不支持复制图片。

w3c新出的[clipboard-apis](https://w3c.github.io/clipboard-apis/)同样不支持复制图片，[社区](https://github.com/w3c/clipboard-apis/issues/44)其实是希望能支持的。

所以只好通过hack的方式来解决了。

解决思路如下：

1、 复制图片的url

2、通过canvas转换为dataURL

3、将dataURL发往后端

4、后端返回新图片链接，插入到聊天窗口中


# 传统方式接收第三方回调现状

1.**费用**-需要单独的服务器来接收回调  

2.**复杂**-繁琐的Nginx配置和PHP脚本  

3.**臃肿**-持久化存储依靠数据库等产品  

4.**繁重**-用SQL语句查询很不方便

# 使用云函数来接收回调带来的好处

1.**开箱即用**-上传接收回调函数代码包即可一键部署

2.**轻便查询，持久保存**-云函数接收到的回调信息全文写入CLS并且自动建立字段索引，方便查询**回调结果**并且可以配置**自动投递**到对象存储持久化保存回调日志

# 使用云函数接收回调的案例

- 对象存储-图片审核回调

![回调日志实时查询](https://ask.qcloudimg.com/developer-images/article/1148853/4t6z93d815.png?imageView2/2/w/1620)

# 云函数部署说明

## 1.前往[Serverless控制台](https://console.cloud.tencent.com/scf/list)创建一个云函数

## 2.[点我下载用于接收回调函数的代码包](https://sls-1252458796.cos.ap-guangzhou.myqcloud.com/%E6%8E%A5%E6%94%B6%E7%AC%AC%E4%B8%89%E6%96%B9%E5%9B%9E%E8%B0%83%E5%87%BD%E6%95%B0%E4%BB%A3%E7%A0%81%E5%8C%85-PHP.zip)

## 3.按照下图指引创建和导入云函数

![创建和导入云函数](https://ask.qcloudimg.com/developer-images/article/1148853/7stbicgbiu.png?imageView2/2/w/1620)

## 5.测试回调函数

![测试回调函数](https://ask.qcloudimg.com/developer-images/article/1148853/21qjy83pk3.png?imageView2/2/w/1620)

## 6.建立需要的索引字段

![索引配置](https://ask.qcloudimg.com/developer-images/article/1148853/29ui0wioj2.png?imageView2/2/w/1620)

![编辑索引配置](https://ask.qcloudimg.com/developer-images/article/1148853/9b9uay7o23.png?imageView2/2/w/1620)

![建立需要的索引字段](https://ask.qcloudimg.com/developer-images/article/1148853/c5wnqcpvbr.png?imageView2/2/w/1620)

## 7.持久化处理回调日志，[将回调日志投递至对象存储](https://console.cloud.tencent.com/cls/shipper/cos)

![添加投递任务](https://ask.qcloudimg.com/developer-images/article/1148853/elu5rekjw9.png?imageView2/2/w/1620)

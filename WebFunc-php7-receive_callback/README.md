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

![回调日志实时查询](https://sls-1252458796.cos.ap-guangzhou.myqcloud.com/WebFunc-php7-receive_callback/img/%E5%9B%9E%E8%B0%83%E6%97%A5%E5%BF%97%E5%AE%9E%E6%97%B6%E6%9F%A5%E8%AF%A2.png?imageView2/2/w/1320)

# 云函数部署说明

## 1.前往[Serverless控制台](https://console.cloud.tencent.com/scf/list)创建一个云函数

## 2.[点我下载用于接收回调函数的代码包](https://sls-1252458796.cos.ap-guangzhou.myqcloud.com/%E6%8E%A5%E6%94%B6%E7%AC%AC%E4%B8%89%E6%96%B9%E5%9B%9E%E8%B0%83%E5%87%BD%E6%95%B0%E4%BB%A3%E7%A0%81%E5%8C%85-PHP.zip)

## 3.按照下图指引创建和导入云函数

![创建和导入云函数](https://sls-1252458796.cos.ap-guangzhou.myqcloud.com/WebFunc-php7-receive_callback/img/%E5%88%9B%E5%BB%BA%E5%92%8C%E5%AF%BC%E5%85%A5%E4%BA%91%E5%87%BD%E6%95%B0.png?imageView2/2/w/1320)

## 5.测试回调函数

![测试回调函数](https://sls-1252458796.cos.ap-guangzhou.myqcloud.com/WebFunc-php7-receive_callback/img/%E6%B5%8B%E8%AF%95%E5%9B%9E%E8%B0%83%E5%87%BD%E6%95%B0.png?imageView2/2/w/1320)

## 6.建立需要的索引字段

![索引配置](https://sls-1252458796.cos.ap-guangzhou.myqcloud.com/WebFunc-php7-receive_callback/img/%E7%B4%A2%E5%BC%95%E9%85%8D%E7%BD%AE.png?imageView2/2/w/1320)

![编辑索引配置](https://sls-1252458796.cos.ap-guangzhou.myqcloud.com/WebFunc-php7-receive_callback/img/%E7%BC%96%E8%BE%91%E7%B4%A2%E5%BC%95%E9%85%8D%E7%BD%AE.png?imageView2/2/w/1320)

![建立需要的索引字段](https://sls-1252458796.cos.ap-guangzhou.myqcloud.com/WebFunc-php7-receive_callback/img/%E5%BB%BA%E7%AB%8B%E9%9C%80%E8%A6%81%E7%9A%84%E7%B4%A2%E5%BC%95%E5%AD%97%E6%AE%B5.png?imageView2/2/w/1320)

## 7.持久化处理回调日志，[将回调日志投递至对象存储](https://console.cloud.tencent.com/cls/shipper/cos)

![添加投递任务](https://sls-1252458796.cos.ap-guangzhou.myqcloud.com/WebFunc-php7-receive_callback/img/%E6%B7%BB%E5%8A%A0%E6%8A%95%E9%80%92%E4%BB%BB%E5%8A%A1.png?imageView2/2/w/1320)

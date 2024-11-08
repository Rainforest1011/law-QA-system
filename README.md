# law-QA-system

# elasticQAPy3.11Code.zip 运行依赖
* elasticSearch 7.3.2  
* Python 3.12
* Django   4.2.16


# 运行软件环境
*Anaconda 3     之spider
* elasticSearch 7.3  
* Python 3.12 
* Django   4.2.16
*PyCharm 2024.2.4

## Python 依赖库
* django  3.0.3
* jieba   
* pyahocorasick

## 运行步骤
1. 启动Anaconda环境的控制台。启动Anaconda可视化界面，选中elasticQA环境，“open terminal"，打开spider查看项目代码。也可以用命令行方式，MacOS进入conda 的命令行方式如下：
```
conda activate elasticQAPy311
```
2. 在conda的控制台启动 django  
``` 
cd code/kbdemo  (依据自己的位置修改)
python manage.py runserver
```
3. 启动elasticSearch 
```
cd elasticsearch-7.6.0/bin 
./elasticsearch  
```

* 访问 curl 'http://localhost:9200’  测试elasticsearch是否启动成功
* 可能出现的问题 ：curl: (52) Empty reply from server 修改方法：在 /config/elasticsearch.yml 中修改 xpack.security.enabled: false 参考链接 https://stackoverflow.com/questions/66772673/parse-server-curl-52-empty-reply-from-server
4. 语义搜索系统入口
* 访问 http://localhost:8000/search

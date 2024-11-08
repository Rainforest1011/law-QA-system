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
软件初始化指南
1.	下载elasticsearch v7.3.2 和 kibana v7.3.2 和 ik分词器v7.3.2（可选，如果有问题另外说）
2.	解压后分别点击启动             
elasticsearch-7.3.2-windows-x86_64\elasticsearch-7.3.2\bin\elasticsearch.bat
kibana-7.3.2-windows-x86_64\kibana-7.3.2-windows-x86_64\bin\kibana.bat
 
Elasticsearch出现started后即为成功
 
Kibana出现端口号即为成功，并访问5601。
3.	进入5601（kibana主页）点左边扳手（dev tool）进入命令行页面
 
 
4.	将以下代码粘贴至左边代码窗口，待命：
#创建索引
PUT /label?include_type_name=true
{
  "mappings": {
    "laws": {
      "properties": {
        "subj": {"type": "keyword"},
        "po":{
          "properties":{
            "pred":{"type":"keyword"},
            "obj":{"type":"keyword"}
          }
        }
      }
    }
  }
}

#查看索引
GET /label

#删除索引
DELETE /label

#通过索引查找数据
GET /label/laws/_search?&pretty
{
  "query":{
    "bool":{
      "must":{ 
        "term":{
          "subj": "第四章"
        }
      } 
    }
  } 
}
5.	下载并解压，使用编码软件（pycharm等）打开产品项目包（elasticQAPy3.11Code_remake）
 
6.	确定右上角运行内容一致，点击运行，之后访问端口8000进入登录页。（先不登陆）
7.	回到kibana窗口，点击“#创建索引”代码，运行（该运行是搭建索引）
 
8.	启用命令行窗口，进入项目（elasticQAPy3.11Code_remake）的以下目录：
elasticQAPy3.11Code_remake\qacode\kbdemo
运行以下指令，等待结束即可：
 
9.	（可选）以防万一，进入kbdemo目录下search文件，再敲入以上指令，等待即可：
 
（注：第八步和第九步也可直接在pycharm上选中并运行对应程序代码）
 
10.	回到kibana窗口，试运行以下区的代码，检查右边json文字”hits”属性中是否有“第四章”法条内容（图如下，查到时右边会有一大堆东西）
 
11.	现在可以回到8000项目页面了，问答的基本功能可以满足（有些需要另外调教，写不写的完就是另外一码事了……）

# KBQA-demo

本项目使用Python搭建了一个简易的问答程序。下图是demo的展示效果：

![demo效果图](url)

## 环境要求
- python3
- apache-jena-3.7
- apache-jena-fuseki-3.7

## 使用

### 一 环境安装
1. [安装python3](https://www.python.org/downloads/)
2. [安装apache-jena](https://jena.apache.org/download/index.cgi)
3. [安装apache-jena-fuseki](https://jena.apache.org/download/index.cg)
4. clone代码, 安装库依赖
```
git clone url
cd KBQA-demo
pip install -i http://pypi.douban.com/simple -- trusted-host pypi.douban.com -r requirements.txt
```

建议安装Apache-jena版本为3.7的，当时使用了最新版3.8出现过诸多问题。
MySQL版本无所谓，若使用最新版配置环境时需注意一些问题。

### 二 使用前配置
1. 在本地jena安装目录下创建tdb文件夹，用于存放tdb数据。
2. 进入jena\bat文件夹执行批处理文件 .\tdbloader.bat --loc="jena\tdb" "path\to\KBQA-demo\kg_demo_movie.nt"
3. 进入jena-fuseki运行`fuseki-server.bat`, 程序会在当前目录中自动创建`run`文件夹。
4. 把本体文件`ontology.ttl`移动到`jena-fuseki\run\database\`目录下。
5. 把`fuseki_conf.ttl`移动到`jena-fuseki\run\fuseki_conf\`目录下，用记事本打开，文件中有两处需要修改为本地文件目录位置，一处是`1`中`tdb`的路径，另一处是`4`中`ontology.ttl`的路径。
6. 删除`jena\tdb`目录中以`prefix`开头的文件。
7. 双击运行`jena-fuseki\fuseki-server.bat`，如果没有出现异常，并显示服务运行在`3030`即运行成功。

### 三 使用KBQA-demo
1. 启动jena的3030服务。(如果这一步出现异常，可尝试删除`tdb\prefix*`)。
2. 运行`KBQA-demo\kbqa_demo_movie\query_main.py`。

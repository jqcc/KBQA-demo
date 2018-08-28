# KBQA-demo

����Ŀʹ��Python���һ�����׵��ʴ������ͼ��demo��չʾЧ����

![demoЧ��ͼ](url)

## ����Ҫ��
- python3
- apache-jena-3.7
- apache-jena-fuseki-3.7

## ʹ��

### һ ������װ
1. [��װpython3](https://www.python.org/downloads/)
2. [��װapache-jena](https://jena.apache.org/download/index.cgi)
3. [��װapache-jena-fuseki](https://jena.apache.org/download/index.cg)
4. clone����, ��װ������
```
git clone url
cd KBQA-demo
pip install -i http://pypi.douban.com/simple -- trusted-host pypi.douban.com -r requirements.txt
```

���鰲װApache-jena�汾Ϊ3.7�ģ���ʱʹ�������°�3.8���ֹ�������⡣
MySQL�汾����ν����ʹ�����°����û���ʱ��ע��һЩ���⡣

### �� ʹ��ǰ����
1. �ڱ���jena��װĿ¼�´���tdb�ļ��У����ڴ��tdb���ݡ�
2. ����jena\bat�ļ���ִ���������ļ� .\tdbloader.bat --loc="jena\tdb" "path\to\KBQA-demo\kg_demo_movie.nt"
3. ����jena-fuseki����`fuseki-server.bat`, ������ڵ�ǰĿ¼���Զ�����`run`�ļ��С�
4. �ѱ����ļ�`ontology.ttl`�ƶ���`jena-fuseki\run\database\`Ŀ¼�¡�
5. ��`fuseki_conf.ttl`�ƶ���`jena-fuseki\run\fuseki_conf\`Ŀ¼�£��ü��±��򿪣��ļ�����������Ҫ�޸�Ϊ�����ļ�Ŀ¼λ�ã�һ����`1`��`tdb`��·������һ����`4`��`ontology.ttl`��·����
6. ɾ��`jena\tdb`Ŀ¼����`prefix`��ͷ���ļ���
7. ˫������`jena-fuseki\fuseki-server.bat`�����û�г����쳣������ʾ����������`3030`�����гɹ���

### �� ʹ��KBQA-demo
1. ����jena��3030����(�����һ�������쳣���ɳ���ɾ��`tdb\prefix*`)��
2. ����`KBQA-demo\kbqa_demo_movie\query_main.py`��

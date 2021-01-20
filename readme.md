# DBLP 爬虫说明
### 安装依赖
```
    pip install scrapy
```
由于scrapy需要用到Twisted，而安装Twisted需要安装Microsoft C++ Build Tools，所以如果没安装C++ Build Tools会出现安装错误。

### 使用说明
在Dblp/spiders/dblp.py文件中，修改start_urls和year
```
    start_urls = []  # 需要搜索的期刊/会议的dblp主页
    year = n  # 最近的n届期刊/会议
```
设定好参数之后即可进行爬虫
```
    # -o 后面的是文件名，可以支持的格式有info.json, iofo.json1, info.csv, info.xml，启动命令在下方
    scrapy crawl dblp -o info.csv

    # 如果还出现乱码就使用以下方法
    scrapy crawl dblp -o info.json
    python json_to_xls.py
```

### 输出文件说明
| 参数 | 含义 |
| - | - |
| ConOrJou | 会议/期刊 |
| authors | 作者列表 |
| title | 论文名字 |#   D b l p  
 
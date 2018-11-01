# Sphinx 文档示例

sphinx 文档示例。在 mkdocs/sphinx/gitbook 之间最后选择了 sphinx。
mkdocs 目前无法支持导出(不过可以直接 make gh-pages 发布到 github pages 比较方便), gitbook 对中文导出不太好。
sphinx 支持导出成 pdf/epub 等格式的电子书，方便网页查看或者下载阅读。
同时 rst 相比 markdown 更加强大。如果需要在 markdown 和 rst 互相转可以用 [pandoc](https://pandoc.org/try/)


### 使用步骤：

```sh
clone https://github.com/PegasusWang/sphinx_demo  # clone 项目，你可以先 fork 一份到自己的仓库
pip install -r requirements.txt  # 安装依赖，包括 sphinx 和主题，插件
make livehtml  # 监听文件变动自动刷新网页
```

### 安装主题

```py
# conf.py
import sphinx_rtd_theme
html_theme = 'sphinx_rtd_theme'
html_theme_path = [sphinx_rtd_theme.get_html_theme_path()]
```

### 自动刷新

编辑 Makefile 增加：

```sh
.PHONY: livehtml
livehtml:
	sphinx-autobuild -b html $(ALLSPHINXOPTS) $(BUILDDIR)/html
```

### 访问

访问本地 `http://127.0.0.1:8000/`
如果需要在线访问，你需要在 [readthedoc.org](https://readthedocs.org/) 配置，并在对应的 github 项目上增加 readthedoc
webhook。

在线访问地址： https://demo-sphinx.readthedocs.io/en/latest/


### 参考：

[如何用 ReadtheDocs、Sphinx 快速搭建写书环境](https://www.jianshu.com/p/78e9e1b8553a)

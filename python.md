## 常用链接

* [PyPI](https://pypi.python.org/pypi)
* [PyPI Ranking](http://pypi-ranking.info/alltime)
* [GitHub Trending](https://github.com/trending?l=python&since=monthly)
* [Unofficial Windows Binaries for Python Extension Packages](http://www.lfd.uci.edu/~gohlke/pythonlibs/) -- Windows 平台二进制扩展包
* [Python HOWTOs](https://docs.python.org/3.4/howto/index.html)
* [PyZh](https://pyzh.readthedocs.org/en/latest/index.html) -- 一起写文章, 一起看文章
  - [让人耳目一新的Python库](https://pyzh.readthedocs.org/en/latest/awesome-python-libraries.html)
* [PEP-0](https://www.python.org/dev/peps/)
* [PEP-3333](https://www.python.org/dev/peps/pep-3333/) -- WSGI(Python Web Server Gateway Interface)

## Python 文章/教程

* [Awesome Python](https://github.com/vinta/awesome-python)
* [30 Python Language Features and Tricks You May Not Know About](http://sahandsaba.com/thirty-python-language-features-and-tricks-you-may-not-know.html)
* [用 setuptools 安装命令行工具](http://click.pocoo.org/4/setuptools/)
* Python 语言特性
  * [Descriptor HowTo Guide](https://docs.python.org/3.4/howto/descriptor.html)
* [abc](https://docs.python.org/3.4/library/abc.html) -- Abstract Base Classes
  * [collections.abc](https://docs.python.org/3.4/library/collections.abc.html#collections-abstract-base-classes) [源码](https://hg.python.org/cpython/file/3.4/Lib/_collections_abc.py)
* [Setuptools](http://pythonhosted.org/setuptools/)
  * [Working in “Development Mode”](https://packaging.python.org/en/latest/distributing.html#working-in-development-mode)
* asyncio
  * [Fast scraping in python with asyncio](http://compiletoi.net/fast-scraping-in-python-with-asyncio.html)

## 工具

* [Cython](http://cython.org/)

## Python 模块

* [lxml](https://pypi.python.org/pypi/lxml/3.4.4) -- XML 分析处理
* [PyYAML](https://pypi.python.org/pypi/PyYAML) -- PyYAML
* [SQLAlchemy](http://www.sqlalchemy.org/)
* [Jinja2](http://jinja.pocoo.org/)
* [parsimonious](https://github.com/erikrose/parsimonious) - PEG(parsing expression grammars) parser
* [redis-py](https://github.com/andymccurdy/redis-py)

* **[sh](http://amoffat.github.io/sh/)**: `from sh import ifconfig; print(ifconfig("wlan0"))`
* fn.py
* when.py
* requests
* **[tinydb](https://github.com/msiemens/tinydb)**

### Web 相关

* [HTTPie](https://github.com/jakubroztocil/httpie)
* gunicorn [文档](http://docs.gunicorn.org/) - Python WSGI HTTP Server for UNIX

### asyncio 相关

* KeepSafe/[aiohttp](https://github.com/KeepSafe/aiohttp)
  * aio-libs/[aiorest](https://github.com/aio-libs/aiorest) -- 已废弃，最重要的功能已经移到 aiohttp.web: Request 和 Response
  * aio-libs/[aiohttp_session](https://github.com/aio-libs/aiohttp_session)
  * aio-libs/[aiohttp_jinja2](https://github.com/aio-libs/aiohttp_jinja2) -- 感觉没太大价值
* Redis
  * jonathanslenders/[asyncio_redis](https://github.com/jonathanslenders/asyncio-redis) -- 推荐
  * aio-libs/[aioredis](https://github.com/aio-libs/aioredis)

### 工具类

* [click](http://click.pocoo.org/)
* [chardet](https://pypi.python.org/pypi/chardet) -- 字符编码检测
* [stevedore](https://github.com/openstack/stevedore) -- 动态插件管理
* [python-dateutil](https://github.com/dateutil/dateutil/) -- 超强的日期工具

### 其他

* [setproctitle](http://pypi.python.org/pypi/setproctitle) - 修改进程名
* [pbr](https://pypi.python.org/pypi/pbr) -- 对于我来说，有点复杂了，用不到

## TIPS

### Python 语言特性

* set 可以写成: `{1, 2, 3}`
* `callable(object)`
* `filter(function, iterable)`
  - `itertools.filterfalse`
* `format(value[, format_spec])`
* `frozenset([iterable])`
* `hash(object)`, `id(object)`
* `iter(object[, sentinel])`
* `print(*objects, sep=' ', end='\n', file=sys.stdout, flush=False)` -- 注意 flush 参数
* `sorted(iterable[, key][, reverse])` -- 注意 reverse 参数
* `zip(*iterable)` 和 `itertools.zip_longest(*iterables, fillvalue=None)`
* `int.bit_length`, `int.from_bytes`, `int.to_bytes`
* `bytes.fromhex(string)`
* `memoryview`, `memoryview.tobytes`
* `str.format(*args, **kwargs)`, **`str.format_map(mapping)`**
* `first, *middle, last = grades`

### 常用软件包

* [pkg_resources 常用API](https://pythonhosted.org/setuptools/pkg_resources.html#convenience-api)
  - load_entry_point(dist, group, name)
  - get_entry_info(dist, group, name)
  - get_entry_map(dist, group=None)
  - iter_entry_points(group, name=None)

## 知识点/技巧


### raise ... from ...

示例:

    raise new_exc from original_exc

### Python3 中的 ascii() 和 repr()

* repr 可能会返回非 ASCII 字符
* ascii 返回 ASCII 字符，对于非 ASCII 用 \x, \u 或 \U 转义。

示例:

    >>> repr('你好'), ascii('你好')
    ("'你好'", "'\\u4f60\\u597d'")
    >>> repr('\xa1\xa2'), ascii('\xa1\xa2')
    ("'\xa1\xa2'", "'\\xa1\\xa2'")

### bytes 和 bytearray

* bytes 是不可修改的字节序列
* bytearray 是可修改的字节序列

常用用法:

* 从 hex 字符串创建 bytes
  - bytes.fromhex('2Ef0 F1f2  ')
* 创建 bytearray 的几种方法
  - bytearray(10)  # 创建长度为 10 的 bytearray
  - bytearray(range(20)) # 从整数序列创建
  - bytearray(b'Hi!')

### metaclass

* [Classes as objects](http://stackoverflow.com/questions/100003/what-is-a-metaclass-in-python#answer-6581949)
  - [译文](http://blog.jobbole.com/21351/)

Python2 和 Python3 均支持的格式:

    class C(metaclass=PapayaMeta):
        pass

## 常用链接

* [GitHub Trending](https://github.com/trending?l=python&since=monthly)
* [Unofficial Windows Binaries for Python Extension Packages](http://www.lfd.uci.edu/~gohlke/pythonlibs/) -- Windows 平台二进制扩展包
* [setuptools](http://pythonhosted.org/setuptools/setuptools.html) -- 不会写 setup.py? 看看这篇文章
  * [Working in “Development Mode”](https://packaging.python.org/en/latest/distributing.html#working-in-development-mode)

## 经典/酷毙的 Python 模块/工具

* [Cython](http://cython.org/)
* [click](http://click.pocoo.org/)
* [stevedore](https://github.com/openstack/stevedore) -- 动态插件管理

## 试用过的模块

* [pbr](https://pypi.python.org/pypi/pbr) -- 对于我来说，有点复杂了，用不到

## Python 模块

* gunicorn [文档](http://docs.gunicorn.org/) - Python WSGI HTTP Server for UNIX
* [setproctitle](http://pypi.python.org/pypi/setproctitle) - 修改进程名
* [parsimonious](https://github.com/erikrose/parsimonious) - PEG(parsing expression grammars) parser

## Python 项目

* [Awesome Python](https://github.com/vinta/awesome-python)
* [HTTPie ](https://github.com/jakubroztocil/httpie)
* [aiohttp](https://github.com/KeepSafe/aiohttp) [文档](http://aiohttp.readthedocs.org/)
  - aiohttp_session
  - aiohttp_jinja2

## 好文章

* [30 Python Language Features and Tricks You May Not Know About](http://sahandsaba.com/thirty-python-language-features-and-tricks-you-may-not-know.html)
* [用 setuptools 安装命令行工具](http://click.pocoo.org/4/setuptools/)

## TIPS

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

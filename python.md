## Python 模块

* gunicorn [文档](http://docs.gunicorn.org/) - Python WSGI HTTP Server for UNIX
* [setproctitle](http://pypi.python.org/pypi/setproctitle) - 修改进程名
* [aiohttp](https://github.com/KeepSafe/aiohttp) [文档](http://aiohttp.readthedocs.org/)
  - aiohttp_session
  - aiohttp_jinja2

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

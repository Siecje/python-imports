Starting with a Python2 project with imports like ```circular_py2``` I am trying to add Python3 support.

```shell
$ python -m circular_py2.two
works
$ python3 -m circular_py2.two
Traceback (most recent call last):
  File "/usr/lib/python3.5/runpy.py", line 184, in _run_module_as_main
    "__main__", mod_spec)
  File "/usr/lib/python3.5/runpy.py", line 85, in _run_code
    exec(code, run_globals)
  File "/home/siecje/Desktop/py3structure/circular_py2/two.py", line 1, in <module>
    import three
ImportError: No module named 'three'
```

```shell
$ python -m circular_py3.two
Traceback (most recent call last):
  File "/usr/lib/python2.7/runpy.py", line 174, in _run_module_as_main
    "__main__", fname, loader, pkg_name)
  File "/usr/lib/python2.7/runpy.py", line 72, in _run_code
    exec code in run_globals
  File "/home/siecje/Desktop/py3structure/circular_py3/two.py", line 1, in <module>
    from . import three
  File "circular_py3/three.py", line 1, in <module>
    from . import one
  File "circular_py3/one.py", line 1, in <module>
    from . import three
ImportError: cannot import name three
$ python3 -m circular_py3.two
works
```

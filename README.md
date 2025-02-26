# uv-opencv-error

To reproduce the error, first build and run the default Dockerfile. You will get the following error:

```
Traceback (most recent call last):
  File "/app/main.py", line 1, in <module>
    import cv2
  File "/app/.venv/lib/python3.12/site-packages/cv2/__init__.py", line 181, in <module>
    bootstrap()
  File "/app/.venv/lib/python3.12/site-packages/cv2/__init__.py", line 153, in bootstrap
    native_module = importlib.import_module("cv2")
                    ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.12/importlib/__init__.py", line 90, in import_module
    return _bootstrap._gcd_import(name[level:], package, level)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
ImportError: libGL.so.1: cannot open shared object file: No such file or directory
```

But if `opencv-python-headless` dependency is installed manually via pip, the error does not occur. Build and run the `pip.Dockerfile` with the expected opencv version printed.


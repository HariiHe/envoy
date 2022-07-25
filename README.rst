Envoy: Python Subprocesses for Humans.
======================================

**Note:** `Delegator <https://github.com/kennethreitz/delegator.py>`_ 是Envoy的替代.

这是一个围绕“subprocess”模块的方便包装器.

你不需要这个.

.. image:: https://github.com/kennethreitz/envoy/raw/master/ext/in_action.png

但是你想要这个.


用法
-----

运行命令，获取结果::

    >>> r = envoy.run('git config', data='data to pipe in', timeout=2)

    >>> r.status_code
    129
    >>> r.std_out
    'usage: git config [options]'
    >>> r.std_err
    ''

运行::

    >>> r = envoy.run('uptime | pbcopy')

    >>> r.command
    'pbcopy'
    >>> r.status_code
    0

    >>> r.history
    [<Response 'uptime'>]

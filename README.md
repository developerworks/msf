最新Erlang发布包下载地址
https://www.erlang-solutions.com/downloads/download-erlang-otp

Rebar注意事项
-------------

1. BUG	https://github.com/basho/rebar/issues/213
2. 仔细阅读Getting Started,有版本问题 https://github.com/basho/rebar/wiki/Getting-started

修改Rebar模版
-------------

* 复制rebar源代码目录下priv/templates到
* Windows:	C:\Documents and Settings\Administrator\.rebar\templates
* Unix/Linux:	~/.rebar\templates
* 修改simplenode.reltool.config中

```erlang
{app, {{nodeid}}, [{mod_cond, app}, {incl_cond, include}]}
```

为
```erlang
{app, {{nodeid}}, [{mod_cond, app}, {incl_cond, include}, {lib_dir, ".."}]}
```

Shell脚本
-------------
```sh
mkdir msf
cd msf
wget http://cloud.github.com/downloads/basho/rebar/rebar && chmod u+x rebar
wget https://raw.github.com/developerworks/msf/master/rebar.config
rebar create-app appid=msf
mkdir rel
cd rel
../rebar create-node nodeid=msf
cd ..
rebar get-deps
rebar compile
rebar generate
```





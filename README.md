
最新Erlang发布包下载地址
https://www.erlang-solutions.com/downloads/download-erlang-otp


Rebar 注意事项

1. BUG
	https://github.com/basho/rebar/issues/213
2. 仔细阅读Getting Started, 有版本问题
	https://github.com/basho/rebar/wiki/Getting-startedi


Erlang 15B02

1. 复制rebar源代码目录下priv/templates到C:\Documents and Settings\Administrator\.rebar\templates

2. 修改simplenode.reltool.config中
    {app, {{nodeid}}, [{mod_cond, app}, {incl_cond, include}]}
	为
    {app, {{nodeid}}, [{mod_cond, app}, {incl_cond, include}, {lib_dir, ".."}]}

3. wget http://cloud.github.com/downloads/basho/rebar/rebar && chmod u+x rebar



mkdir msf
cd msf
wget http://cloud.github.com/downloads/basho/rebar/rebar && chmod u+x rebar
rebar



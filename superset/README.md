- superset/bin:

   该目录下的`superset`文件为程序的执行入口, 可以在项目根目录执行`python superset/bin/superset runserver`启动superset后台. 实际上调用了`superset/cli.py

- superset/connectors:

   superset的一些数据源, table的model和view, 可以理解为接入数据源相关的控制代码\

  

- superset/migration: 
  存放`superset database schema`升级和版本变迁, 所有的数据库修改都需要走migration, 升级的时候需要执行`superset db upgrade && superset db init`

- superset/models:

   存放superset的数据库模型, superset的核心逻辑如Slice, Dashboard都可以在这里找到. 可以理解为后端的模型代码都放在这边.

  `superset/static` 和 `superset/templates`: superset前端相关的模板, 控件代码全部在该目录下, 如果需要对superset的前端进行编译, 需要执行`npm run dev`, 编译后的前端代码不会出现本地代码后台启动后css没效果等情况.

- superset/views:

   放置superset所有的视图, 关于Slice, Dashboard和SQL Lab相关的展示, 查询, 存储, 下载等功能可以查看这里面的源码. 前端相关的交互, API都可以到views目录下查看.

- superset/__init__.py:

 这里包含了Flask APP, Flask AppBuilder, SQLAlchemy, 和Security Manager的启动工作, 启动了superset的视图, 数据库连接, 安全管理等.
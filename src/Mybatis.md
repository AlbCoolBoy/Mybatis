# Mybatis



## 原始JDBC

原始JDBC开发存在的问题如下：

1. 数据库连接创建、释放频繁造成系统资源浪费从而影响系统性能
2. sql语句在代码中硬编码，造成代码不易维护，实际应用sql变化的可能较大，sql变动需要改变java代码
3. 查询操作的时候，需要手动将结果集中的数据手动封装到实体中。插入操作的时候，需要手动将实体的数据设置到sql语句的占位符位置

应对上述问题的解决方案

1. 使用数据库连接池初始化链接资源
2. 将sql语句抽取到xml配置文件中
3. 使用反射、内省等底层技术，自动将实体与表进行属性与字段的自动映射



## Mybatis介绍

- mybatis是一个基于java的持久层框架，内部封装了jdbc，开发者只需要关注sql语句本身，不需要花费精力去处理加载驱动、创建连接、创建statement等繁杂的过程
- mybatis通过xml或注解的方式将要执行的各种statement配置起来，并通过java对象和statement中的sql动态参数进行映射生成最终执行的sql语句
- 最后mybatis框架执行sql并将结果映射为java对象返回。使用ORM思想解决了实体和数据库映射的问题，对jdbc进行了封装，屏蔽了jdbc api访问细节，使我们不得不与jdbc api打交道，就可以完成对数据库的持久化操作



## Mybatis开发步骤

1. 添加MyBatis坐标
2. 创建user数据表
3. 编写User实体类
4. 编写映射文件UseMapper.xml
5. 编写核心文件SqlMapConfig.xml
6. 编写测试类
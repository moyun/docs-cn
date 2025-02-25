---
title: TiDB 支持的第三方工具
aliases: ['/zh/tidb/dev/supported-by-pingcap']
---

# TiDB 支持的第三方工具

> **注意：**
>
> 本文档仅列举了常见的 TiDB 支持的第三方工具，未被列入其中的第三方工具并非代表不支持，但 PingCAP 无法了解其是否使用到 TiDB 不支持的特性，从而无法保证兼容性。

TiDB [高度兼容 MySQL 协议](/mysql-compatibility.md)，使得大部分适配 MySQL 的 Driver、ORM 及其他工具与 TiDB 兼容。本文主要介绍这些工具和它们的支持等级。

## 支持等级

PingCAP 与开源社区合作，通过三方工具提供以下支持：

- Full：表明 PingCAP 已经支持该工具的绝大多数功能兼容性，并且在新版本中对其保持兼容，将定期地对下表中记录的新版本进行兼容性测试。
- Compatible：表明由于该工具已适配 MySQL，而 TiDB 高度兼容 MySQL 协议，因此可以使用此工具的大部分功能。但 PingCAP 并未对该工具作出完整的兼容性验证，有可能出现一些意外的行为。

> **注意：**
>
> 除非明确说明，否则对于支持的 Driver 或者 ORM 框架并不包括[应用端事务重试和错误处理](/develop/dev-guide-transaction-troubleshoot.md#应用端重试和错误处理)。

如果在使用本文列出的工具连接 TiDB 时出现问题，请在 GitHub 上提交包含详细信息的 [issue](https://github.com/pingcap/tidb/issues/new?assignees=&labels=type%2Fquestion&template=general-question.md)，以帮助在此工具的支持上得到进展。

## Driver

| 编程语言 | 驱动 | 最新已测试版本 | 支持等级 | TiDB 适配器 | 教程 |
| - | - | - | - | - | - |
| C | [libmysqlclient](https://dev.mysql.com/doc/c-api/8.0/en/c-api-introduction.html) | 8.0 | Compatible | N/A | N/A |
| C#(.Net) | [MySQL Connector/NET](https://downloads.mysql.com/archives/c-net/) | 8.0 | Compatible | N/A | N/A |
| ODBC | [MySQL Connector/ODBC](https://downloads.mysql.com/archives/c-odbc/) | 8.0 | Compatible | N/A | N/A |
| Go | [go-sql-driver/mysql](https://github.com/go-sql-driver/mysql) | v1.6.0 | Full | N/A | [TiDB 和 Golang 的简单 CRUD 应用程序](/develop/dev-guide-sample-application-golang.md) |
| Java | [JDBC](https://dev.mysql.com/downloads/connector/j/) | 8.0 | Full | <ul><li><a href="/develop/dev-guide-choose-driver-or-orm.md#java-drivers">pingcap/mysql-connector-j</a></li> <li><a href="/develop/dev-guide-choose-driver-or-orm.md#tidb-loadbalance">pingcap/tidb-loadbalance</a></li></ul> | [TiDB 和 Java 的简单 CRUD 应用程序](/develop/dev-guide-sample-application-java.md) |
| JavaScript | [mysql](https://github.com/mysqljs/mysql) | v2.18.1 | Compatible | N/A | N/A |
| PHP | [mysqlnd](https://dev.mysql.com/downloads/connector/php-mysqlnd/) | PHP 5.4+ | Compatible | N/A | N/A |
| Python | [MySQL Connector/Python](https://downloads.mysql.com/archives/c-python/) | 8.0 | Compatible | N/A | N/A |

## ORM

<table>
   <thead>
      <tr>
         <th>编程语言</th>
         <th>ORM 框架</th>
         <th>最新已测试版本</th>
         <th>支持等级</th>
         <th>TiDB 适配器</th>
         <th>教程</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td rowspan="5">Go</td>
         <td><a href="https://github.com/go-gorm/gorm" target="_blank" referrerpolicy="no-referrer-when-downgrade">gorm</a></td>
         <td>v1.23.5</td>
         <td>Full</td>
         <td>N/A</td>
         <td><a href="/tidb/dev/dev-guide-sample-application-golang">Build a Simple CRUD App with TiDB and Golang</a></td>
      </tr>
      <tr>
         <td><a href="https://github.com/beego/beego" target="_blank" referrerpolicy="no-referrer-when-downgrade">beego</a></td>
         <td>v2.0.3</td>
         <td>Full</td>
         <td>N/A</td>
         <td>N/A</td>
      </tr>
      <tr>
         <td><a href="https://github.com/upper/db" target="_blank" referrerpolicy="no-referrer-when-downgrade">upper/db</a></td>
         <td>v4.5.2</td>
         <td>Full</td>
         <td>N/A</td>
         <td>N/A</td>
      </tr>
      <tr>
         <td><a href="https://gitea.com/xorm/xorm" target="_blank" referrerpolicy="no-referrer-when-downgrade">xorm</a></td>
         <td>v1.3.1</td>
         <td>Full</td>
         <td>N/A</td>
         <td>N/A</td>
      </tr>
      <tr>
         <td><a href="https://github.com/ent/ent" target="_blank" referrerpolicy="no-referrer-when-downgrade">ent</a></td>
         <td>v0.11.0</td>
         <td>Compatible</td>
         <td>N/A</td>
         <td>N/A</td>
      </tr>
      <tr>
         <td rowspan="4">Java</td>
         <td><a href="https://hibernate.org/orm/" target="_blank" referrerpolicy="no-referrer-when-downgrade">Hibernate</a></td>
         <td>6.1.0.Final</td>
         <td>Full</td>
         <td>N/A</td>
         <td><a href="/tidb/dev/dev-guide-sample-application-java">Build a Simple CRUD App with TiDB and Java</a></td>
      </tr>
      <tr>
         <td><a href="https://mybatis.org/mybatis-3/" target="_blank" referrerpolicy="no-referrer-when-downgrade">MyBatis</a></td>
         <td>v3.5.10</td>
         <td>Full</td>
         <td>N/A</td>
         <td><a href="/tidb/dev/dev-guide-sample-application-java">Build a Simple CRUD App with TiDB and Java</a></td>
      </tr>
      <tr>
         <td><a href="https://spring.io/projects/spring-data-jpa/" target="_blank" referrerpolicy="no-referrer-when-downgrade">Spring Data JPA</a></td>
         <td>2.7.2</td>
         <td>Full</td>
         <td>N/A</td>
         <td><a href="/tidb/dev/dev-guide-sample-application-spring-boot">Build a TiDB Application Using Spring Boot</a></td>
      </tr>
      <tr>
         <td><a href="https://github.com/jOOQ/jOOQ" target="_blank" referrerpolicy="no-referrer-when-downgrade">jOOQ</a></td>
         <td>v3.16.7 (Open Source)</td>
         <td>Full</td>
         <td>N/A</td>
         <td>N/A</td>
      </tr>
      <tr>
         <td>Ruby</td>
         <td><a href="https://guides.rubyonrails.org/active_record_basics.html" target="_blank" referrerpolicy="no-referrer-when-downgrade">Active Record</a></td>
         <td>v7.0</td>
         <td>Full</td>
         <td>N/A</td>
         <td>N/A</td>
      </tr>
      <tr>
         <td rowspan="4">JavaScript / TypeScript</td>
         <td><a href="https://www.npmjs.com/package/sequelize" target="_blank" referrerpolicy="no-referrer-when-downgrade">sequelize</a></td>
         <td>v6.20.1</td>
         <td>Compatible</td>
         <td>N/A</td>
         <td>N/A</td>
      </tr>
      <tr>
         <td><a href="https://knexjs.org/" target="_blank" referrerpolicy="no-referrer-when-downgrade">Knex.js</a></td>
         <td>v1.0.7</td>
         <td>Compatible</td>
         <td>N/A</td>
         <td>N/A</td>
      </tr>
      <tr>
         <td><a href="https://www.prisma.io/" target="_blank" referrerpolicy="no-referrer-when-downgrade">Prisma Client</a></td>
         <td>3.15.1</td>
         <td>Compatible</td>
         <td>N/A</td>
         <td>N/A</td>
      </tr>
      <tr>
         <td><a href="https://www.npmjs.com/package/typeorm" target="_blank" referrerpolicy="no-referrer-when-downgrade">TypeORM</a></td>
         <td>v0.3.6</td>
         <td>Compatible</td>
         <td>N/A</td>
         <td>N/A</td>
      </tr>
      <tr>
         <td>PHP</td>
         <td><a href="https://laravel.com/" target="_blank" referrerpolicy="no-referrer-when-downgrade">laravel</a></td>
         <td>v9.1.10</td>
         <td>Compatible</td>
         <td><a href="https://github.com/colopl/laravel-tidb" target="_blank" referrerpolicy="no-referrer-when-downgrade">laravel-tidb</a></td>
         <td>N/A</td>
      </tr>
      <tr>
         <td rowspan="4">Python</td>
         <td><a href="https://pypi.org/project/Django/" target="_blank" referrerpolicy="no-referrer-when-downgrade">Django</a></td>
         <td>v4.0.5</td>
         <td>Compatible</td>
         <td><a href="https://github.com/pingcap/django-tidb" target="_blank" referrerpolicy="no-referrer-when-downgrade">django-tidb</a></td>
         <td>N/A</td>
      </tr>
      <tr>
         <td><a href="https://github.com/coleifer/peewee/" target="_blank" referrerpolicy="no-referrer-when-downgrade">peewee</a></td>
         <td>v3.14.10</td>
         <td>Compatible</td>
         <td>N/A</td>
         <td>N/A</td>
      </tr>
      <tr>
         <td><a href="https://ponyorm.org/" target="_blank" referrerpolicy="no-referrer-when-downgrade">PonyORM</a></td>
         <td>v0.7.16</td>
         <td>Compatible</td>
         <td>N/A</td>
         <td>N/A</td>
      </tr>
      <tr>
         <td><a href="https://www.sqlalchemy.org/" target="_blank" referrerpolicy="no-referrer-when-downgrade">SQLAlchemy</a></td>
         <td>v1.4.37</td>
         <td>Compatible</td>
         <td>N/A</td>
         <td>N/A</td>
      </tr>
   </tbody>
</table>

## GUI

| GUI | 最新已测试版本 | 支持等级 | 教程 |
| - | - | - | - |
| [DBeaver](https://dbeaver.io/) | 22.1.0 | Compatible | N/A |
| [Navicat for MySQL](https://www.navicat.com/) | 16.0.14 | Compatible | N/A |
| [MySQL Workbench](https://www.mysql.com/products/workbench/) | 8.0 | Compatible | N/A |

<table>
   <thead>
      <tr>
         <th>IDE</th>
         <th>插件</th>
         <th>支持等级</th>
         <th>教程</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><a href="https://www.jetbrains.com/datagrip/" target="_blank" referrerpolicy="no-referrer-when-downgrade">DataGrip</a></td>
         <td>N/A</td>
         <td>Compatible</td>
         <td>N/A</td>
      </tr>
      <tr>
         <td><a href="https://www.jetbrains.com/idea/" target="_blank" referrerpolicy="no-referrer-when-downgrade">IntelliJ IDEA</a></td>
         <td>N/A</td>
         <td>Compatible</td>
         <td>N/A</td>
      </tr>
      <tr>
         <td rowspan="2"><a href="https://code.visualstudio.com/" target="_blank" referrerpolicy="no-referrer-when-downgrade">Visual Studio Code</a></td>
         <td><a href="https://marketplace.visualstudio.com/items?itemName=dragonly.ticode" target="_blank" referrerpolicy="no-referrer-when-downgrade">TiDE</a></td>
         <td>Compatible</td>
         <td>N/A</td>
      </tr>
      <tr>
         <td><a href="https://marketplace.visualstudio.com/items?itemName=formulahendry.vscode-mysql" target="_blank" referrerpolicy="no-referrer-when-downgrade">MySQL</a></td>
         <td>Compatible</td>
         <td>N/A</td>
      </tr>
   </tbody>
</table>

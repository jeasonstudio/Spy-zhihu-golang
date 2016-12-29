# Spy-zhihu-golang
A Spyder of zhihu with golang by Jeason


安装依赖：

```golang
go get github.com/Go-SQL-Driver/MySQL
go get  github.com/bitly/go-simplejson
```

修改数据库相关配置：

```go
const (
	username   = "root"
	password   = "root"
	ip         = "127.0.0.1"
	port       = "8889"
	db_name    = "zhihu_user"
	table_name = "user"
)
```

执行下面语句建库：

```SQL
USE zhihu_user;
CREATE TABLE IF NOT EXISTS `user` (
  `my_id` int(20) NOT NULL AUTO_INCREMENT,
  `name` varchar(255) DEFAULT NULL,
  `is_followed` boolean DEFAULT FALSE,
  `avatar_url_template` varchar(255) DEFAULT NULL,
  `url` varchar(255) DEFAULT NULL,
  `user_type` varchar(255) DEFAULT NULL,
  `answer_count` int(255) DEFAULT 0,
  `url_token` varchar(255) DEFAULT NULL,
  `is_advertiser` boolean DEFAULT FALSE,
  `avatar_url` varchar(255) DEFAULT NULL,
  `is_following` boolean DEFAULT FALSE,
  `is_org` boolean DEFAULT FALSE,
  `headline` varchar(255) DEFAULT NULL,
  `follower_count` varchar(255) DEFAULT NULL,
  `the_type` varchar(255) DEFAULT NULL,
  `id` varchar(255) DEFAULT NULL,
  `articles_count` int(255) DEFAULT NULL,
  PRIMARY KEY (`my_id`)
) ENGINE=InnoDB  DEFAULT CHARSET=utf8 AUTO_INCREMENT=3 ;
```

开始爬取：

```go
go run main.go
```

终止：

```shell
ctrl + C
```

TODO:

 - 优化爬虫效率
 - 防重复爬取
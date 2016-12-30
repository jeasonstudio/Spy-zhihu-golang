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
    `id` varchar(255) unique,
    `name` varchar(255) DEFAULT NULL,
    `headline` varchar(255) DEFAULT NULL,
    `is_followed` boolean DEFAULT FALSE,
    `following_count` int(100) DEFAULT 0,
    `description` varchar(255) DEFAULT NULL,
    `the_type` varchar(100) DEFAULT NULL,
    `thank_from_count` int(100) DEFAULT 0,
    `marked_answers_count` int(100) DEFAULT 0,
    `show_sina_weibo` boolean DEFAULT FALSE,
    `pins_count` int(100) DEFAULT 0,
    `following_question_count` int(100) DEFAULT 0,
    `thanked_count` int(100) DEFAULT 0,
    `avatar_url_template` varchar(255) DEFAULT NULL,
    `marked_answers_text` varchar(255) DEFAULT NULL,
    `logs_count` int(100) DEFAULT 0,
    `hosted_live_count` int(100) DEFAULT 0,
    `favorite_count` int(100) DEFAULT 0,
    `voteup_count` int(100) DEFAULT 0,
    `commercial_question_count` int(100) DEFAULT 0,
    `following_columns_count` int(100) DEFAULT 0,
    `is_blocking` boolean DEFAULT FALSE,
    `is_force_renamed` boolean DEFAULT FALSE,
    `thank_to_count` int(100) DEFAULT 0,
    `participated_live_count` int(100) DEFAULT 0,
    `following_favlists_count` int(100) DEFAULT 0,
    `favorited_count` int(100) DEFAULT 0,
    `allow_message` boolean DEFAULT FALSE,
    `is_active` int(100) DEFAULT 0,
    `is_blocked` boolean DEFAULT FALSE,
    `mutual_followees_count` int(100) DEFAULT 0,
    `following_topic_count` int(100) DEFAULT 0,
    `gender` int(100) DEFAULT 0,
    `vote_from_count` int(100) DEFAULT 0,
    `vote_to_count` int(100) DEFAULT 0,
    `message_thread_token` varchar(255) DEFAULT NULL,
    `url` varchar(255) DEFAULT NULL,
    `user_type` varchar(255) DEFAULT NULL,
    `answer_count` int(100) DEFAULT 0,
    `url_token` varchar(255) DEFAULT NULL,
    `is_advertiser` boolean DEFAULT FALSE,
    `avatar_url` varchar(255) DEFAULT NULL,
    `is_following` boolean DEFAULT FALSE,
    `is_org` boolean DEFAULT FALSE,
    `follower_count` int(100) DEFAULT 0,
    `articles_count` int(100) DEFAULT 0,
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
 - ~~防重复爬取~~
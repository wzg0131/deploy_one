# deploy_one
## 脚本说明
### 全新系统
1. `sudo ./deploy_one_cloud.sh ip port`
### php老数据迁移
1. `sudo ./deploy_one_cloud.sh ip port`
2. 挂载旧数据(`uploads` 和 `database`)
3. `sudo ./unserialize_ccloud.sh`

## 修改记录
> ***2020年3月20日***
>> `application.yml`
>>> - 增加`device.report.time`
>>> - 增加`request.check.timeout`
>>> - 修改日志级别

>> unserialize
>>> - 增加将_terminal_group和_terminal_led解析到新的节目关系表(wp_group_program,wp_terminal_program)的脚本
>>> - `unserialize/ccloud_parse_program_relationships_table.php`
>>> - `unserialize/spring_parse_program_relationships_table.php`

>> db_spring
>>> `db_spring/fetch_unserialize_ccloud.sql`增加节目关系表的创建
>>> `db_spring/spring.sql`增加节目关系表的创建

>> `deploy_one_cloud.sh`
>>> 增加解析节目关系的语句

>> `unserialize_ccloud.sh`
>>> 增加解析节目关系的语句

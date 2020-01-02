# Jeecg-database OA系统数据库自动备份

#### Description
备份鹏程晟泰OA系统数据库信息

#### Tips
每小时自动备份一次

#### Account
root/********

#### IP
`***.she****i.c***`

#### 备份脚本
```
SHELL=/bin/bash
PATH=/sbin:/bin:/usr/sbin:/usr/bin
MAILTO=root

# For details see man 4 crontabs

# Example of job definition:
# .---------------- minute (0 - 59)
# |  .------------- hour (0 - 23)
# |  |  .---------- day of month (1 - 31)
# |  |  |  .------- month (1 - 12) OR jan,feb,mar,apr ...
# |  |  |  |  .---- day of week (0 - 6) (Sunday=0 or 7) OR sun,mon,tue,wed,thu,fri,sat
# |  |  |  |  |
# *  *  *  *  * user-name  command to be executed

 0 */1 * * sun-sat root /usr/local/bin/mysqlbkup.sh 1>>/var/log/mysqlbkup.log 2>>/var/log/mysqlbkup-err.log
 0 */1 * * *       root /var/mysqlbkup/jeecg/start.sh

```
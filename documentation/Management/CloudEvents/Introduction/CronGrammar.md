# Cron 语法说明

京东云云事件的使用的是crontab语法规则

## 1.语法数字范围说明
| 时间项 | 分钟 | 小时 | 日 | 月 | 周 | 命令项 |
|-|-|-|-|-|-|-|
| 数值范围 | 0-59 | 0-23 | 1-31 | 1-12 | 0-7（0，7都代表周日） | 该项用户无需填写 |

## 2.特殊字符含义说明
| 特殊字符 | 含义说明 |
|-|-|
| *(星号) | 代表任何时刻都接受的意思。举例来说，`0 18 * * *` ，日、月、周都是*，就代表着不论何月、何日的礼拜几的18：00都执行指定命令的意思。 |
| ,(逗号) | 代表分隔时段的意思。举例来说，如果要执行的工作是3：00与6：00时，就会是：`0 2,8 * * *` ，时间还是有五列，不过第二列是 2,8 ，代表2与8都适用 |
| -(减号) | 代表一段时间范围内，举例来说，6点到8点之间的每小时的10分都进行一项工作：`10 6-8 * * *` ，仔细看到第二列变成6-8.代表 6,7,8 都适用的意思 |
| /n(斜线) | n代表数字，即是每隔n单位间隔的意思，例如每五分钟进行一次，则：`*/5 * * * *` ，用*与/5来搭配，也可以写成0-59/10，意思相同 |

## 3.举例说明

（1）每X分钟定时执行一次规则
- 每1分钟执行： `*/1 * * * *`或者`* * * * *`
- 每5分钟执行： `*/5 * * * *`

(2)每X小时定时执行一次规则：
- 每1小时执行： `0 * * * *`或者`0 */1 * * *`
- 每天上午9点执行：`0 9 * * *`
- 每天上午9点30分执行：`30 9 * * *`

(3)每X天定时执行一次规则：
- 每天执行 `0 0 * * *`

(4)每X周定时执行一次规则：
- 每周执行 `0 0 * * 0`

(5)每月定时执行一次规则：
- 每月1日执行 `0 0 1 * *`

(6)每年定时执行一次规则：
- 每年的1月1日执行 `0 0 1 1 *`

(7)其他
- 每天下午14：30执行一次： `30 14 * * *`
- 每月5号和15号的9:45执行一次： `45 9 5,15 * *`
- 每天14-16点的第30分钟执行： `30 14-16 * * *`
- 指定每星期三的9:30执行命令： `30 9 * * 3` （注：0和7表示星期天，1表示星期1，以此类推，也可以用英文来表示，sun表示星期天，mon表示星期一等。）



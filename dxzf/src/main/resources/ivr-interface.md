## GetIvrOption

* URL:/interface/ivr/GetIvrOption
* Method:GET
* Content type: application/json
* 输入参数：

| 参数名         | 是否必填 | 数据类型 | 说明                      |
| -------------- | -------- | -------- | ------------------------- |
| gwIp           | 是       | String   | 呼叫来源IP eg.10.10.3.235 |
| numberTrunk    | 是       | String   | 中继号码 eg.80206528      |
| customerNumber | 是       | String   | 客户号码 eg.18800101027   |
| callType       | 是       | String   | 呼叫类型 eg.1             |
| webcallIvrId   | 是       | String   | web呼叫IVR ID             |
| enterpriseId   | 是       | String   | 企业ID                    |

* 返回结果：

| 字段                       | 数据类型     | 说明                                                    |
| -------------------------- | ------------ | ------------------------------------------------------- |
| __cdr_customer_number      | string       | cdr客户号码 eg."18800101027"                            |
| __cdr_customer_number_type | String       | cdr客户号码类型 eg.2                                    |
| __cdr_customer_area_code   | String       | cdr客户号码区号 eg."010"                                |
| number_trunk_area_code     | String       | 中继号码区号 eg."021"                                   |
| __enterprise_id            | String       | 企业ID eg."5000000"                                     |
| cdr_hotline                | String       | cdr热线号码 eg."02180206528"                            |
| enterprise_call_limit_ib   | String       | 企业呼入限制 eg.200                                     |
| enterprise_status          | String       | 企业状态标志 eg.1                                       |
| is_restrict_check          | String       | 是否检查黑名单,调用`CheckBlackList`接口 eg."1"          |
| is_record                  | String       | 是否录音 eg."1"                                         |
| ~~                         | record_scope | String                                                  | eg."1" | ~~ |
| is_dual_record_open        | String       | 开启双轨录音(`Monitor`)或者禁止(`MixMonitor`) eg."1"    |
| is_crbt_open               | String       | 是否开启彩铃 eg."1"                                     |
| is_asr_transfer_open       | String       | 是否开启asr功能 eg."0"                                  |
| ivr_router_type            | String       | ivr路由类型 取值`1`转入ivr `2`转固定电话 `3`转分机 eg.1 |
| __ivr_id                   | String       | ivr ID eg."10"                                          |
| valid_ivr                  | String       | ivr使能有效标志 eg."1"                                  |

realtime模块，提供HTTP接口，支持GET和POST请求方式。
# 目录
[1.Identify](realtime接口.md#1.identify接口)  
## realTime模块
### 1.Identify接口 
#### multi

- URL 格式: `http://${host}/interface/realtime/identify/multi`
- 参数:
    | 字段          | 可选 | 描述                                |
    | ------------ | ---- | ------------------------------------|
    | id           | 必选 | 网关ip地址或网关名称                    |
- 返回:
  - String格式数

  | 字段          | 可选 | 描述                                 |
  | ------------ | ---- | ------------------------------------|
  | id           | 必选 | 等同于网关名称                         |
  | type         | 必选 | 固定为identify                        |
  | endpoint     | 必选 | 等同于网关名称                         |
  | match        | 必选 | 等同于网关ip地址                       |
  - 示例: `id=gateway.1&type=identify&endpoint=gateway.1&match_header=P-Tinet-Identify-Endpoint: gateway.1`
  


#### single

- URL 格式: `http://${host}/interface/realtime/identify/single,id=10.10.5.157`
- 参数:
    | 字段          | 可选 | 描述                                 |
    | ------------ | ---- | ------------------------------------|
    | id           | 必选 | 网关ip地址或网关名称                    |
- 返回:
  - String格式数

  | 字段          | 可选 | 描述                                  |
  | ------------ | ---- | ------------------------------------ |
  | id           | 必选 | 等同于网关名称                          |
  | type         | 必选 | 固定为identify                         |
  | endpoint     | 必选 | 等同于网关名称                          |
  | match        | 必选 | 等同于网关ip地址                        |
  - 示例: `id=gateway.1&type=identify&endpoint=gateway.1&match_header=P-Tinet-Identify-Endpoint: gateway.1`

### 2.Moh接口
#### multi

- URL 格式: `http://${host}/interface/realtime/moh/multi`
- 参数:
    | 字段          | 可选 | 描述                                |
    | ------------ | ---- | ------------------------------------|
    | name         | 必选 | 类名 格式：企业号+类名                |
- 返回:
  - String格式数

  | 字段          | 可选 | 描述                                 |
  | ------------ | ---- | ------------------------------------|
  | name         | 必选 | 类名 格式：企业号+类名                   |
  | mode         | 必选 | 模式                                  |
  | directory    | 必选 | 频文件的路径                           |
  


#### single

- URL 格式: `http://${host}/interface/realtime/moh/single`
- 参数:
    | 字段          | 可选 | 描述                                   |
    | ------------ | ---- | --------------------------------------|
    | name         | 必选 | 类名 格式：企业号+类名                    |
- 返回:
  - String格式数

  | 字段         | 可选 | 描述                                      |
  | ------------ | ---- | ----------------------------------------|
  | name         | 必选 | 类名 格式：企业号+类名                      |
  | mode         | 必选 | 模式                                     |
  | directory    | 必选 | 频文件的路径                               |

### 3.SipUsers接口
#### multi

- URL 格式: `http://${host}/interface/realtime/sipUsers/multi`
- 参数:
    | 字段          | 可选 | 描述                                |
    | ------------ | ---- | ------------------------------------|
    | name         | 必选 | ip地址或网关名称              |
- 返回:
  - String格式数

  | 字段          | 可选 | 描述                                 |
  | ------------ | ---- | ------------------------------------|
  | name         | 必选 | 当参数name是ip地址时该值等同于name,否则该值等同于网关名称|
  | type         | 必选 | 类型,固定为friend                       |
  | host         | 必选 | 域名,等同于ip地址                        |
  | context      | 必选 | 固定为default                           |
  | call-limit   | 必选 | 网关吞吐能力                             |
  | ipaddr       | 必选 | 网关ip地址                              |
  | port         | 必选 | sip信令端口                             |
  | disallow     | 必选 | 网关codec选择disallow                   |
  | allow        | 必选 | 网关codec选择allow                      |
  | dtmf_mode    | 必选 | 网关的dtmf设置 rfc2833/info/auto/inband |
  | change       | 必选 | 是否变更,1表示变更,0表示未变更             |
  


#### single
- URL 格式: `http://${host}/interface/realtime/sipUsers/multi`
- 参数:
    | 字段          | 可选 | 描述                                |
    | ------------ | ---- | ------------------------------------|
    | name         | 必选 | ip地址或网关名称              |
- 返回:
  - String格式数

  | 字段          | 可选 | 描述                                 |
  | ------------ | ---- | ------------------------------------|
  | name         | 必选 | 当参数name是ip地址时该值等同于name,否则该值等同于网关名称|
  | type         | 必选 | 类型,固定为friend                       |
  | host         | 必选 | 域名,等同于ip地址                        |
  | context      | 必选 | 固定为default                           |
  | call-limit   | 必选 | 网关吞吐能力                             |
  | ipaddr       | 必选 | 网关ip地址                              |
  | port         | 必选 | sip信令端口                             |
  | disallow     | 必选 | 网关codec选择disallow                   |
  | allow        | 必选 | 网关codec选择allow                      |
  | dtmf_mode    | 必选 | 网关的dtmf设置 rfc2833/info/auto/inband |
  | change       | 必选 | 是否变更,1表示变更,0表示未变更             |
  
### 4.EndPoint接口
#### multi

- URL 格式: `http://${host}/interface/realtime/endpoint/multi`
- 参数:
    | 字段          | 可选 | 描述                                |
    | ------------ | ---- | ------------------------------------|
    | id           | 必选  | ip地址或网关名称                       |
- 返回:
  - String格式数

  | 字段                 | 可选 | 描述                                   |
  | ------------        | ---- | ------------------------------------  |
  | id                  | 必选 | 网关名称                                |
  | type                | 必选 | 固定为endpoint                          |
  | transport           | 必选 | 固定为transport-udp-nat                 |
  | context             | 必选 | 固定为default                           |
  | disallow            | 必选 | 网关codec选择disallow                   |
  | allow               | 必选 | 网关codec选择allow                      |
  | dtmf_mode           | 必选 | 网关的dtmf 设置 rfc2833/info/auto/inband |
  | device_state_busy_at| 必选 | 等同于网关吞吐能力                        |
  | rtp_keepalive       | 必选 | 固定为60                                |
  | rtp_timeout         | 必选 | 固定为60                                |
  | rtp_timeout_hold    | 必选 | 固定为60                                |
  | timers              | 必选 | 固定为no                                |
  


#### single
- URL 格式: `http://${host}/interface/realtime/endpoint/multi`

- 参数:
    | 字段          | 可选 | 描述                                |
    | ------------ | ---- | ------------------------------------|
    | id           | 必选 | ip地址或网关名称                      |
- 返回:
  - String格式数

  | 字段                 | 可选 | 描述                                   |
  | ------------        | ---- | ------------------------------------  |
  | id                  | 必选 | 网关名称                                |
  | type                | 必选 | 固定为endpoint                          |
  | transport           | 必选 | 固定为transport-udp-nat                 |
  | context             | 必选 | 固定为default                           |
  | disallow            | 必选 | 网关codec选择disallow                   |
  | allow               | 必选 | 网关codec选择allow                      |
  | dtmf_mode           | 必选 | 网关的dtmf 设置 rfc2833/info/auto/inband |
  | device_state_busy_at| 必选 | 等同于网关吞吐能力                        |
  | rtp_keepalive       | 必选 | 固定为60                                |
  | rtp_timeout         | 必选 | 固定为60                                |
  | rtp_timeout_hold    | 必选 | 固定为60                                |
  | timers             | 必选 | 固定为no                                |

## IVR模块
### 1.GetPrePost接口

- URL 格式: `http://${host}/interface/ivr/GetPrePost`

- 参数:
    | 字段                | 可选 | 描述                         |
    | ------------      | ---- | -----------------------------|
    | enterpriseId      | 必选 | 通道中的企业id                  |
    | tel               | 必选 | 号码                          |
    | routerClidCallType| 必选 | clid类型                      |
- 返回:
  - json字符串格式数据

  | 字段                 | 可选 | 描述                                 |
  | --------------------|---- | ------------------------------------ |
  | pre                 | 必选 | 号码前缀                              |
  | post                | 必选 | 等同于网关名称                         |
  | gw_ip               | 必选 | 网关ip地址                            |
  | gw_port             | 必选 | sip信令端口                           |
  | cdr_callee_area_code| 必选 | 区号                                 |
  | dial_interface_cust | 必选 |                                     |
  
### 2.CheckBlackList接口

- URL 格式: `http://${host}/interface/ivr/CheckBlackList`

- 参数:
    | 字段               | 可选 | 描述                         |
    | ----------------- | ---- | -----------------------------|
    | enterpriseId      | 必选 | 通道中的企业id                  |
    | customerNumber    | 必选 | 当期呼入号码                    |
    | customerAreaCode  | 必选 | 地区区号                       |
- 返回:
  - json字符串格式数据

  | 字段                  | 可选 | 描述                                   |
  | ------------          | ---- | ------------------------------------  |
  | is_restrict_tel       | 必选 | 是否在黑名单/不在白名单中,只有可能为1或者2|

### 3.GetIvrOption接口

- URL 格式: `http://${host}/interface/ivr/GetIvrOption`

- 参数:
    | 字段                | 可选 | 描述                         |
    | ------------      | ---- | ----------------------------- |
    | numberTrunk      | 可选 | 传入的中继绑定的号码                |
    | customerNumber    | 必选 | 当期呼入号码                   |
    | gwIp  | 必选 | 网关ip地址                              |
    | callType  | 必选 | 呼叫类型,呼入和网上400呼入           |
    | webcallIvrId  | 必选 | 网上400接口使用的ivrId            |
    | enterpriseId  | 可选 | 企业id                         |
- 返回:
  - json字符串格式数据

  | 字段                  | 可选 | 描述                                   |
  | ------------          | ---- | ------------------------------------  |
  | __cdr_customer_number       | 必选 | 客户号码    |
  | __cdr_customer_number_type       | 必选 | 客户号码类型    |
  | __cdr_customer_area_code       | 必选 | 号码区号    |
  | number_trunk_area_code       | 可选 | trunk号码区号,当numberTrunk为空时无该字段 |
  | enterprise_status       | 可选 | 企业中继状态,当enterpriseId为空时固定为0,否则没有该字段,0:未开通 1:正常 2:欠费 3:停机 4:注销 |
  | __enterprise_id       | 可选 | 企业id,当enterprise_id不为空时等同于enterpriseId |
  | __cdr_hotline       | 可选 | 热线号码,根据numberTrunk获取hotline，当numberTrunk对应的hotline不存在时，用numberTrunk区号+numberTrunk代替 |
  | is_restrict_check       | 可选 | 是否开启了黑白名单功能,如果enterprise_id对应的企业开启了黑白名功能,则该字段值为1 |
  | is_record       | 可选 |是否开启了录音功能,如果enterpriseId对应的企业开启了录音功能,则该值为1|
  | record_scope       | 可选 |通道变量:is_ob_record  外呼是否录音 0--不录音 ，1--录音,当对应的企业开启了录音功能时该值为1|
  | is_crbt_open       | 可选 |是否开启了录音功能,如果enterprise_id对应的企业开启了彩铃功能,则该值为1|
  | is_asr_transfer_open | 可选 |是否开启ASR 0关闭 1 阿里 2 科大讯飞,当redis中存在enterprise_id对应的企业的asr配置时该字段存在|
  | is_double_channel_record_open | 可选 |是否开启双声道录音,0关闭,1开启,当redis中存在enterprise_id对应企业的双声道录音配置时该字段存在|
  | __ivr_id | 可选 |通道变量,当callType为2即为网上400呼入类型并且webcallIvrId不为空时该值等同于webcallIvrId,当webcallIvrId为空时参照enterprise_id对应的企业对该字段的设置|

### 4.IsClidValid接口

- URL 格式: `http://${host}/interface/ivr/IsClidValid`

- 参数:
    | 字段                | 可选 | 描述                         |
    | ------------      | ---- | ----------------------------- |
    | appId      | 必选 | 企业id                    |
    | clid       | 必选 | 需要验证的clid              |
- 返回:
  - json字符串格式数据

  | 字段                  | 可选 | 描述                                   |
  | ------------          | ---- | ------------------------------------  |
  | clidResult       | 可选 | 验证结果状态信息 1 有效,0无效,只有当clid合法时才有该字段 |
  | result           | 可选 | 验证结果错误状态信息,当clid为空时该值为false,只有当clidResult不合法时才有该字段 |
  | description      | 可选 | 验证结果错误描述信息,当clid不合法时才有该字段,当clid为空时该值为"提交失败，clid不能为空",当clid不是数字时,该值为"提交失败，参数clid格式不正确" |
  
 ### 5.IsTelNumber接口

- URL 格式: `http://${host}/interface/ivr/IsTelNumber`

- 参数:
    | 字段               | 可选  | 描述                          |
    | ------------      | ---- | ---------------------------- |
    | tel               | 必选  | 需要验证的号码                  |
- 返回:
  - json字符串格式数据

  | 字段                  | 可选 | 描述                                    |
  | ------------         | ---- | ------------------------------------  |
  | result               | 必选 | 当tel符合规则时该值为1,否则为0             |
  | description          | 必选 | 描述信息,当tel为空时该值为"提交失败，tel不能为空";"当tel不为数字或号码正则不匹配tel时该值为"提交失败，参数tel格式不正确";当号码正则匹配tel时,该值为"号码正则不匹配tel"|
  
 ### 6.GetPastCalleeNumber接口

 - URL 格式: `http://${host}/interface/ivr/GetPastCalleeNumber`
 - 参数:
     | 字段              | 可选 |            描述                |
     | ------------     | ---- | ----------------------------- |
     | appId            | 必选 | 通道里面的企业ID                 |
     | validTime        | 必选 | 主叫记忆时间                     |
     | cdrType          | 必选 | 记忆类型                        |
     | callerNumber     | 必选 | 来电号码                        |
 - 返回:
   - json字符串格式数据

   | 字段                    | 可选 | 描述                                   |
   | ------------           | ---- | ------------------------------------  |
   | result                 | 必选 | 请求结果状态信息,只有可能为1或0              |
   | cdrType                | 必选 | 只有可能为inbound或outbound或both        |
   | validTime              | 必选 | 主叫记忆时间                             |
   | calleeNumber           | 必选 | 呼叫号码                                |
   | description            | 必选 | 结果描述信息                             |

 ### 7.AllModuleStarted接口

 - URL 格式: `http://${host}/interface/system/AllModuleStarted`

 - 参数:
     | 字段               | 可选 | 描述                         |
     | ------------      | ---- | ----------------------------- |
 - 返回:
   - json字符串格式数据

   | 字段                   | 可选 | 描述                                   |
   | ------------          | ---- | ------------------------------------  |
   | allModuleStarted      | 可选 | 所有模块是否已加载 true,如果未加载,则报404错误 |
   
 ### 8.GetClid接口

 - URL 格式: `http://${host}/interface/ivr/GetClid`

 - 参数:
     | 字段                | 可选 | 描述                         |
     | ------------      | ---- | ----------------------------- |
     | enterpriseId             | 必选 | 通道里面的企业ID                |
     | routerClidCallType             | 必选 | clid类型，只能为1、2、中的一个 |
     | customerNumber             | 必选 | 顾客号码 |
     | numberTrunk             | 必选 | 中继号码 |
 - 返回:
   - json字符串格式数据

   | 字段                  | 可选 | 描述                                   |
   | ------------          | ---- | ------------------------------------  |
   | result           | 可选 | 请求结果状态信息，当参数不合法时才会有该参数，且固定为1 |
   | description           | 可选 | 请求结果描述信息，当参数不合法时才会有该参数，且固定为‘参数不合法’ |
   | clid           | 可选 | 当参数合法时才有该参数，有可能为customerNumber或trunk号码区号+trunk号码或随机选取已有的一个clidNumber |
   | clid_bak           | 可选 | 当参数合法才有该参数，有肯能为有可能为trunk号码区号+trunk号码或随机选取已有的一个clidNumber或空字符串 |
   
 ### 9.GetAreaCode接口

 - URL 格式: `http://${host}/interface/ivr/GetAreaCode`

 - 参数:
     | 字段                | 可选 | 描述                         |
     | ------------      | ---- | ----------------------------- |
     | tel            | 必选 | 号码                |
     | gateway             | 必选 | 网关id地址                |
 - 返回:
   - json字符串格式数据

   | 字段                  | 可选 | 描述                                   |
   | ------------          | ---- | ------------------------------------  |
   | __cdr_customer_number           | 必选 | 客户号码|
   | __cdr_customer_number_type           | 必选 |电话类型 |
   | __cdr_customer_area_code           | 必选 |客户号码区号 |
   
 ### 10.Curl接口

 - URL 格式: `http://${host}/interface/ivr/Curl`

 - 参数:
     | 字段                | 可选 | 描述                         |
     | ------------      | ---- | --------------------------- |
     | enterpriseId            | 必选 | 企业id                |
     | retry             | 必选 | 重试次数 |
     | timeout             | 必选 | 超时时间 |
     | uniqueId             | 必选 | 通话唯一标识 |
     | url | 必选 | 请求唯一标识 |
     | userField             | 必选 |                 |
     | params             | 必选 | 请求参数 |
     | sync             | 必选 |                 |
     | method             | 必选 | 请求方式 |
 - 返回:
   - json字符串格式数据或String格式数据（当sync为1的时候返回普通的String数据，并且以下两个字段不存在，否则返回json）

   | 字段                  | 可选 | 描述                                   |
   | ------------          | ---- | ------------------------------------  |
   | curl_result           | 必选 | 请求结果状态信息，可能为1或0，当参数不合法时为0，否则为1，当sync不为1时存在该参数 |
   | msg                   | 可选 | 请求结果描述信息，当有不合法的参数的时候才有该参数；当sync不为1并且enterpriseId、retry，timeout参数不为数字时该参数为"参数格式错误”，当params、sync、method为空时该参数为“缺少参数” |

 ### 11.IvrProfileImport接口

 - URL 格式: `http://${host}/interface/system/IvrProfileImport`

 - 参数:
     | 字段                | 可选 | 描述                         |
     | ------------      | ---- | ----------------------------- |
     | enterpriseId            | 必选 | 企业id                |
     | userName             | 必选 | 用户名                |
     | seed             | 必选 |                 |
     | pwd             | 必选 | 密码 |
     | action             | 必选 | 动作类型 |
     | stringIvr             | 必选 |                 |
     | ivrProfileId             | 必选 |                 |
 - 返回:
   - json字符串格式数据

   | 字段                  | 可选 | 描述                                   |
   | ------------          | ---- | ------------------------------------  |
   | result             | 必选 | 请求结果状态信息,，可能为error或success，error表示参数不合法或内部异常,sucess代表成功 |
   | code                   | 必选 | 请求结果详细状态信息，可能为0、1、2、3、6。0代表请求成功且结果有效，1代表参数为空，2代表参数格式不正确，3代表参数有误(主要是查不到相关记录),6代表服务器内部发生异常 |
   | msg                   | 必选 |请求结果描述信息|
   | ivrProfileId           | 可选 | 当action为add时才有该字段,且等同于IvrProfile对象的id |

 ### 12.FormatRDNIS接口

 - URL 格式: `http://${host}/interface/ivr/FormatRDNIS`

 - 参数:
     | 字段                | 可选 | 描述                         |
     | ------------      | ---- | ----------------------------- |
     | rdnis            | 必选 |                 |
     | gwIp             | 必选 | 网关ip地址 |
 - 返回:
   - json字符串格式数据

   | 字段                   | 可选 | 描述                                   |
   | ------------          | ---- | ------------------------------------   |
   | __RDNIS               | 可选 |    格式化后的rdnis                      |
 ### 13.GetTelSet接口

 - URL 格式: `http://${host}/interface/ivr/GetTelSet`

 - 参数:
     | 字段                | 可选 | 描述                         |
     | ------------      | ---- | ----------------------------- |
     | enterpriseId            | 必选 |  企业id               |
     | type             | 必选 |     呼叫类型            |
     | telSet | 必选 | 组号 |
 - 返回:
   - json字符串格式数据

   | 字段                   | 可选 | 描述                                   |
   | ------------          | ---- | ------------------------------------  |
   | cdr_queue_name | 必选 | 等同于组号 |
   | tel_set_count | 可选 | 符合enterpriseId和telSet条件的所有记录的数量,当type是ivr时存在该字段 |
   | tel_set_timeout | 可选 | 组超时时间,秒数,默认300,,当type是ivr时存在该字段 |
   | tel_set_strategy | 可选 | 组呼叫策略, order:顺序,random:随机,,当type是ivr时存在该字段 |
   | tel_set_tel | 可选 | 电话和组超时时间组成的长字符串,如13515,300;141325,200,,当type是ivr时存在该字段 |
   | tel_set | 可选 | 电话组成的长字符串,如13515;141325.当type不是ivr时存在该字段 |

### 14.GetHangupSet接口

- URL 格式: `http://${host}/interface/ivr/GetHangupSet`

- 参数:

  | 字段         | 可选 | 描述                                      |
  | ------------ | ---- | ----------------------------------------- |
  | enterpriseId | 必选 | 企业id                                    |
  | callType     | 必选 | 呼叫类型,1(呼入)或2(网上400呼入),否则无效 |

- 返回:

  - json字符串格式数据

  | 字段                         | 可选 | 描述                                                |
  | ---------------------------- | ---- | --------------------------------------------------- |
  | result                       | 必选 | 执行结果,固定为success                              |
  | hangup_set_count             | 必选 | 符合外呼(呼入)和enterpriseId条件的所有记录数量      |
  | hangup_set_+ i + _name       | 必选 | enterprise_hangup_set变量名称(其中i为集合索引,下同) |
  | hangup_set_ + i + _value     | 必选 | enterprise_hangup_set变量值                         |
  | hangup_set_+ i + _value_type | 必选 | enterprise_hangup_set变量类型 0:表达式 1:字符串     |


 ### 15.AlarmEvent接口

 - URL 格式: `http://${host}/interface/ivr/alarmEvent`

 - 参数:
     | 字段                | 可选 | 描述                         |
     | ------------      | ---- | ----------------------------- |
     | enterpriseId            | 必选 |  企业id               |
     | uniqueId            | 必选 | 通话唯一标识 |
     | callType             | 必选 | 呼叫类型 |
     | eventType             | 必选 | 事件类型 1:按键后立刻挂机 2:webcall排队超过最大 3:webcall排队超过75% |
     | msg             | 必选 | 请求结果描述信息 |
 - 返回:
   - json字符串格式数据

   | 字段                   | 可选 | 描述                                   |
   | ----------------------| ---- | ------------------------------------  |
   | result                | 必选 | 执行结果状态信息,固定为success,发生异常则500错误 |

    ### 16.CheckCallLimit接口

 - URL 格式: `http://${host}/interface/ivr/CheckCallLimit`

 - 参数:
     | 字段              | 可选 | 描述                         |
     | ------------     | ---- | ----------------------------- |
     | appId            | 必选 |  企业id                        |
     | calleeNumber     | 必选 | 被叫号码 |
 - 返回:
   - json字符串格式数据

   | 字段                   | 可选 | 描述                                   |
   | ----------------------| ---- | ------------------------------------  |
   | result                | 必选  | 请求结果状态信息, 2 3 4 false代表参数不合法      |
   | description           | 可选  | 请求结果描述信息,如果参数都合法,则该字段不存在 |

 ### 17.SendOnlineCallUrl接口

 - URL 格式: `http://${host}/interface/SendOnlineCallUrl`

 - 参数:
     | 字段                | 可选 | 描述                         |
     | ------------      | ---- | ----------------------------- |
     | appId            | 必选 |  企业id                          |
     | timestamp     | 必选 | 时间戳(秒) |
     | sign     | 必选 | 鉴权参数,由appId和timestamp以及toten进行MD5加密生成的字符串 |
     | subId     | 必选 | 绑定关系的唯一标识 |
     | telB     | 必选 | AXB号码绑定关系中的B号码 |
 - 返回:
   - json字符串格式数据或普通String数据（当参数都合法且有效时返回普通String，否则返回json）

   | 字段                   | 可选 | 描述                                   |
   | ----------------------| ---- | ------------------------------------  |
   | result                | 可选 | 请求结果状态信息,0代表参数不合法或者无效。如果参数合法且有效，则没有该字段 |
   | description           | 可选  | 请求结果描述信息。如果参数合法且有效，则没有该字段 |
   

 ## 保存自助录音信息
 ### 18.SaveSelfRecord接口

 - URL 格式: `http://${host}/interface/ivr/SaveSelfRecord`

 - 参数:
     | 字段              | 可选 | 描述                         |
     | ------------     | ---- | ----------------------------- |
     | enterpriseId     | 必选 |  企业id                        |
     | path             | 必选 |  企业语音文件路径                           |
 - 返回:
   - json字符串格式数据

   | 字段                   | 可选 | 描述                                   |
   | ----------------------| ---- | ------------------------------------  |
   | result                | 必选  | 执行结果信息,如果未发生异常,则固定为success,否则500错误 |
 ## 发起自助录音信息
 ### 19.SelfRecord接口

 - URL 格式: 'http://${host}/interface/selfRecord/SelfRecord'

 - 参数:
     | 字段              | 可选 | 描述                         |
     | ------------     | ---- | ----------------------------- |
     | enterpriseId     | 必选 |  企业id                        |
     | tel              | 必选 |  号码               |
 - 返回:
   - json字符串格式数据

   | 字段                   | 可选 | 描述                                   |
   | ----------------------| ---- | ------------------------------------  |
   | result                | 必选 | 执行结果状态信息,如果参数不合法或无效或者发生异常,则该字段为erro,否则该字段为success(呼叫成功) |
   | msg                   | 必选 | 执行结果描述信息          |
 ## 重新生成失败cdr接口
 ### 20.ReExecuteCDR接口

 - URL 格式: `http://${host}/interface/reExecuteCDR'

 - 参数:

     | 字段 | 可选 | 描述 |
     | ---- | ---- | ---- |

 - 返回:
   - json字符串格式数据

   | 字段                   | 可选 | 描述                                   |
   | ----------------------| ---- | ------------------------------------  |
   | result                | 必选  | 请求结果状态信息 |
   | msg                   | 必选  | 请求结果描述信息 |
   | totalCount            | 必选  | 呼叫总数 |
   | successCount          | 必选  | 呼叫成功数 |
   | failCount             | 必选  | 呼叫失败数 |
 ## ivr使用外部函数接口
 ### 21.DecryptBase64DES接口

 - URL 格式: `http://${host}/interface/ivr/DecryptBase64DES`

 - 参数:
     | 字段              | 可选 | 描述                         |
     | ------------     | ---- | ----------------------------- |
     | input            | 必选 | 需要解密的内容 |
     | key              | 必选 | 辅助解密的键值(可以理解为密码) |
 - 返回:
   - json字符串格式数据

   | 字段                   | 可选 | 描述                                   |
   | ----------------------| ---- | ------------------------------------  |
   | func_output           | 必选  | 解密结果,如果input或key为空,则该字段为空字符串 |

 ## 固话本地打本地API
 ### 22.FixdLineToLocal接口

 - URL 格式: `http://${host}/interface/ivr/fixdLineToLocal`

 - 参数:
     | 字段              | 可选 | 描述                         |
     | ------------     | ---- | ----------------------------- |
     | appId            | 必选 | 企业id |
     | tel              | 必选 | 被叫号码 |
     | areaCode              | 必选 | 区号 |
     | trunkNumber              | 必选 | 中继号码 |
     | type              | 必选 | 中继号码类型 |
 - 返回:
   - json字符串格式数据

   | 字段                   | 可选 | 描述                          |
   | ----------------------| ---- | ----------------------------|
   | result           | 必选  | 请求结果状态信息,1代表参数不合法或无效,2代表成功 |
   | description      | 必选  | 请求结果描述信息 |
   | number           | 必选  | 根据appId和areaCode随机获取的一个号码,如果选出的号码为空,则该字段等同于trunkNumber |


 ### 23.getCaller接口

 - URL 格式: `http://${host}/interface/ivr/getCaller`

 - 参数:
     | 字段              | 可选 | 描述                         |
     | ------------     | ---- | ----------------------------- |
     | appId            | 必选 | 企业id |
     | calleeNumber     | 必选 | 被叫号码 |
     | trunkNumber      | 必选 | 中继号码 |
 - 返回:
   - json字符串格式数据

     | 字段                   | 可选 | 描述                        |
     | ----------------------| ---- | ---------------------------|
     | result                | 必选  | 请求结果转台信息,1代表参数不合法或无效,2代表成功 |
     | description           | 必选  | 请求结果描述信息 |
     | number                | 必选  | 从该企业的自备号里面随机选取的一个号码,如果该企业没有拓展类参数配置或者拓展类配置里包含了被叫号码,则该字段为空字符串;如果该企业拓展类参数配置的value为空字符串,则该字段等同于trunkNumber |
 ## 手机号逻辑调度

 ### 24.telNumerSchedul接口

 - URL 格式: `http://${host}/interface/ivr/telNumerSchedul`

 - 参数:
     | 字段              | 可选 | 描述                         |
     | ------------     | ---- | ----------------------------- |
     | mode             | 必选 | 只能为1或2 |
     | telX             | 必选 | AXB绑定关系中的X号码 |
     | appId            | 必选 | 企业id |
     | telB             | 必选 | AXB绑定关系中的B号码 |
     | areaCode         | 必选 | 区号 |
     | trunkNumber      | 必选 | 中继号码 |
 - 返回:
   - json字符串格式数据

     | 字段                   | 可选 | 描述                        |
     | ----------------------| ---- | ---------------------------|
     | result                | 必选  | 请求结果状态信息,1代表参数不合法或无效,2代表成功 |
     | description           | 必选  | 请求结果描述信息 |
     | number                | 必选  | 如果axb绑定成功,则该字段等同于根据appId和areaCode随机获取的一个号码,否则该字段等同于trunkNumber |
 ## 25.exportTaskQueue接口

 - URL 格式: `http://${host}/exportTaskQueue`

 - 参数:
     | 字段              | 可选 | 描述                         |
     | ------------     | ---- | ----------------------------- |
     | enterpriseId     | 必选 | 企业id |
     | fileName         | 必选 | 文件名 |
     | op               | 必选 | 操作类型 download或delete |
 - 返回:

   - String格式数据(描述操作结果)


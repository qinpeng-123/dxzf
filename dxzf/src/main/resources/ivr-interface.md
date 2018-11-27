realtime模块，提供HTTP接口，支持GET和POST请求方式。
# 目录
[1.Identify](realtime接口.md#1.identify接口)  
## realTime模块
### 1.Identify接口 
#### multi

- URL 格式: `http://${host}/interface/realtime/identify/multi`

- 参数:  
    | 字段 | 可选 | 描述               |
    | ---- | ---- | ------------------ |
    | id   | 不限 | 傻傻的广东省更多撒 |

- 返回:
  - String格式数

  |   字段          |   可选 |   描述                                 |
  |   ------------ |   ---- |   ------------------------------------|
  |   id           |   必选 |   等同于网关名称                         |
  |   type         |   必选 |   固定为identify                        |
  |   endpoint     |   必选 |   等同于网关名称                         |
  |   match        |   必选 |   等同于网关ip地址                       |
  - 示例: `id=gateway.1&type=identify&endpoint=gateway.1&match_header=P-Tinet-Identify-Endpoint: gateway.1`



#### single

- URL 格式: `http://${host}/interface/realtime/identify/single,id=10.10.5.157`
- 参数:  
    |   字段          |   可选 |   描述                                 |
    |   ------------ |   ---- |   ------------------------------------|
    |   id           |   必选 |   网关ip地址或网关名称                    |
- 返回:
  - String格式数

  |   字段          |   可选 |   描述                                  |
  |   ------------ |   ---- |   ------------------------------------ |
  |   id           |   必选 |   等同于网关名称                          |
  |   type         |   必选 |   固定为identify                         |
  |   endpoint     |   必选 |   等同于网关名称                          |
  |   match        |   必选 |   等同于网关ip地址                        |
  - 示例: `id=gateway.1&type=identify&endpoint=gateway.1&match_header=P-Tinet-Identify-Endpoint: gateway.1`

### 2.Moh接口
#### multi

- URL 格式: `http://${host}/interface/realtime/moh/multi`
- 参数:  
    |   字段          |   可选 |   描述                                |
    |   ------------ |   ---- |   ------------------------------------|
    |   name         |   必选 |   类名 格式：企业号+类名                |
- 返回:
  - String格式数

  |   字段          |   可选 |   描述                                 |
  |   ------------ |   ---- |   ------------------------------------|
  |   name         |   必选 |   类名 格式：企业号+类名                   |
  |   mode         |   必选 |   模式                                  |
  |   directory    |   必选 |   频文件的路径                           |
  


#### single

- URL 格式: `http://${host}/interface/realtime/moh/single`
- 参数:  
    |   字段          |   可选 |   描述                                   |
    |   ------------ |   ---- |   --------------------------------------|
    |   name         |   必选 |   类名 格式：企业号+类名                    |
- 返回:
  - String格式数

  |   字段         |   可选 |   描述                                      |
  |   ------------ |   ---- |   ----------------------------------------|
  |   name         |   必选 |   类名 格式：企业号+类名                      |
  |   mode         |   必选 |   模式                                     |
  |   directory    |   必选 |   频文件的路径                               |

### 3.SipUsers接口
#### multi

- URL 格式: `http://${host}/interface/realtime/sipUsers/multi`
- 参数:  
    |   字段          |   可选 |   描述                                |
    |   ------------ |   ---- |   ------------------------------------|
    |   name         |   必选 |   ip地址或网关名称              |
- 返回:
  - String格式数

  |   字段          |   可选 |   描述                                 |
  |   ------------ |   ---- |   ------------------------------------|
  |   name         |   必选 |   当参数name是ip地址时该值等同于name,否则该值等同于网关名称|
  |   type         |   必选 |   类型,固定为friend                       |
  |   host         |   必选 |   域名,等同于ip地址                        |
  |   context      |   必选 |   固定为default                           |
  |   call-limit   |   必选 |   网关吞吐能力                             |
  |   ipaddr       |   必选 |   网关ip地址                              |
  |   port         |   必选 |   sip信令端口                             |
  |   disallow     |   必选 |   网关codec选择disallow                   |
  |   allow        |   必选 |   网关codec选择allow                      |
  |   dtmf_mode    |   必选 |   网关的dtmf设置 rfc2833/info/auto/inband |
  |   change       |   必选 |   是否变更,1表示变更,0表示未变更             |
  


#### single
- URL 格式: `http://${host}/interface/realtime/sipUsers/multi`
- 参数:  
    |   字段          |   可选 |   描述                                |
    |   ------------ |   ---- |   ------------------------------------|
    |   name         |   必选 |   ip地址或网关名称              |
- 返回:
  - String格式数

  |   字段          |   可选 |   描述                                 |
  |   ------------ |   ---- |   ------------------------------------|
  |   name         |   必选 |   当参数name是ip地址时该值等同于name,否则该值等同于网关名称|
  |   type         |   必选 |   类型,固定为friend                       |
  |   host         |   必选 |   域名,等同于ip地址                        |
  |   context      |   必选 |   固定为default                           |
  |   call-limit   |   必选 |   网关吞吐能力                             |
  |   ipaddr       |   必选 |   网关ip地址                              |
  |   port         |   必选 |   sip信令端口                             |
  |   disallow     |   必选 |   网关codec选择disallow                   |
  |   allow        |   必选 |   网关codec选择allow                      |
  |   dtmf_mode    |   必选 |   网关的dtmf设置 rfc2833/info/auto/inband |
  |   change       |   必选 |   是否变更,1表示变更,0表示未变更             |
  
### 4.EndPoint接口
#### multi

- URL 格式: `http://${host}/interface/realtime/endpoint/multi`
- 参数:  
    |   字段          |   可选 |   描述                                |
    |   ------------ |   ---- |   ------------------------------------|
    |   id           |   必选  |   ip地址或网关名称                       |
- 返回:
  - String格式数

  |   字段                 |   可选 |   描述                                   |
  |   ------------        |   ---- |   ------------------------------------  |
  |   id                  |   必选 |   网关名称                                |
  |   type                |   必选 |   固定为endpoint                          |
  |   transport           |   必选 |   固定为transport-udp-nat                 |
  |   context             |   必选 |   固定为default                           |
  |   disallow            |   必选 |   网关codec选择disallow                   |
  |   allow               |   必选 |   网关codec选择allow                      |
  |   dtmf_mode           |   必选 |   网关的dtmf 设置 rfc2833/info/auto/inband |
  |   device_state_busy_at|   必选 |   等同于网关吞吐能力                        |
  |   rtp_keepalive       |   必选 |   固定为60                                |
  |   rtp_timeout         |   必选 |   固定为60                                |
  |   rtp_timeout_hold    |   必选 |   固定为60                                |
  |   timers              |   必选 |   固定为no                                |
  


#### single
- URL 格式: `http://${host}/interface/realtime/endpoint/multi`

- 参数:  
    |   字段          |   可选 |   描述                                |
    |   ------------ |   ---- |   ------------------------------------|
    |   id           |   必选 |   ip地址或网关名称                      |
- 返回:
  - String格式数

  |   字段                 |   可选 |   描述                                   |
  |   ------------        |   ---- |   ------------------------------------  |
  |   id                  |   必选 |   网关名称                                |
  |   type                |   必选 |   固定为endpoint                          |
  |   transport           |   必选 |   固定为transport-udp-nat                 |
  |   context             |   必选 |   固定为default                           |
  |   disallow            |   必选 |   网关codec选择disallow                   |
  |   allow               |   必选 |   网关codec选择allow                      |
  |   dtmf_mode           |   必选 |   网关的dtmf 设置 rfc2833/info/auto/inband |
  |   device_state_busy_at|   必选 |   等同于网关吞吐能力                        |
  |   rtp_keepalive       |   必选 |   固定为60                                |
  |   rtp_timeout         |   必选 |   固定为60                                |
  |   rtp_timeout_hold    |   必选 |   固定为60                                |
  |   timers             |   必选 |   固定为no                                |

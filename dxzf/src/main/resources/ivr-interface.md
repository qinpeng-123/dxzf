### 1.Identify接口 
#### multi

* URL 格式: `http://${host}/interface/realtime/identify/multi`
|学号|姓名|分数|
|-|-|-|
|小明|男|75|
|小红|女|79|
|小陆|男|92|
* 返回:
  - String格式数

  | 字段          | 可选 | 描述                                 |
  | ------------ | ---- | ------------------------------------|
  | id           | 必选 | 等同于网关名称                         |
  | type         | 必选 | 固定为identify                        |
  | endpoint     | 必选 | 等同于网关名称                         |
  | match        | 必选 | 等同于网关ip地址                       |
  - 示例: `id=gateway.1&type=identify&endpoint=gateway.1&match_header=P-Tinet-Identify-Endpoint: gateway.1`
  


#### single

* URL 格式: `http://${host}/interface/realtime/identify/single,id=10.10.5.157`
* 参数:
    | 字段          | 可选 | 描述                                 |
    | ------------ | ---- | ------------------------------------|
    | id           | 必选 | 网关ip地址或网关名称                    |
* 返回:
  * String格式数

  | 字段          | 可选 | 描述                                  |
  | ------------ | ---- | ------------------------------------ |
  | id           | 必选 | 等同于网关名称                          |
  | type         | 必选 | 固定为identify                         |
  | endpoint     | 必选 | 等同于网关名称                          |
  | match        | 必选 | 等同于网关ip地址                        |
  * 示例: `id=gateway.1&type=identify&endpoint=gateway.1&match_header=P-Tinet-Identify-Endpoint: gateway.1`

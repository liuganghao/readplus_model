#目录:
----
[TOC]
#实体user
----
$$entity
name]:用户
code]:user
acl_read]:currentuser,admin
acl_write]:currentuser,admin
propertylist]:
code | name | type | option
--- | --- | --- | --- | --- | ---
code | 编码 | String  | required:[true, 'code required'] & lowercase:true
name | 昵称 | String |  |
role | 角色 | List<String>
phone | 手机号 | String |  |
email | Email | String |
avatar | 头像 | Image |  | 
province | 省份 | String |  | 
city | 城市 | String |  | 
state | 状态 | Enum_State |
password | 密码 | String | required:[true, 'password required']
reg_ip | 注册时IP | String
openid| 微信openid | String |
unionid | 微信唯一id | String |  |
createdby | 创建人 | Ref__User |
createdby_name | 创建人 | String | 
updatedby | 修改人 | Ref__User |
updatedby_name | 修改人 | String |  

##状态机
----
statemachine]:
```dot
digraph G{
"enabled 启用"->"draft 草稿"[label="disable 停用"]
"draft 草稿"->"enabled 启用"[label="enable 启用"]
}
```
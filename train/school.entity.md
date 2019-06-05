#目录:
----
[TOC]
#实体_school
----
$$entity
name]:学校
code]:school
acl_read]:public
acl_write]:currentuser,admin,bd
propertylist]:
code | name | type | option
--- | --- | --- | ---
name | 名称 | String |
shortname | 简称 | String |
avatar | 首图 | Image |
avatar_ex1 | 图片 | Image
avatar_ex2 | 图片 | Image
province | 省 | String
city | 市 | String
region | 区 | String
area_fullname | 所在地全称 | String |
grade_from | 年级 | Int |
grade_to | 年级 | Int |
level_from | 级别 | Int |
level_to | 到级别 | Int |
manager | 校长 | Ref__User
manager_name | 校长名称 | String
isgov | 公立/私立 | Boolean
state | 状态 | Enum_State |
createdby | 创建人 | Ref__User |
createdby_name | 创建人 | String |
updatedby | 修改人 | Ref__User |
updatedby_name | 修改人 | String | 
 
 

#生命周期
----
##状态机
statemachine]:
```dot
digraph G{
"draft 草稿"->"enabled 启用"[label="enable 启用"]
"enabled 启用"->"draft 草稿"[label="disable 停用"]
}
```

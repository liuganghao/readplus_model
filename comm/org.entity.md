# 目录
---
[TOC]

## 实体 org
---
$$entity
name]:组织
code]:org
acl_read]:public
acl_write]:currentuser,admin
propertylist]:
code | name | type | option
--- | --- | --- | ---
code | 编码 |String |index:true 
name | 名称 | String |  
logo | 图标 | Image | 
approveid | 审批流程id | String |  
tel | 电话 | String
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
"draft 草稿"->"approving 核准中"[label="submit 提交"]
"approving 核准中"->"inprogressing 已核准"[label="approve 核准"]
"approving 核准中"->"closed 关闭"[label="reject 拒绝"]
"inprogressing 已核准"->"closed 关闭"[label="close 关闭"]
"closed 关闭"->"draft 草稿"[label="open 打开"]
}
```
```
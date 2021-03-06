# 实验1：业务流程建模

学号：201510414217

班级：15级软工2班

姓名：万佳羽

## 流程图1：考试及成绩管理流程

PlantUML源码如下：

```
@startuml
|教务处|
start
:安排考试;
:考试安排表;
|教师|
if(出卷)
:A,B试卷;
else
:打印审批表;
|系主任|
:审批签字;
:打印审批表;
endif
|教务处|
:打印试卷;
:试卷;
|学生|
:参加考试;
:答卷;
|教师|
if(阅卷出成绩)
:成绩单;
|教务处|
if(有不及格？)then(有)
  :安排补考;
  :补考安排表;
  endif
|教师|
else
:答卷;
:装订存档;
endif
:期末流程结束;
end
@enduml
```

业务流程图如下：

![1](1.png)

流程说明：

全程用到了泳道来定义人员，【出卷处】和【阅卷出成绩】用到了并行处理，【有不及格？】处用到了条件语句

## 流程图2：客户维修服务流程

PlantUML源码如下：

```
@startuml
|客户|
start
:申请服务;
|业务经理|
if(是新客户吗？)then(是)
:等级客户信息;
else(不是)
endif
:上门勘察;
:制订方案;
|客户|
if(满意吗？)then(否)
end
else(是)
:签订服务合同;
|业务经理|
fork
 :安排工人;
fork again
 :安排材料;
end fork
:填写派工单;
|工人|
:领取材料;
:上门服务;
|客户|
:验收并填写反馈意见;
|业务经理|
:交回派工单;
|财务人员|
:结算收款;
```

业务流程图如下：

![2](2.png)

流程说明：

全程用到了泳道来定义人员，【是新客户吗？】和【满意吗？】两处用到了条件语句，【安排工人】和【安排材料】用到了fork关键字
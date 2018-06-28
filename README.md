# 打造基于SSM的人员管理系统
------------数据库准备------------
## 部门记录表
```
CREATE TABLE `tbl_dept` (
  `dept_id` int(11) NOT NULL DEFAULT '0' COMMENT '部门的id',
  `dept_name` varchar(255) NOT NULL DEFAULT '' COMMENT '部门的名字',
  `dept_leader` varchar(255) NOT NULL DEFAULT '' COMMENT '部门主管',
  PRIMARY KEY (`dept_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8
```

## 人员记录表
```
CREATE TABLE `tbl_emp` (
  `emp_id` int(11) unsigned NOT NULL AUTO_INCREMENT COMMENT '员工id',
  `emp_name` varchar(22) NOT NULL DEFAULT '' COMMENT '员工姓名',
  `emp_email` varchar(256) NOT NULL DEFAULT '' COMMENT '员工邮箱',
  `gender` char(2) NOT NULL DEFAULT '' COMMENT '员工性别',
  `department_id` int(11) NOT NULL DEFAULT '0' COMMENT '部门id',
  PRIMARY KEY (`emp_id`)
) ENGINE=InnoDB AUTO_INCREMENT=7 DEFAULT CHARSET=utf8
```

---------------------------------
# V1
- Date：2018.06.28
- 功能：建立模版，实现部门/人员查询、部门/人员增删的功能
- 遇到过的问题及解决方式：Tomcat7默认使用ISO-8859-1解码，导致传到后台的中文出错。解决方案：修改server.xml，令tomcat使用浏览器的编码。
---
title: '后端实验指南'
weight: 2002
---

# Lab03 后端进阶

## 紧急加播

考虑到大家java才刚学没多久，因此酌情调整难度，已经完成的同学可以提交老版本的作业，但是在实验报告中需要注明，新接触的同学按照最新的实验指南和要求即可

## 实验目的

- 学习使用maven管理配置依赖

- 了解springboot的基础知识，能够自行创建一个springboot项目

- 了解基础的分层结构

- ~~锻炼解决问题的能力，通过查询**官方文档**或其他**技术博客**解决遇到的问题~~

## 资源链接

<a href="https://bhpan.buaa.edu.cn:443/link/2B8C3DF0CE32D21908D8007C843940A5" target="_blank">https://bhpan.buaa.edu.cn:443/link/2B8C3DF0CE32D21908D8007C843940A5</a>
有效期限：2022-08-01 23:59

## 实验指南

- 阅读资源中提供的Maven资料，了解Maven的基础内容，如果你还不了解基础的java依赖引入，可以先行学习，再来学习Maven
- 学习《Springboot基础》与视频资料，自行创建一个基础的Springboot项目并成功运行
- 学习使用postman（可参考官网教程<a href="https://learning.postman.com/docs/getting-started/introduction" target="_blank">https://learning.postman.com/docs/getting-started/introduction</a>， 不推荐一口气读完，推荐随用随查）

## 实验作业

### 任务1

提供视频中的基础代码(跟视频手打or自己弄明白原理手搓)，并连接自己的本地数据库（需要回忆你的数据库课程知识），并且成功运行，请提供运行**截图**

### ~~任务2~~<span style="color: red">（考虑到大多数同学都是初学java，本任务不再强行要求）</span>

~~根据注册代码和 session 的处理方式完成登录请求（localhost:8090/login），并使用Postman 测试，请提供运行**截图**~~

~~{{< hint info >}}~~
~~温馨提示：session 的处理方式 ppt 上所说的是绝对不够用的，这里是为了考验大家能不能通过官网等渠道获取到有用信息~~
~~{{< /hint >}}~~

### 任务3

增加个人信息查询功能（localhost:8090/show_info），并使用 Postman 测试（在 body 中返回“name”：“xxx”， “password”： “xxx”），请提供运行**截图**

写一份实验报告，简要说明任务 1 的完成过程，以及在任务 2 和任务 3 中使用 Postman 测试情况截图（测试数据和结果），最好附上你的心得

{{< hint info >}}

注：完成上述需求并且运行无 bug 和报错即满分。

{{< /hint >}}

##### 提交方式

- 截止时间：**2022/4/3 晚12点**
- 提交方式：<a href="https://scs.buaa.edu.cn/" target="_blank">软院云平台</a>
- 提交内容：实现上述任务1和3功能后的项目代码文件夹，和实验报告，命名格式如下：


```txt
学号_姓名_第3次实验.zip
|-- 项目代码文件夹
 -- 学号_姓名_第3次实验_实验报告.docx/pdf
```


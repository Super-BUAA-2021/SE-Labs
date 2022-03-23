---
title: 'Django入土篇'
weight: 2005
---

# Django 入土篇

## Django 从入门到入土

Liujiang Blog：https://www.liujiangblog.com/course/django/84

{{< button href="https://www.liujiangblog.com/course/django/84" >}}Get Liujiang Blog{{< /button >}}

Marvolo Djangobook：https://super-buaa-2021.github.io/Djangobook/

{{< button href="https://super-buaa-2021.github.io/Djangobook/" >}}Get Djangobook{{< /button >}}

## Django 指令或代码指示

### 项目指令

```shell
django-admin startproject <project_name>    # 创建项目
python manage.py startapp <app_name>        # 创建APP
python manage.py runserver                  # 本地运行
python manage.py makemigrations             # 生成迁移文件
python manage.py migrate                    # 迁移数据库模型
```

### Django Models

#### Django 的 Model 数据类型

| 数据类型 | 说明 |
| - | - |
| AutoField | 根据 ID 自增长的 IntegerField 字段，通常用于主键ID |
| IntegerField | 32位整数，可自定义选项 |
| BooleanField | 布尔值(True/False)字段 |
| CharField | 字符串字段，对小字符串和大字符串都适用；对于大量文本建议使用TextField。必须参数：max_length（字段的最大字符数）|
| DateField | 利用 Python 的 datetime.date 实例来表示日期 |
| DateTimeField | 利用 datetime.datetime 实例表示日期和时间 |
| EmailField | 带有 email 合法性检测的CharField，默认max_length=75 |
| TextField | 超大文本字段 |
| FileField | 文件字段 |
| ImageField | 继承于FileField，确保是有效图片 |

#### Model 数据类型的通用参数

| 参数 | 说明 |
| - | - |
| null | 是否允许为空值，默认为false |
| default | 该属性的默认值 |
| primary_key | 该属性是否为主键，默认为false |
| unique | 该属性的值是否唯一，默认为false |

#### 时间类型的可选参数

- DateField.auto_now：设为 `True` 时，每一次保存对象时，Django 都会自动将该字段的值设置为当前时间。一般用来表示最后修改时间。
- DateField.auto_now_add：设为 `True` 时，第一次创建对象时，Django 自动将该字段的值设置为当前时间，一般用来表示对象创建时间。

### Django 数据库增删查改

#### 增

```python
# 方法一
user = User()
user.name = "ZewanHuang"
user.save()
# 方法二
user = User(id=1, name="ZewanHuang")
user.save()
# 方法三
User.objects.create(id=1, name="ZewanHuang")
```

#### 查

```python
# 查询特定结果
user = User.objects.get(id=1)
# 查看多个结果（返回一个列表）
users = User.objects.filter(kind=‘学生’)
# 查询全部结果
users = User.objects.all()
```

#### 改

```python
# 方法一：查后改后保存
user = User.objects.get(id=1)
user.name = "Zewan"
user.save()
# 方法二：更新
users = User.objects.filter(kind="学生")
users.update(kind="老师")
```

#### 删

```python
user = User.objects.get(id=1)
user.delete()
```

### Django session 登录信息

**session**：临时保存在服务器端的用户数据，本质是键值对。将用户登录时的ID（标志）存储在 session 中以便后续获取，当处理修改用户信息等请求时，从中获取并核验身份，防止用户能修改其它用户的信息

登录时：
```python
# 如果登录成功，存储用户标志信息
if user.password == password: 
    request.session['id'] = user.id
	request.session['kind'] = "user"
```

检查登录信息时，需要获取 session 存储的数据：
```python
username = request.POST.get('username')
if request.session.get('username') == username:
    # 若session存储数据和请求的用户名相同，则登录信息核验成功
    # 防止用户能修改其它用户的信息
```
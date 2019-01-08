---
layout: default
title: 生产规范与指南
---

# 生产规范与指南
{:.no_toc}

* 目录
{:toc}

## 8.1 点餐系统 生产规范与指南

## 前端代码规范

### JavaScript规范

**1.使用空格代替tab进行缩进**

使用两个空格代替tab键，对代码进行缩进管理。

**2.不能省略分号**

每个语句必须以分号结尾，不允许依赖于JS自动添加分号的功能。

**3.杜绝var**

使用const或let来声明所有局部变量。如果变量不需要被重新赋值，默认应该使用const。

**4.使用模板字符串取代连接字符串**

在处理多行字符串时，使用模板字符串代替+号连接字符串

**5.不要使用eval语句**

**6.常量的命名规范**

常量命名应该使用全大写格式，并用下划线分割，如：	
```
const MAX_LENGTH = 100;
```
**7.使用单引号**

只允许使用单引号包裹普通字符串，禁止使用双引号。

### 项目文件规范

**1.文件命名由多个单词组成，采用中划线连接**

**2.文件名称只由小写英文字母、数字、中划线组成，不应包含特殊符号**

**3.每个页面的默认入口文件应当命名为index.vue**

**4.公共组件统一放置在components文件夹中；页面组件统一放置在pages文件夹中，每个页面的文件夹命名参考文件命名规则**

**5.父组件与子组件间应当以目录结构的方式表现出层级关系，如子组件放置在childrens文件夹中，且childrens文件夹与父组件放置在同一目录下**



## 使用ES2016+

JavaScript规范使用[ES2016+](http://kangax.github.io/compat-table/es2016plus/)



## 使用ESLint

代码使用[ESlint](http://eslint.cn/)作为基本的语法检验工具，规则如下：

- [Eslint Config Standard](https://github.com/standard/eslint-config-standard) 作为基础规则
- [semi](https://eslint.org/docs/rules/semi) 使用分号
- [space-before-function-paren](https://eslint.org/docs/rules/space-before-function-paren) 函数参数列表前需要有括号
- [object-curly-spacing](https://eslint.org/docs/rules/object-curly-spacing) 对象花括号中必须有空格
- [arrow-parens](https://eslint.org/docs/rules/arrow-parens) 箭头函数参数列表按需添加括号
- [no-console](https://eslint.org/docs/rules/no-console) 不适用console
- [camelcase](https://eslint.org/docs/rules/camelcase) 允许非驼峰式命名




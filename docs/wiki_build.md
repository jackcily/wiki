# wiki 构建

wiki构建分为两个部分，一部分是markdown文本存储和显示，一部分是自动生成的网页文本存储和显示。

## 1 环境安装

```bash
pip3 install mkdocs #安装wiki搭建工具 
mkdocs --version   #查看版本，检查安装是否成功

# 新建维基
mkdocs new inner-wiki
cd inner-wiki

# 启动wiki服务
mkdocs serve 

# 更换主题为git风格
pip3 install mkdocs-material 
修改mkdocs.yml,增加风格设置
```

## 2 将wiki托管到git

### 2.1 托管md文件
```bash
cd inner-wiki
git init
git add remote https://github.com/user_name/repository_name
git add .
git commit -m "first commit"
git push origin master
```

### 2.2 托管html文件

部署wiki站点，以下命令执行两个操作：

1. 将md文件自动转为html
2. 将html自动托管到远程仓库的gh-pages分支

```bash
mkdocs gh-deploy  # 自动托管
https://user_name.github.io/repository_name #访问对应的网页
```
<!--![mkdocs](img/1.jpg)-->
## 编辑后无脑更新

```bash
mkdocs gh-deploy && git add . && git commit -m "update" && git push origin master
```
# 参考链接
- [wiki知识库搭建](https://zhuanlan.zhihu.com/p/61492480)
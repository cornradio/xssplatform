## 声明
站点源自 https://github.com/78778443/xssplatform
本人fork仅为学习研究使用。

## 搭建
1. 使用小皮面板，创建一个站点、创建一个xssplatform数据库
2. 打开站点目录，把内容替换为 [78778443/xssplatform: ](https://github.com/78778443/xssplatform) 解压后内容
3. 访问站点，进行初始配置（数据库账号密码、管理员账号密码等）
4. 设置伪静态-打开小皮面板-站点-管理-修改-伪静态，粘贴下面代码（forapache）
5. 小皮面板会把文件内容写入 .htaccess 文件中
```
<IfModule mod_rewrite.c>
RewriteEngine On
RewriteBase /
RewriteRule ^([0-9a-zA-Z]{6})$ /index.php?do=code&urlKey=$1 [L]
RewriteRule ^do/auth/(\w+?)(/domain/([\w\.]+?))?$  /index.php?do=do&auth=$1&domain=$3 [L]
RewriteRule ^register/(.*?)$ /index.php?do=register&key=$1 [L]
RewriteRule ^register-validate/(.*?)$ /index.php?do=register&act=validate&key=$1 [L]
</IfModule>
```

## 使用
1. 我的项目-创建
2. 勾选 默认模块 、 keepsession


- 博客：[https://blog.uliuli.fun](https://blog.uliuli.fun)   

[![Build Status](https://travis-ci.com/baijunyao/laravel-bjyblog.svg?branch=master)](https://travis-ci.com/baijunyao/laravel-bjyblog)
## 简介
项目基于 [laravel-bjyblog](https://github.com/baijunyao/laravel-bjyblog) ；  

## 项目介绍
1. 纯手工前台响应式页面布局适配PC、平板、手机；
2. 带表情的ajax无限级评论系统；
3. 队列邮件通知；
4. QQ、微博、github第三方登录；
5. markdown 编辑器；

## 版权
项目使用 MIT 协议；免费开源可随意使用；

## 更新记录
#####v5.5.3.2 (2018-8-18)
解决第三方登录用户被删除后评论列表报错的问题
去掉第三方账号登录后的弹出提示
##### v5.5.3.1 (2018-8-11)
解决文章被彻底删除后后台评论列表报错的问题
##### v5.5.3.0 (2018-8-4)
解决备案号没有从数据库获取的问题
增加菜单管理功能
注: 因增加了数据表请按执行如下命令升级
更新 composer map

composer dump-autoload
运行迁移生成表文件

php artisan migrate
导入默认的填充数据

php artisan db:seed --class=NavsTableSeeder
##### v5.5.2.2 (2018-7-28)
升级laravel-model至1.3
升级laravel-flash至1.3
引入laravel-jquery
编辑文章的时候不再提示标签的删除操作
前台页面屏蔽flash提示
##### v5.5.2.1 (2018-7-21)
解决用户数展示错误的问题
解决开源项目页面报错的问题
后台文章、评论、用户搜索功能完成
##### v5.5.2.0 (2018-7-14)
过滤搜索中的特殊符号
新底部页面完成
注: 若底部样式展示不完整可执行 php artisan view:clear 刷新缓存

##### v5.5.1.8 (2018-7-7)
禁止蜘蛛抓取搜索页
全文搜索出错时自动降级使用 sql like
##### v5.5.1.7 (2018-06-30)
增加 rss 订阅功能
增加 sql like 搜索方案
整合 elasticsearch
##### v5.5.1.6 (2018-06-23)
解决有恶意访问第三方登录回调的问题
##### v5.5.1.5 (2018-06-16)
Admin 模块 webpack 完成
定义robots禁止搜索引擎抓取搜索页面
优化搜索
##### v5.5.1.4 (2018-06-9)
Home 模块 webpack 完成
##### v5.5.1.3 (2018-05-3)
1. 设置默认标签长度为20
2. 解决QQ登录头像保存失败的问题

**注: 建议把 tag 标签的 name 字段长度增加到 20 以上；避免英文被截断的问题**  
#### v5.5.1.2 (2018-05-26)
1. 默认使用异步创建索引
2. 解决获取登录时的url报错的问题
#### v5.5.1.1 (2018-05-19)
1. 解决添加文章的错误提示
2. 删除和恢复以及彻底删除文章后跳转到之前的页面
3. 解决laravel-flash报错的问题
#### v5.5.1.0 (2018-05-12)
1. 访问不存在的分类和标签时返回404
2. 使用TNTSearch实现全文搜索

**注: 因使用TNTSearch请按执行如下命令升级**  
.env 增加如下配置项
```bash
SCOUT_DRIVER=tntsearch
TNTSEARCH_TOKENIZER=jieba
```
更新 composer  
```bash
composer install --no-dev && composer dump-autoload
```
初始化索引  
```bash
php artisan scout:import "App\Models\Article"
```
#### v5.5.0.23 (2018-05-06)
1. 解决容易忘记选分类的问题
2. 完善article_tags表操作的逻辑
3. 不展示没有文章的标签
#### v5.5.0.22 (2018-04-29)
1. 修复在移动端上下篇文章因标题过长导致样式错乱的问题
2. 解决添加和编辑分类时排序为空时报错的问题
3. 解决markdown编辑器遮挡modal的问题
4. 解决ajax不自动携带X-CSRF-TOKEN的问题
5. 增加在添加文章页面新增标签的功能
6. 解决访问没有文章的分类时报错的问题
#### v5.5.0.21 (2018-04-22)
1. 解决编辑文章时封面图会被第一张图片替换的问题
2. 更改gitee链接
#### v5.5.0.20 (2018-04-21)
1. 删除文章后先同步删除关联表article_tags中的数据
2. 解决markdown编辑器全屏被遮挡的问题
3. 添加在评论无意义信息时的提醒并关闭loading
4. 取消使用Laravel-Searchy
5. 前台页面不弹出添加评论的提示
6. 开源项目页面的oschina改为gitee
#### v5.5.0.19 (2018-04-14)
1. 解决后台登录错误提示重复的问题
2. 使用Laravel-Searchy增强文章搜索功能
#### v5.5.0.18 (2018-04-07)
1. 自定义文章封面图功能完成
2. 解决后台列表内容不自动换行的问题
3. 后台和前台统一分页样式
4. 更改默认头像和文章封面
#### v5.5.0.17 (2018-03-31)
1. 删除、恢复、彻底删除管理员功能完成
2. 所有的恢复数据统一使用restoreData方法
3. 增加彻底删除数据后的提示
#### v5.5.0.16 (2018-03-25)
1. 修复标签名不能跟分类名重复的问题
#### v5.5.0.15 (2018-03-18)
1. 解决添加文章时的错误提示
2. 后台首页只count(id)
#### v5.5.0.14 (2018-03-03)
1. 使用laravel-flash替代flash_message
2. 文章模型关联标签
3. 首页列表文章使用模型关联代替join
4. 解决文章页面有序和无序列表无法正常显示样式的问题
5. 使用模型关联代替join获取文章详情数据
6. 使用访问器过滤描述中的换行
7. 分类页面使用模型关联代替join
8. 使用模型关联重构前台标签下的文章列表
9. 更新系统功能完成
#### v5.5.0.13 (2018-02-23)
1. 增加bjyblog:migrate命令
#### v5.5.0.12 (2018-02-23)
1. 修复数据库密码获取错误的问题
2. 使用gitee以解决clone太慢的问题
3. 解决install报错的问题
#### v5.5.0.11 (2018-02-23)
1. 引入baijunyao/laravel-flash
2. 引入baijunyao/laravel-model
3. 增加旧标签记录
4. readme增加tag日期
5. 使用模型关联替代join获取后台文章列表
6. 文章模型关联分类模型
7. 使用关联模型替代join获取标签下的文章数统计

**注: 因引入了新的包；升级后记得执行`composer install --no-dev && composer dump-autoload`命令**
#### v5.5.0.10 (2018-02-10)
1. 解决第三方账号关联管理员后无法回复评论的问题
2. 增加bjyblog:install命令以简化安装
3. 修复后台无法退出的问题
4. 修复分类没有按照sort字段排序的问题
#### v5.5.0.9 (2018-02-03)
1. 使用 mews/purifier 过滤评论加强 xss 防护
2. 添加EditorConfig配置
3. 修复移动端版权说明样式错乱的问题
4. 默认使用 /config/session.php 定义的 session 过期时间
5. 升级prism增加复制功能
#### v5.5.0.8 (2018-01-26)
1. 升级baijunyao/laravel-print至3.1
2. 只允许使用 oauth 账号登录评论
3. 统一编码风格
4. 自定义验证类用于验证评论内容
5. 更合理的获取评论请求数据
6. 增加中间件用于防止未登录状态请求评论接口
#### v5.5.0.7 (2018-01-22)
1. 设置session过期时间为30天
2. 评论出错返回403错误并阻止继续操作
3. 增加评论草稿箱功能防止评论丢失
4. 底部增加版本号
5. 底部2017改为2018年
6. request只取指定字段
#### v5.5.0.6 (2018-01-16)
1. 解决登录后丢失评论内容的问题
2. 解决dusk测试关闭过快评论失败的问题
#### v5.5.0.5 (2018-01-14)
1. 后台增加清除缓存的菜单
2. 已经登录后台后再访问登录页面自动跳转到后台首页
3. 修复彻底删除评论后跳转不正确的问题
4. 设置随言碎语和开源项目页面的title
5. Powered by改为中文
#### v5.5.0.4 (2018-01-08)
1. require laravel-print 用于调试打印
2. 开启自动发现dusk
3. require dbal用于修改字段
4. 修改文章内容字段类型为mediumText
5. 把char改为string
6. 删除text字段类型的长度  

**注: 因表迁移不支持修改 text 类型 ；所以建议安装 5.5.0.4 之前版本的童鞋手动把 articles 表的 markdown 和 html 字段从 text 类型改为 mediumtext ；以防止生成的 html 过长无法完整储存；**
#### v5.5.0.3 (2018-01-05)
1. 不追踪favicon.ico文件
2. 水印文字从数据库配置中获取
3. 修复分类和标签列表title、keywords、description未正确设置的问题
#### v5.5.0.2 (2018-01-02)
1. 前台dusk测试完成
2. 访问不存在的文章时返回404页面
#### v5.5.0.1 (2017-12-28)
1. 修复社会化登录的错误
#### v5.5.0.0 (2017-12-24)
1. 升级laravel框架到5.5版本
#### v5.3.0.6 (2017-12-21)
1. 修复show_message函数改名造成的错误
2. 修复右侧捐款链接错误的问题
3. 切分日志保留1年的记录
#### v5.3.0.5 (2017-12-20)
1. 新增或者编辑文章后更新标签统计缓存
#### v5.3.0.4 (2017-12-17)
1. 博客版本号从配置项中获取
2. 规范统一使用驼峰命名
#### v5.3.0.3 (2017-12-14)
1. 全局路由约束；限制id必须为数字
#### v5.3.0.2 (2017-12-12)
1. 完善使用说明
2. 自动过滤一些无意义评论
#### v5.3.0.1 (2017-12-09)
1. 第一个稳定版本
#### v5.3.0-rc.4 (2017-12-03)
1. 优化处理缓存的方式
#### v5.3.0-rc.3 (2017-11-26)
1. 加入组织功能完成
#### v5.3.0-rc.2 (2017-10-27)
1. 增加开源项目功能
#### v5.3.0-rc.1 (2017-09-21)
1. 修复各种bug
#### v5.3.0-beta.4 (2017-09-19)
1. 回收站及恢复功能完成
#### v5.3.0-beta.3 (2017-08-31)
1. 使用DB编辑数据后清空缓存
#### v5.3.0-beta.2 (2017-08-23)
1. 使用优雅的方式更新缓存数据
#### v5.3.0-beta.1 (2017-08-18)
1. 使用缓存完善功能
#### v5.3.0-alpha.3 (2017-08-06)
1. 处理一些图片相关的问题
#### v5.3.0-alpha.2 (2017-07-24)
1. 数据填充完成
#### v5.3.0-alpha.1 (2017-07-11)
1. 发布第一个完整的内测版
#### v1.5.3 (2017-06-29)
1. 修复表情和头像的bug
#### v1.5.2 (2017-06-27)
1. 把第三方登录的用户保存在本地
#### v1.5.1 (2017-06-25)
1. 使用ubb标签的方式重构评论表情
#### v1.5.0 (2017-06-13)
1. 后台配置项功能完成
#### v1.4.0 (2017-05-16)
1. 后台分类管理完成
#### v1.3.0 (2017-05-05)
1. 后台随言碎语功能完成
#### v1.2.0 (2017-05-01)
1. 友情链接管理完成
#### v1.1.1 (2017-04-26)
1. 正式开始上线使用
#### v1.1.0 (2017-04-07)
1. 后台增加评论列表
#### v1.0.0 (2017-03-29)
1. 初始版本完成

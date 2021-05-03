# dev-sql

## 说明
* 本项目目的在于方便部署和配置常用数据库，方便本地开发使用，**并非**为了线上正式环境
* 本项目配置了 mysql8.0 mongodb4.4 redis:latest
* 推荐使用 DBeaver 数据库管理工具，可以一次性解决大多数数据库

## 安装及准备工作

```shell
# 克隆本项目
git clone https://github.com/huihuipan/dev-sql.git

# 进入项目目录
cd dev-sql

```

## 使用

### 运行这些容器。
```
docker-compose up -d
```

### 关闭这些容器
```
docker-compose stop
```

### 删除所有容器
```
docker-compose down
```

### 部署yapi
参考 [https://github.com/Ryan-Miao/docker-yapi](https://github.com/Ryan-Miao/docker-yapi)
默认账号密码
***account***: ```admin@admin.com```
***pwd***: ```ymfe.org```
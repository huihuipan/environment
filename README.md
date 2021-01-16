# Environment

## 说明
该项目目的在于方便部署和配置常用数据库，方便本地开发使用，**并非**为了线上正式环境

## 安装及准备工作

```shell
# 克隆本项目
git clone https://github.com/huihuipan/dev-sql.git

# 进入项目目录
cd dev-sql

# 新建文件夹用于数据持久化
mkdir data
cd data
mkdir mysql mongo redis
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

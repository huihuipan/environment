# Environment

## 安装

1、你需要克隆 `environment` 仓库到你的电脑上
```
git clone https://github.com/PretendTrue/environment.git
```

2、进入根目录，复制 `env-example` 一份并且更改文件名为 `.env`
```
cp env-example .env
```

3、进入 `nginx` 文件加下的 `sites` 文件加下，添加你的站点配置文件

4、然后你就可以开始愉快的使用了

## 使用

### 运行这些容器。
```
docker-compose up -d nginx php mysql
```

### 进入 `php` 容器使用
```
docker-compose exec php bash
```

### 关闭这些容器
```
docker-compose stop
```

### 删除所有容器
```
docker-compose down
```

### `Laravel` 项目
打开 `Laravel` 项目的 `.env` 文件 然后 配置 你的 `mysql` 的 `DB_HOST`:
```
DB_HOST=mysql
```

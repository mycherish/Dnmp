# Dnmp

> 自用 Docker 开发环境搭建，使用 M1 的 macOS14.0，其他系统未验证。  
> 
> `Docker` `Nginx` `MySQL` `PHP` `Redis` `Elasticsearch` `IK`
> 
> 注意：本项目仅供学习交流，请勿用于生产环境。

## Version

[![GitHub release](https://img.shields.io/badge/Docker-v24.0.6-red?logo=docker)](https://img.shields.io/badge/Docker-v24.0.6-red)
[![GitHub release](https://img.shields.io/badge/M1_macOS-v14.0-red?logo=apple)](https://img.shields.io/badge/macOS-v14.0-red)

[![GitHub release](https://img.shields.io/badge/MySQL-v8.0.34-4F5D95?logo=mysql)](https://img.shields.io/badge/MySQL-v8.0.34-4F5D95?logo=mysql)
[![GitHub release](https://img.shields.io/badge/Redis-v7.0.5-4F5D95?logo=redis)](https://img.shields.io/badge/Redis-v7.0.5-4F5D95?logo=redis)
[![GitHub release](https://img.shields.io/badge/Nginx-v1.25.1-4F5D95?logo=nginx)](https://img.shields.io/badge/Nginx-v1.25.1-4F5D95?logo=nginx)
[![GitHub release](https://img.shields.io/badge/PHP-v7.3_/_v8.1-4F5D95?logo=php)](https://img.shields.io/badge/PHP-v7.3_/_v8.1-4F5D95?logo=php)
[![GitHub release](https://img.shields.io/badge/Elasticsearch-v7.9.1-4F5D95?logo=Elasticsearch)](https://img.shields.io/badge/PHP-v7.3_/_v8.1-4F5D95?logo=php)
[![GitHub release](https://img.shields.io/badge/IK-v7.9.1-4F5D95)](https://img.shields.io/badge/PHP-v7.3_/_v8.1-4F5D95)

## 使用
1. 安装 Docker Desktop 并启动
2. 克隆本项目到本地，重命名为 `dnmp`  
   ```shell
    git clone git@github.com:mycherish/Dnmp.git dnmp
    ```
3. 进入项目目录
   ```shell
    cd dnmp/compose.dockerfile
    ```
4. 启动服务
   ```shell
    docker-compose up -d
    ```

## License

[MIT](https://opensource.org/licenses/MIT)

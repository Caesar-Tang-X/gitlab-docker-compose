# GiaLab Docker Compose YML File


## 简介
    docker 一键启动 GiaLab 容器的 docker-compose.yml 配置


## 镜像环境：
	gitlab/gitlab-ce:15.0.5-ce.0


## 导入镜像：
	docker load -i 镜像包


## 启动命令：
	docker-compose up -d


## 安装及生成数据路径：
    ├── gitlab 
        ├── images                      镜像文件文件目录
        ├── gitlab                      容器挂载目录
            ├── config                      配置文件目录
            ├── data                        数据目录
            └── logs                        日志目录
        ├── docker-compose.yml          docker-compose.yml
        └── README.md                   README.md


## 隐私信息配置：
    1. 修改 GiaLab root 账号的初始密码, 文件路径：docker-compose.yml


## 后续操作：
### 1. 配置访问地址
#### （1）配置 http 协议访问地址，编辑 ./config/gitlab.rb
	external_url 'http://xw.gitlab.h5xiaomi.com'

#### （2）配置 ssh 协议访问地址，编辑 ./config/gitlab.rb
	gitlab_rails['gitlab_ssh_host'] = '101.37.232.108'
	gitlab_rails['gitlab_shell_ssh_port'] = 22

#### （3）重启 bookstack 容器
	docker restart gitlab



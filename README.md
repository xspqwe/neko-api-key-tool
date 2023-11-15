![img.png](img.png)

# 使用方法
复制.env.example文件为.env
```
cp .env.example .env
```
修改.env文件中的配置
```
# 展示使用明细
SHOW_DETAIL="false"

# 展示余额
SHOW_BALANCE="true"

# BaseURL 结尾不要带/
BASE_URL="https://nekoapi.com"
```

展示使用明细功能需要使用的魔改版One API，项目地址：https://github.com/Calcium-Ion/one-api

在详述部署步骤之前，我们需要假设你的Linux服务器上已经安装了以下必要的软件：Node.js（包括NPM），Docker（如果我们要使用Docker来部署应用）。如果没有，那你需要先安装这些软件。

以下是在Linux服务器上部署这个项目的步骤：

远程连接你的Linux服务器。 使用SSH协议连接到你的Linux服务器，例如 ssh username@your_server_ip。

获取项目文件。 你可以通过git、sftp、scp等方式将你的项目文件传输到服务器上，或者如果项目已经托管在例如Github上，那么可以直接在服务器上用git clone命令下载项目。

示例：git clone https://github.com/username/repository.git

进入项目目录。 使用cd命令进入项目目录。

示例：cd neko-api-key-tool-main

安装项目依赖。 在项目根目录下运行 npm install 命令，这会查看 package.json 文件并安装所列出的所有依赖。

构建项目。 使用npm run build命令进行项目构建。这会创建一个构建版本的应用文件并放在build文件夹下。

部署项目。 运行 npm start 命令来启动应用。

如果你使用Docker，参考下面的步骤

在根目录下创建一个Dockerfile文件，并写入你的项目需要的配置。根据这个项目的特点，这个Dockerfile已经创建好了。

创建Docker镜像：运行 docker build -t your_image_name .，your_image_name是你给这个Docker镜像取的名字。

运行Docker容器：使用 docker run -p 80:80 -d --name your_container_name your_image_name 启动该容器。将应用的80端口映射到你主机的80端口。你可以将80端口更换为任何未被占用的端口。

至此，项目应该已经部署并正在运行中了。如果想要让应用在后台持续运行，或者在服务器重启后自动启动，你可能需要使用像pm2这样的进程管理器，或者使用docker-compose或kubernetes这样的容器编排工具来进行管理。如果你的应用需要持久化存储或者需要连接的数据库，也需要在服务器上进行相应的配置。

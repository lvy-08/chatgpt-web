#使用Node.js16Alpine作为基础镜像
FROMnode:16-alpineasbuild

ENVNEXT_PUBLIC_API_HOST_URL=""

#设置工作目录
WORKDIR/app

#复制package.json和package-lock.json到容器中
COPYpackage*.json./

#安装依赖
RUNnpminstall

#将应用程序代码复制到容器中
COPY..

#构建TypeScript代码
RUNnpmrunbuild

#使用多阶段构建
FROMnode:16-alpine

WORKDIR/app

#从构建阶段复制构建的产物
COPY--from=build/app./

#暴露3001端口
EXPOSE3000

#启动应用程序
CMD["npm","start"]
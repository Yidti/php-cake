# 使用 nginx:alpine 作为基础镜像
FROM nginx:alpine

# 设置工作目录
WORKDIR /var/www/movie8

# 将自定义的 Nginx 配置文件复制到镜像中
COPY docker/nginx/nginx.conf /etc/nginx/conf.d/default.conf

# 暴露端口 80
EXPOSE 80

# 启动 Nginx
CMD ["nginx", "-g", "daemon off;"]
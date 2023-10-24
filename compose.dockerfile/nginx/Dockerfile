FROM nginx:1.25.1
#维护者信息
LABEL xuweidong="determined_xw@126.com"  
#时区
ENV TZ Asia/Shanghai
RUN date -R


#容器启动时执行指令
CMD ["nginx", "-g", "daemon off;"]

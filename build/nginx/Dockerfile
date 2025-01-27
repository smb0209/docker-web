FROM nginx

RUN cd /etc/nginx/conf.d/ && cp -a default.conf default.conf.bak \
 && rm -f default.conf \
 && ln -s /etc/nginx/tmp/conf/default.conf /etc/nginx/conf.d/default.conf

WORKDIR /etc/nginx

EXPOSE 18080
EXPOSE 80
EXPOSE 443

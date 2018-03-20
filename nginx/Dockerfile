FROM nginx

ADD conf.d/* /etc/nginx/conf.d/

RUN mkdir -p /var/www/html
ADD index.html /var/www/html/index.html

RUN apt-get update -y && apt-get install -y netcat

COPY entrypoint.sh /tmp/entrypoint.sh
RUN chmod +x /tmp/entrypoint.sh

VOLUME ["/etc/nginx/conf.d/"]

CMD [ "sh", "-c", "/tmp/entrypoint.sh" ]

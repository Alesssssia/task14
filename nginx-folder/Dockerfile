FROM nginx:alpine

RUN rm /etc/nginx/conf.d/default.conf
RUN mkdir -p /etc/nginx/certs

RUN touch /var/run/nginx.pid && \
    chown -R nginx:nginx /var/run/nginx.pid /var/cache/nginx /var/log/nginx /etc/nginx /usr/share/nginx/html

USER nginx

COPY ./nginx.conf /etc/nginx/conf.d/default.conf
COPY --chown=nginx:nginx ./certs /etc/nginx/certs
COPY --chown=nginx:nginx ./site/ /usr/share/nginx/html/

EXPOSE 8080

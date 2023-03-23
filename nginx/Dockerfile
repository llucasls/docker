FROM nginx

COPY --chown=nginx:nginx /etc/nginx/conf.d/*.conf /etc/nginx/conf.d/

COPY --chown=nginx:nginx /etc/nginx/sites-available/* /etc/nginx/sites-available/

COPY --chown=nginx:nginx /etc/nginx/sites-enabled/* /etc/nginx/sites-enabled/

EXPOSE 80

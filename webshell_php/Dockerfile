FROM php:8.0-apache

COPY . /var/www/html
RUN chown -R www-data:www-data /var/www/html
RUN rm /var/log/apache2/*
RUN apache2ctl restart
RUN chown -R root:www-data /var/log/apache2/

RUN rm -rf /var/www/html/.docker/

COPY .docker/scr /bin/resetApache
RUN chmod +x /bin/resetApache
RUN apt-get update && apt-get -y install cron supervisor

COPY .docker/mycron /etc/cron.d/mycron
RUN chmod 0644 /etc/cron.d/mycron
RUN crontab /etc/cron.d/mycron

COPY .docker/supervisord.conf /etc/supervisor/conf.d/supervisord.conf
EXPOSE 9005
CMD /usr/bin/supervisord -c /etc/supervisor/conf.d/supervisord.conf

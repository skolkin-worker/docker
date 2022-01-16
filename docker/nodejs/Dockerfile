FROM node:16
RUN npm install npm -g

RUN mkdir /var/www /var/www/app /var/www/app/public
RUN adduser developer
RUN chmod 755 /var/www/app/public
USER developer

WORKDIR /var/www/app
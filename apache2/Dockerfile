FROM webdevops/apache:ubuntu-16.04

MAINTAINER Eric Pfeiffer <computerfr33k@users.noreply.github.com>

ARG PHP_SOCKET=php-fpm:9000

ENV WEB_PHP_SOCKET=$PHP_SOCKET

ENV WEB_DOCUMENT_ROOT=/var/www/public

EXPOSE 80 443

WORKDIR /var/www/public

ENTRYPOINT ["/opt/docker/bin/entrypoint.sh"]

CMD ["supervisord"]

RUN ["a2enmod", "dump_io"]

RUN apt-get update \
	&& apt-get install -y git \
	&& git clone https://github.com/stefanpl/install-scripts /tmp/install-scripts \
	&& /tmp/install-scripts/install_zsh.sh \
	&& /tmp/install-scripts/install_vim.sh 

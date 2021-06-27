FROM phpdockerio/php72-fpm:latest
WORKDIR "/application"

#####################################
# Non-Root User:
#####################################
# User Arg
ARG PUID
ARG PGID
# Use user=larauser in docker-compose comands
# If you want, create a alias to "docker-compose exec --user=larauser"
RUN groupadd -g $PGID larauser && \
    useradd -u $PUID -g larauser -m larauser

# Install selected extensions and other stuff
RUN apt-get update \
    && apt-get -y --no-install-recommends install  php7.2-mysql php7.2-redis \
    && apt-get clean; rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

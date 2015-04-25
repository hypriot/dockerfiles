# Pull from base Ubuntu image
FROM ubuntu

# Do system updates and install dependencies
RUN apt-get update && \
    apt-get -y install reprepro nginx && \
    rm -rf /var/lib/apt/lists/*

# Remove the default Nginx configuration file
RUN rm -v /etc/nginx/nginx.conf

# allow to configure nginx
ADD ./nginx/nginx.conf /etc/nginx/nginx.conf
ONBUILD ADD ./nginx/nginx.conf /etc/nginx/nginx.conf

# forward request and error logs to docker log collector
RUN ln -sf /dev/stdout /var/log/nginx/access.log
RUN ln -sf /dev/stderr /var/log/nginx/error.log

# reprepro setup
ADD ./reprepro/signing.key /signing.key
ADD ./reprepro/public.key /public.key
RUN gpg --import public.key signing.key

RUN mkdir -p /var/repositories/conf
ADD ./reprepro/distributions /var/repositories/conf/distributions
ADD ./reprepro/options /var/repositories/conf/options

# Expose the nginx port
EXPOSE 80 443

VOLUME ["/etc/nginx"]
VOLUME ["/var/packages"]
#
# The command we'll be running when the container starts
CMD ["nginx", "-g", "daemon off;"]

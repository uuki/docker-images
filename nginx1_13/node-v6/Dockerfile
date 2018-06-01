FROM ubuntu:16.04

MAINTAINER Yuichi Aoki <sena.rn68@gmail.com>

# Update
RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-keys $key
RUN apt-get update
RUN apt-get install -y curl gnupg git vim

# Add Repository
RUN echo "deb http://nginx.org/packages/mainline/ubuntu/ xenial nginx" >> /etc/apt/sources.list.d/nginx.list
RUN echo "deb-src http://nginx.org/packages/ubuntu/ xenial nginx" >> /etc/apt/sources.list.d/nginx.list

# Install Node.js 6.x
RUN curl -sL https://deb.nodesource.com/setup_6.x | bash -
RUN apt-get install -y nodejs build-essential
# Install nginx
RUN apt-get install --allow-unauthenticated nginx

# disable Firewall
# RUN ufw disable

# Copy a configuration file from the current directory
# ADD ./nginx.conf /etc/nginx/conf.d/default.conf

# Append "daemon off;" to the beginning of the configuration
# RUN echo "daemon off;" >> /etc/nginx/nginx.conf

# Set the default command to execute when creating a new container
# CMD service nginx start
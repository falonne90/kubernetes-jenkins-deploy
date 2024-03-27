# Use an official base image
FROM centos:7

LABEL description="this image is build for Apache containers"
LABEL maintener="Falonne"

# Set the working directory
# WORKDIR /DOCKER-web-App  

# update package list and install Apache httpd
RUN yum -y update 
RUN yum -y install httpd
RUN yum clean all
# Copy the local code to the container
COPY . /var/www/html/
# COPY webapp/ .
# COPY webapp/index.html .
# COPY webapp/license.txt .
# COPY webapp/js/ js/
# COPY webapp/js/ js/
# COPY webapp/img/ img/
# COPY webapp/css/ css/
# COPY webapp/fonts/ fonts/

# Copy index.html /var/www/html/

# Expose a port (if your application needs it) inthis case i exposed port 80
EXPOSE 80

# Configuration Apache and let it start in the foreground (backgroung)
# RUN echo "ServerName localhost" >> /etc/httpd/conf/httpd.conf

# ENTRYPOINT [ “/usr//sbin/httpd” ]

CMD ["/usr/sbin/httpd", "-D", "FOREGROUND"]







FROM ubuntu:latest
LABEL Author="Sudalaimani"
LABEL Project="Bristacafe"
ENV DEBIAN_FRONTEND=noninteractive
RUN apt update && apt install -y git apache2
WORKDIR /var/www/html
ADD baristacafe.tar.gz /var/www/html/
EXPOSE 80
VOLUME /var/log/apache2
CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]

FROM alpine:3.15
RUN apk add apache2
COPY index.html /var/www/localhost/htdocs/
RUN echo "<center><h1>Hello from ECS</h1><br><h2>Demo2 Terraform<h2><br>$HOSTNAME" > /var/www/localhost/htdocs/index.html
EXPOSE 80
CMD ["/usr/sbin/httpd", "-DFOREGROUND"]

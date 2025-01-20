FROM nginx:alpine
COPY nginx.conf /etc/nginx/nginx.conf
RUN mkdir -p /var/log/nginx
RUN touch /var/log/nginx/jenkins.access.log
RUN touch /var/log/nginx/jenkins.error.log
EXPOSE 9000
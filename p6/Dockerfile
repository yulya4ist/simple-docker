FROM nginx
WORKDIR /home/
COPY ./nginx.conf /etc/nginx/nginx.conf
COPY ./main.c .
COPY ./run.sh .



# RUN apt-get update

# RUN apt-get install -y gcc spawn-fcgi libfcgi-dev 
RUN apt-get update && \
     apt-get install -y gcc spawn-fcgi libfcgi-dev && rm -rf /var/lib/apt/lists/* && \
     chown -R nginx:nginx /etc/nginx/nginx.conf; \
         chown -R nginx:nginx /var/cache/nginx; \
         chown -R nginx:nginx /home; \
         touch /var/run/nginx.pid; \
         chown -R nginx:nginx /var/run/nginx.pid;
USER nginx



ENTRYPOINT ["sh", "./run.sh"]
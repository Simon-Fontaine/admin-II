FROM nginx:latest
RUN apt update && apt upgrade -y
RUN apt install -y nano net-tools
COPY index.html /usr/share/nginx/html
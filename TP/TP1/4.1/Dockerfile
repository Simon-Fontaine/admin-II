FROM httpd:latest

# Supprimer les configurations par défaut et le contenu du DocumentRoot par défaut
RUN rm -f /usr/local/apache2/conf/httpd.conf
RUN rm -f /usr/local/apache2/conf/extra/httpd-vhosts.conf
RUN rm -rf /usr/local/apache2/htdocs/*  

# Copier les fichiers de configuration personnalisés
COPY httpd.conf /usr/local/apache2/conf/httpd.conf
COPY httpd-vhosts.conf /usr/local/apache2/conf/extra/httpd-vhosts.conf

# Copier les sites web dans les répertoires appropriés des VirtualHosts
COPY site-port80 /usr/local/apache2/htdocs/site-port80
COPY site-port8080 /usr/local/apache2/htdocs/site-port8080

# Exposer les ports
EXPOSE 80
EXPOSE 8080
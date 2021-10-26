# About 
ACPC Online websites such as points.acpc, and www.acpc.global

 * acpc-site.yaml file
  * A yaml file creates ACPC.GLOBAL pod website on any ready kubernetes cluster. The pod mounts an external host storage to /var/www/html/wp-content. The pod listen for port 80/tcp.
  * Usage:
     * In spec container template, in env:
      * Change WORDPRESS_DB_HOST that matches your DB server IP
      * Change WORDPRESS_DB_USER that matches your DB Username
      * Change WORDPRESS_DB_PASSWORD that matches your DB password
      * Change WORDPRESS_DB_NAME that matches your DB name
     * git clone https://github.com/acpc-system/acpc-onlinewebapps.git
     * cd  acpc-onlinewebapps
     * kubectl create -f acpc-site.yaml

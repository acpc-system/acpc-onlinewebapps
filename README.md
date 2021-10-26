# About 
ACPC Online websites such as points.acpc, and www.acpc.global

# acpc-site.yaml file
  * A yaml file creates ACPC.GLOBAL pod website on any ready kubernetes cluster. The pod mounts an external host storage to /var/www/html/wp-content. The pod listens for port 80/tcp.
  * Usage:
     * In spec container template, in env:
      * Change WORDPRESS_DB_HOST that matches your DB server IP
      * Change WORDPRESS_DB_USER that matches your DB Username
      * Change WORDPRESS_DB_PASSWORD that matches your DB password
      * Change WORDPRESS_DB_NAME that matches your DB name
     * git clone https://github.com/acpc-system/acpc-onlinewebapps.git
     * cd  acpc-onlinewebapps
     * kubectl create -f acpc-site.yaml
  * To do:
     * Change WORDPRESS_DB_USER, and WORDPRESS_DB_PASSWORD to a kubernetes secrets object.
     * Adding a cluster IP service to expose this pod
     * Adding an ingress rule to publish the pod through nginx ingress load balancer.
# acpc-points.yaml file
  * A yaml file creates points.acpc.global website on any ready kubernetes cluster. The pod mounts an external host storage to /points. The pod listens for port 80/TCP. in a namespace called acpc
  * Creates a ClusterIP service called acpc-points-service in acpc namespaces that expose the port 80 to the kubernetes cluster.
  * Creates an ingress rule to publish website points.acpc.global
  * Usage:
    * Change the pathes to match your setup
    * git clone https://github.com/acpc-system/acpc-onlinewebapps.git
    * cd acpc-onlinewebapps
    * kubectl create -f acpc-points.yaml

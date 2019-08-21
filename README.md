README.MD

El Web_full_Stack recoge los archivos docker_compose.yml y Dockerfile de los diferentes dockers y containers que ejecutarán
toda una web de Wordpress, en principio, con el siguiente nivel de detalle:
  1. frontend que será un container de traefik que se conectará en principio a los container locales del nodo de Varnish, contendrá los certificados SSL (obtenidos de la solución gratuita Let'sEncrypt) y será el punto de entrada https para los usuarios, este container realmente estará fuera del docker-compose pero detectará los diferentes dockers que se vayan levantando del stack: Varnish-Apache que será ejecutados por cada hosting, 
  2. un cacheador web que será un Varnish que se ejecutará parametrizado para el backend de aplicaciones pertinente, de forma que con reglas genéricas podremos acceder a un: Wordpress, Drupal, WooComerce, Prestashop o cualquier otro CMS u aplicación que se ejecute en los containers de Apache, 
  3. Un contenedor de Apache, que como características será:
    a. Apache 2.4
    b. Tendrá Php en la versión requerida mínima de las aplicaciones web que ejecute el core de la aplicación o la necesaria para los plugin de la misma, 
    c. montará un volumen donde se localizará los archivos con el Core de la aplicación Web, los archivos de imágenes y contenidos, 
No incluimos en este Stack el backend de MySQL ya que es mejor que haya un servicio, local o en otro nodo, exclusivamente dedicadoa estos menesteres de almacenamiento,backup y restore de datos de las diferentes bases de datos. 
El objetivo es que 

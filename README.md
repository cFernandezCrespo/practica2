# practica2
# Tarea 2

<h2>Descarga la imagen 'httpd' y comprueba que está en tu equipo.
Crea un contenedor con el nombre 'asir_httpd'.</h2>

~~~
docker run -dit --name asir_httdp -p 8000:80 httpd:2.4
~~~

Con este comando creamos un contenedor con la imagen, si no la tuvieramos la descargaría de cero.

~~~
docker images
~~~

Con esta linea de comando podemos ver todas las imagenes descargadas en nuestro ordenador.
<br/>

<h2>Mapea el puerto 80 del contenedor con el puerto 8000 de tu máquina.</h2>
<br/>
Utiliza -v "$PWD"/htdocs:/usr/local/apache2/htdocs/
<br/>
<br/>

~~~
docker run -dit --name asir_httdp -p 8000:80 -v "$PWD"/htdocs:/usr/local/apache2/htdocs  httpd:2.4
~~~

De esta forma hariamos un comando que mapee el puerto 80 con el 8000.

<h2>Utiliza bind mount para que el directorio del apache2 'htdocs' este montado un directorio que tu elijas.</h2>
<br/>

~~~
docker run -dit --name asir_httdp -p 8000:80 -v "$PWD"/htdocs:/usr/local/apache2/htdocs  httpd:2.4
~~~

Es el mismo comando de antes pero aqui la parte importante es a partir del -v ya que le enseñamos la nueva ruta a nuestro html.

<h2>Realiza un 'hola mundo' en html y comprueba que accedes desde el navegador.</h2>
<br/>
Creamos un index.html en la carpeta que dirigimos antes el apache osea htdocs y de esta forma cuando busquemos el puerto en localhost aparecerá nuestro hola mundo.
<br/>
<br/>
<h2>Crea un contenedor 'asir_web1' que use este mismo directorio para 'htdocs' y el puerto 8000</h2>
<br/>

~~~
docker run -dit --name asir_web1 -p 8000:80 -v "$PWD"/htdocs:/usr/local/apache2/htdocs  httpd:2.4
~~~

En esencia es el mismo comando de antes pero cambiando el nombre que es lo unico que nos piden.
<br/>
<h3>Utiliza Code para hacer un hola mundo en html</h3>
<br/>
<br/>
Entras en el html e introduces la información que necesites haciendo un html formateado de forma correcta es decir con la etiqueta html body y demás.
<br/>
<br/>
<h2>Crea otro contenedor 'asir_web2' con el mismo volumen y a otro puerto, por ejemplo 9080.</h2>
<br/>

~~~
docker run -dit --name asir_web2 -p 9080:80 -v "$PWD"/htdocs:/usr/local/apache2/htdocs  httpd:2.4  
~~~

El comando es en esencia el mismo pero cambiamos el nombre y el puerto.

<h2>Comprueba que los dos servidores 'sirven' la misma página, es decir, cuando consultamos en el navegador:</h2>
<br/>
http://localhost:9080 
http://localhost:8000
<br/>
Tienen que salir la misma página web
<br/>
Ponemos en el buscador localhost:"el puerto" y deberia aparecernos las siguientes paginas

![ puerto 8000 ](./imagenes/8000.png)
![ puerto 9080 ](./imagenes/9080.png)
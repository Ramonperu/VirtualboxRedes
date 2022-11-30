# VirtualBox NET
*Noviembre 30 de 2022*, Ramón Peinado Ruiz



Para configurar la red en virtual box primero hemos de crear nuestra red NAT:

<img src="/img/1ºimagenn.png" alt="1ºimagenn"  />

Posteriormente hemos de conectar las maquinas a esta red:

**WSERVER 2019:**

<img src="/img/2ºimagenn.png" alt="2ºimagenn" style="zoom: 67%;" />

**W10:**

<img src="/img/3ºimagenn.png" alt="3ºimagenn" style="zoom: 67%;" />

**CENTOS:**

<img src="/img/4ºimagenn.png" alt="4ºimagenn" style="zoom: 67%;" />





***PERTENENCIA A LA RED:***





A continuación vamos a comprobar si las maquinas están conectadas a la misma red, comparten el adaptador de red y disponen de acceso a la red:





W10:

Ejecutamos el comando ipconfig en windows.

<img src="/img/5ºimagenn.png" alt="5ºimagenn" style="zoom: 67%;" />

​				IP-> 										192.26.0.4

​				MASCARA -> 						 255.255.255.0 

​				Puerta de enlace-> 			  192.26.0.1

​	Conexión a internet:

<img src="/img/6ºimagenn.png" alt="6ºimagenn" style="zoom: 33%;" />







CENTOS:



Primero hemos de ver si la interfaz de  red esta conectada con el comando 	<nmcli device status>.

<img src="/img/7ºimagenn.png" alt="7ºimagenn"  />

Tras esto debemos activar la interfaz de red con el *<nmcli device connect "enp0s3" >* y comprobaremos el estado con <*nmcli connection show* "enp0s3">.

<img src="/img/8ºimagenn.png" alt="8ºimagenn"  />

Podremos entonces los datos de nuestra red

<img src="/img/9ºimagenn.png" alt="9ºimagenn"  />

​				IP-> 										192.26.0.5

​				MASCARA(24) -> 						 255.255.255.0 

​				Puerta de enlace-> 			  192.26.0.1

​	Conexión a internet(?):



WSERVER 2019:

Ejecutamos el comando ipconfig en el cmd.

<img src="/img/10ºimagenn.png" alt="10ºimagenn"  />

​				IP-> 										192.26.0.6

​				MASCARA -> 						 255.255.255.0 

​				Puerta de enlace-> 			  192.26.0.1

​	Conexión a internet:

<img src="/img/11ºimagenn.png" alt="11ºimagenn"  />

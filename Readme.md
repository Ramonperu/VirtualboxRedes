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

------



A continuación vamos a comprobar si las maquinas están conectadas a la misma red, comparten el adaptador de red y disponen de acceso a la red:





W10:

Ejecutamos el comando <  ipconfig > en windows.

<img src="/img/5ºimagenn.png" alt="5ºimagenn" style="zoom: 67%;" />

​				IP-> 										192.26.0.4

​				MASCARA -> 						 255.255.255.0 

​				Puerta de enlace-> 			  192.26.0.1

​	Conexión a internet:

<img src="/img/6ºimagenn.png" alt="6ºimagenn" style="zoom: 33%;" />







CENTOS:

Ejecutamos el comando *< ifconfig >* en el terminal después de activar nuestra interfaz en configuración.

​				IP-> 										192.26.0.7

​				MASCARA -> 						 255.255.255.0 

<img src="/img/7ºimagenn.png" alt="7ºimagenn"  />

Como vemos la puerta de enlace no sale reflejada hemos de ejecutar el comando *< route -n >*

<img src="/img/8ºimagenn.png" alt="8ºimagenn"  />

​				Puerta de enlace-> 			  192.26.0.1

​	Conexión a internet:

<img src="/img/9ºimagenn.png" alt="9ºimagenn"  />









WSERVER 2019:

Ejecutamos el comando ipconfig en el cmd.

<img src="/img/10ºimagenn.png" alt="10ºimagenn"  />

​				IP-> 										 

​				MASCARA -> 						 255.255.255.0 

​				Puerta de enlace-> 			  192.26.0.1

​	Conexión a internet:

<img src="/img/11ºimagenn.png" alt="11ºimagenn" style="zoom: 33%;" />



------





DIAGRAMA DE LA RED:



<img src="/img/12ºimagenn.png" alt="12ºimagenn"  />







**COMPROBACION DE PINGS ENTRE LAS MAQUINAS**

------

Para que las maquinas consigan hacer ping entre ellas hemos de activar las reglas del protocolo ICMP dentro del firewall de Windows en las maquinas de windows.

En linux tendremos que activar el ping desde el terminal con el comando:

*echo 0> /proc/sys/net/ipv4/icmp_echo_ignore_all* 



**-Ping de w10 a centOS:**

<img src="/img/13ºimagenn.png" alt="13ºimagenn"  />



-**Ping de w10 a wserv:**

<img src="/img/16ºimagenn.png" alt="16ºimagenn"  />



------





**-Ping de wserv a linux:**

<img src="/img/14ºimagenn.png" alt="14ºimagenn"  />

**-Ping de wserv a w10:**

<img src="/img/15ºimagenn.png" alt="12ºimagenn"  />



------





**-Ping de centos a w10:**



<img src="/img/17ºimagenn.png" alt="17ºimagenn"  />

-**Ping de centos a wserv:**

<img src="/img/18ºimagenn.png" alt="18ºimagenn"  />

---
title: GESTIÓN DE INCIDENTES DE SEGURIDAD INFORMÁTICA
date: 2021-05-31
---
# MF0488_3: Gestión de incidentes de seguridad informática
# 29/06/2021

## UC0488_3: Detectar y responder ante incidentes de seguridad
- [Perfil Profesional | Detectar y responder ante incidentes de seguridadArchivo](../../libros/modulo_03/01.Perfil-Profesional.-Detectar-y-responder-ante-incidentes-de-seguridad.pdf).
- [Formación | Detectar y responder ante incidentes de seguridadArchivo](../../libros/modulo_03/02.Formación.Detectar-y-responder-ante-incidentes-de-seguridad.pdf).

```
$ apt install mc
```

Cambiar el color del terminal de tu servidor Debian: [link](https://ubunlog.com/como-activar-los-colores-de-la-terminal/).

- suricata para linux
- Veil-Evasion
- Video de Chema Alonso, de como empezar en el Hacking: [Youtube](https://www.youtube.com/watch?v=5zlzdQe7nig).

# 30/06/2021
- [Esquema servidores Web](https://prezi.com/view/FoooXU43LN3kNT8t25FU/).
- [Comandos de Linux](https://prezi.com/i/view/nRotTbKnJVJORghJ7vTz).
- [SIEM Open sourceURL](https://www.dnsstuff.com/free-siem-tools).

## T1. Sistemas de detección y prevención de intrusiones (IDS/IPS)
- [Sistemas de detección y prevención de intrusiones IDS-IPSArchivo](../../libros/modulo_02/03.T1.Sistemas-de-detección-y-prevención-de-intrusiones-IDS-IPS.pdf).

- [Network Security Toolkit (NST)](http://www.networksecuritytoolkit.org/nst/index.html).
- [SELKS](https://www.stamus-networks.com/selks).
- [Open Distro](https://opendistro.github.io/for-elasticsearch/).

**Instalación del paquete de APACHE:**
``` 
$ apt -y install apache2
$ systemctl status apache2
``` 
**Instalación de un firewall en un servidor debian:**
``` 
$ apt install ufw
$ ufw allow ssh
$ ufw allow http
$ ufw allow https
$ ufw status numbered
$ ufw delete 5
```
**Instalación de un WAF (WEB APPLICATION FIREWALL)**

Dispositivo de seguridad diseñado para analizar el tráfico de datos en las aplicaciones Web, monitorizándolas para detectar posibles problemas de seguridad debido a fallos en su codificación mediante al análisis de las variables que llegan a través de las peticiones al servidor Web (GET / POST / PUT / OPTIONS / DELETE / HEADER)
``` 
$ apt install libapache2-mod-security2 -y
$ a2enmod security2
$ systemctl reload apache2
$ nano /etc/apache2/mods-available/security2.conf
$ SecRuleEngine on
``` 
Reglas desarrolladas por la comunidad: CORE RULE SET

Aquí estarán las reglas desarrolladas por la comunidad:
``` 
$ wget https://github.com/coreruleset/coreruleset/archive/v3.3.0.tar.gz
$ tar -xvzf v3.3.0.tar.gz
$ mv coreruleset-3.3.0 /etc/apache2/modsecurity.d
$ cd /etc/apache2/modsecurity.d
$ mv crs-setup.conf.example crs-setup.conf
$ nano /etc/apache2/apache2.conf
    <IfModule security2>
        Include modsecurity.d/crs-setup.conf
        Include modsecurity.d/rules/*.conf
    </IfModule>
$ systemctl restart apache2
``` 
# 1/7/2021
## T4. Respuesta ante incidentes de seguridad
- [Respuesta ante incidentes de seguridad Archivo](../../libros/modulo_03/04.T4.Respuesta-ante-incidentes-de-seguridad.pdf).
- [¿Qué es un SOC?](https://www.youtube.com/watch?v=3S01vLlvubE).
- [CERTs Europeos](http://www.enisa.europa.eu/activities/cert/background/inv).
- [CERTs internacionales](http://www.internationalcybercenter.org/).

- Cambiar el color del teminal: [zsh](https://terminaldelinux.com/terminal/introduccion/instalacion-zsh/).

**Fail2ban**
``` 
$ apt install fail2ban
$ systemctl status fail2ban
$ tail -f /var/log/fail2ban.log
$ nano /etc/fail2ban/jail.d/defaults-debian.conf

[apache-shellshock]
enabled = true
[apache-modsecurity]
enabled = true
[apache-fakegooglebot]
enabled = true
[apache-botsearch]
enabled = true
[apache-nohome]
enabled = true
[apache-overflows]
enabled = true
[apache-noscript]
enabled = true
[apache-badbots]
enabled = true
[apache-auth]
enabled = true

$ systemctl restart fail2ban
$ tail -f /var/log/apache2/error.log

ssh root@ip (fallar varias veces)

gobuster dir --url http://217.76.139.144/ -w /usr/share/wordlists/dirb/common.txt -q -n -e
wpscan --url 217.76.139.144
``` 
# 02/07/2021

# 05/07/2021

- [Ejecicio:](https://www.hackers-arise.com/post/2016/12/05/web-app-hacking-hacking-form-authentication-with-burp-suite).
- [Ejecicio SSH:](https://www.hackingarticles.in/ssh-penetration-testing-port-22/).
- [Ejercicio Telnet](https://www.hackingarticles.in/penetration-testing-telnet-port-23/).

- [Implantación y puesta en producción de sistemas IDS/IPS](../../libros/modulo_03/05.T2.Implantación-y-puesta-en-producción-de-sistemas-IDS-IPS.pdf).
- [Práctica Snort](../../libros/modulo_03/06.Práctica-4.-Primeros-pasos-con-Snort.docx).

```
$ snort -W
$ snort -i 2 -l ../log
```

-[Instalación en Windows](https://flylib.com/books/en/2.12.1/installing_snort_on_windows.html).

-[Instalación en debian](https://upcloud.com/community/tutorials/installing-snort-on-debian/).

https://conpilar.es/como-instalar-snort-y-uso-en-ubuntu-15-04/

https://www.nomoreransom.org/

# 06/07/2021

- [Página oficial de Snort - Snort.org](https://snort.org/)
- [Página ofical de Snort para Windows - Winsnort.com](http://www.winsnort.com/)
- [Página ofical de Snort - NIDS para Win32](https://www.snort.org/faq/readme-win32)
- [Alarmas en Snort - The Hacker News](http://thehackerway.com/tag/snort-alarmas/)

```
Práctica 1L. Métodos HTTP
$ touch /var/www/html/hola.html
echo "Holaaaaaaa cara colaaaaaa" > /var/www/html/hola.html
$ apt install telnet
$ apt install apache2

1.  Petición 200 ok
telnet 127.0.0.1 80

GET /hola.html HTTP/1.1
Host: servidor

2. Da solo 1 intro., y espera a que el servidor te eche. Tiempo de espera agotado
telnet 127.0.0.1 80

GET /hola.html HTTP/1.1
Host: servidor

3. Sólo la comunicación, la cabecera:
telnet 127.0.0.1 80

HEAD /hola.html HTTP/1.1
Host: servidor

4.  No está implementado el método:
telnet 127.0.0.1 80

TRAEME /hola.html HTTP/1.1
Host: servidor

5.  No existe la URL que pido:
telnet 127.0.0.1 80

GET /login.php HTTP/1.1
Host: servidor
```

# 07/07/2021
## T5. Proceso de notificación y gestión de intentos de intrusión

- [Proceso de notificación y gestión de intentos de intrusión](../../libros/modulo_03/07.T5.Proceso-de-notificación-y-gestión-de-intentos-de-intrusión.pdf).
- [Infografía Snort](https://snort-org-site.s3.amazonaws.com/production/document_files/files/000/000/116/original/Snort_rule_infographic.pdf?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAIXACIED2SPMSC7GA%2F20210719%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20210719T232032Z&X-Amz-Expires=172800&X-Amz-SignedHeaders=host&X-Amz-Signature=944c23fbd0fa1d98dc2df6680e298bf082246ab4a6b73f60793b8aaf7d2eff44)
```
Práctica 5L. IDS / IPS
SNORT - Instalación y configuración
Instalación SNORT

$ apt-cache search snort
$ apt install snort
$ snort -V
$ cd /etc/snort
$ nano /etc/snort/snort.conf

    #Poner la IP del servidor
    ipvar HOME_NET 5.196.224.111

    #Comentar y ponemos nuestra IP
    #ipvar EXTERNAL_NET any

    #Descomentar
    ipvar EXTERNAL_NET !$HOME_NET

    #Comentar todas las lineas de rules, y dejamos solo:
    # site specific rules
    include $RULE_PATH/local.rules

$ nano /etc/snort/rules/local.rules
    alert icmp $EXTERNAL_NET any -> $HOME_NET any (msg:"Me están pingueandoooooo";sid:500;rev:4)
    alert tcp $EXTERNAL_NET any -> $HOME_NET 23 (msg:"Intento de TELNET";sid:504440;rev:4)    

$ systemctl restart snort

$ snort -D -i ens192 -c /etc/snort/snort.conf -A full
$ tail -f /var/log/snort/alert

$ snort -r /var/log/snort/snort.log.1584xxxxxx

Hacemos un PING sobre el servidor y con el PUTTY nos conectamos por el puerto 23

https://snowl.io/downloads/


https://wiki.salud.gob.sv/wiki/Instalaci%C3%B3n_de_Snort_en_Debianv

$ apt install tcpdump
```
# 08/07/2021

- [Material para Snort](../../libros/modulo_03/08.material.zip).
- [Reglas actualizadas de Snort](https://www.snort.org/downloads).
- [Snort Cookbook](http://commons.oreilly.com/wiki/index.php/Snort_Cookbook).
- [Snort para Dummies](../../libros/modulo_03/09.Snort-For-Dummies.pdf)
- [Instalación de bruteshark](https://github.com/odedshimon/BruteShark/).

## T3. Control de código malicioso

- [Control de código malicioso | diapositiva](../../libros/modulo_03/10.T3.Control-de-código-malicioso-V3.0.pdf).
- [TCPView, Process Explorer, Autoruns, winmd5free](../../libros/modulo_03/11.Apps-Tools.zip).
- [RAT | Programa de análisis de troyanos](https://jejo.es/posts/pentesting/analisis_forense/any.run/rat_macros_excel_bp9_2.png).

- [Programa de escaneo de puertos](https://docs.microsoft.com/en-us/sysinternals/downloads/tcpview).
- [Programa que muestra los procesos del sistema](https://docs.microsoft.com/en-us/sysinternals/downloads/procmon).
- [Página de descarga de programas | driverview](https://www.nirsoft.net/).
- [Programa que muestra los programas que se inician](https://docs.microsoft.com/en-us/sysinternals/downloads/autoruns).

VSFTPd

1. Instalación del VSFTPd
2. Permitir usuarios anónimos
3. Creación de usuarios seguros
4. VSFTPd + SSL

```
# instalar ftp
$ apt install vsftpd
$ nano /etc/vsftpd.conf
    #añadir puerto minimo y maximo
    pasv_min_port=10090
    pasv_max_port=10100 

$ systemctl restart vsftpd
$ systemctl status vsftpd

# dar permiso en el firewall
$ ufw allow 10090:10100/tcp

#subir archivos
$ nano /etc/vsftpd.conf
    write_enable=YES

# Permitir usuarios anónimos
$ nano /etc/vsftpd.conf
    #Ponerlo a YES
    anonymous_enable=YES

    #Añadir no pedir contraseña y el directorio por defecto, se puede cambiar
    no_anon_password=YES
    anon_root=/home/debian

#Enjaulado de usuarios (no ver la estructura de directorios)
$ nano /etc/vsftpd.conf
    #Descomentar esta línea
    chroot_local_user=YES

    #Añadimos
    allow_writeable_chroot=YES

# Dar permisos 750 sobre la carpeta asociada al ftp (/home/tuUsuario), sino, no podrías acceder nunca, te hecha de la conexión    
$ chmod 750 /home/tusuario

#Activar SSL
$ nano /etc/vsftpd.conf
ssl_enable=YES

# ver estado y reinicio
$ systemctl restart vsftpd
$ systemctl status vsftpd

# Fail2ban
$ nano /etc/fail2ban/jail.d/defaults-debian.conf
    [vsftpd]
    enabled = true
$ systemctl restart fail2ban
$ tail -f /var/log/fail2ban.log
```
# 12/07/2021
## T6. Análisis forense informático

- [Análisis forense Slices](../../libros/modulo_03/12.T6.Análisis forense.pdf)
- [Asociación Nacional de Tasadores y Peritos Judiciales InformáticosURL](https://antpji.org/)
- [Wiki Mobile](https://appsecwiki.com/#/mobilesecurity)
- [Infografía de análisis forense informáticoURL](http://eforensicsmag.com/wp-content/uploads/2015/05/Prudential-Associates_IGDT_d04-d19-d22-d24_2-1.jpg)
- [Ejemplos metadatosURL](https://www.elladodelmal.com/2012/04/analisis-forense-de-metadatos-15.html)
- [ENISA](../../libros/modulo_03/14.ETL2020-ENISA_List_of_Top_15_Threats_eBook_EN_ES.pdf)
- [Web ENISA](../../libros/modulo_03/15.ETL2020-Web_Based_Attacks_eBook_EN_ES.pdf)
- [Anális forense](../../libros/modulo_03/16.incibe_toma_evidencias_analisis_forense.pdf)

# 14/07/2021

```
Permitir firewall puerto 91 tcp
$ ufw allow 91/tcp

$ dd if=/dev/sda conv=sync,noerror | nc ip 91

en el servidor
$ nc -l -p 91 -w 100000 > sdb.db

$ md5sum nombre_archivo
$ sh1sum nombre_archivo
$ sh512sum nombre_archivo
```
- [Análisis forense Slices](../../libros/modulo_03/17.T6.2-Análisis-forense.pdf)
- [Supuesto práctico](18.análisis-forense.txt)

```
 driverquery | more
 systeminfo | find /i "fecha de"
```
- [Nirsoft](https://launcher.nirsoft.net/downloads/index.html)
- [Caine](https://www.caine-live.net/)
- [Web de la MV Metasplotable2](https://sourceforge.net/projects/metasploitable/files/latest/download)

# 15/07/2021

- [Configuración Postfix](https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-postfix-as-a-send-only-smtp-server-on-ubuntu-18-04-es)

```
$ apt install postfix
$ apt install mailutils

$ sudo ufw allow 25
$ sudo ufw allow smtp
$ sudo ufw allow 143
$ sudo ufw allow 993
$ sudo ufw allow 110
$ sudo ufw allow 995
```

# 16/07/201

- Trasteando con máquinas virtuales.
- Examen, realizando preguntas.




## Examen - Gestión de incidentes de seguridad informática

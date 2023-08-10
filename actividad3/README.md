# PARTE1
### 1.CREACION DE USUARIOS
paula@LAPTOP-0O53IDSA:~$ sudo useradd usuario1
[sudo] password for paula:
paula@LAPTOP-0O53IDSA:~$ sudo useradd usuario2
paula@LAPTOP-0O53IDSA:~$ sudo useradd usuario3

### 2.ASIGNACION DE CONTRASEÑAS
paula@LAPTOP-0O53IDSA:~$ sudo passwd usuario1
New password:u1
Retype new password:u1
passwd: password updated successfully
paula@LAPTOP-0O53IDSA:~$ sudo passwd usuario2
New password:u2
Retype new password:u2
passwd: password updated successfully
paula@LAPTOP-0O53IDSA:~$ sudo passwd usuario3
New password:u3
Retype new password:u3
passwd: password updated successfully

### 3.INFORMACION DE USUARIOS
paula@LAPTOP-0O53IDSA:~$ id usuario1
uid=1001(usuario1) gid=1001(usuario1) groups=1001(usuario1)

### 4.ELIMINAR USUARIO 3
paula@LAPTOP-0O53IDSA:~$ sudo userdel usuario3

# PARTE2
### 1.CREACION DE GRUPOS
paula@LAPTOP-0O53IDSA:~$ sudo groupadd grupo1
paula@LAPTOP-0O53IDSA:~$ sudo groupadd grupo2

### 2.AGREGAR USUARIOS A GRUPOS
paula@LAPTOP-0O53IDSA:~$ sudo usermod -aG grupo1 usuario1
paula@LAPTOP-0O53IDSA:~$ sudo usermod -aG grupo2 usuario2

### 3.VERIFICAR MEMBRESIA
paula@LAPTOP-0O53IDSA:~$ groups usuario1
usuario1 : usuario1 grupo1
paula@LAPTOP-0O53IDSA:~$ groups usuario2
usuario2 : usuario2 grupo2

### 4.ELIMINAR GRUPO 2
paula@LAPTOP-0O53IDSA:~$ sudo groupdel grupo2

# PARTE 3
### 1.CREAR ARCHIVOS Y DIRECTORIOS
paula@LAPTOP-0O53IDSA:~$ sudo su usuario1
usuario1@LAPTOP-0O53IDSA:/home/paula$ cd /
usuario1@LAPTOP-0O53IDSA:/$ cd home
usuario1@LAPTOP-0O53IDSA:/home$ cd usuario1
usuario1@LAPTOP-0O53IDSA:~$ echo "2017008231" > ~/archivo1.txt
usuario1@LAPTOP-0O53IDSA:~$ mkdir ~/directorio1
usuario1@LAPTOP-0O53IDSA:~$ echo "Paula García" > ~/directorio1/archivo2.txt

### 2.VERIFICAR PERMISOS
usuario1@LAPTOP-0O53IDSA:~$ ls -l ~/archivo1.txt
-rw-rw-r-- 1 usuario1 usuario1 11 Aug  9 18:19 /home/usuario1/archivo1.txt
usuario1@LAPTOP-0O53IDSA:~$ ls -ld ~/directorio1
drwxrwxr-x 2 usuario1 usuario1 4096 Aug  9 18:19 /home/usuario1/directorio1
usuario1@LAPTOP-0O53IDSA:~$

### 3.MODIFICAR PERMISOS MODO NUMERICO
usuario1@LAPTOP-0O53IDSA:~$ chmod 640 ~/archivo1.txt

### 4.MODIFICAR PERMISOS METODO SIMBOLICO
usuario1@LAPTOP-0O53IDSA:~$ chmod u+x ~/directorio1/archivo2.txt

### 5.CAMBIAR EL GRUPO PROPIETARIO
usuario1@LAPTOP-0O53IDSA:~$ sudo chown :grupo1 ~/directorio1/archivo2.txt
[sudo] password for usuario1:
Sorry, try again.
[sudo] password for usuario1:
usuario1 is not in the sudoers file.  This incident will be reported.
usuario1@LAPTOP-0O53IDSA:~$ chown :grupo1 ~/directorio1/archivo2.txt

### 6.CONFIGURAR PERMISOS DIRECTOPRO 
usuario1@LAPTOP-0O53IDSA:~$ chmod 750 ~/directorio1
### 7.COMPROBACION DE ACCESO
paula@LAPTOP-0O53IDSA:/home/usuario1$ su usuario2
Password:
usuario2@LAPTOP-0O53IDSA:/home/usuario1$ cat ./directorio1/archivo2.txt
cat: ./directorio1/archivo2.txt: Permission denied
usuario2@LAPTOP-0O53IDSA:/home/usuario1$ cat ./archivo1.txt
cat: ./archivo1.txt: Permission denied

### 8.VERIFICACION FINAL 
paula@LAPTOP-0O53IDSA:/home/usuario1$ su usuario1
Password:
usuario1@LAPTOP-0O53IDSA:~$ ls -l ./archivo1.txt
-rw-r----- 1 usuario1 usuario1 11 Aug  9 18:19 ./archivo1.txt
usuario1@LAPTOP-0O53IDSA:~$ ls -ld ./directorio1
drwxr-x--- 2 usuario1 usuario1 4096 Aug  9 18:19 ./directorio1
usuario1@LAPTOP-0O53IDSA:~$


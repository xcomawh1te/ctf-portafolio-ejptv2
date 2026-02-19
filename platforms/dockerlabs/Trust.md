Maquina Dockerlabs - Trust
Nivel: Easy


## 1. Reconocimiento
Habilitamos la maquina y nos entrega su io -> 172.18.0.2<br>

<img width="918" height="174" alt="image" src="https://github.com/user-attachments/assets/52b50d19-4258-4e06-861b-8e3459fc4be9" /><br>


## 1. Enumeración

sudo nmap -p- -sS -sC -sV --min-rate 5000 -n -vvv -Pn 172.18.0.2<br>
<img width="885" height="551" alt="image" src="https://github.com/user-attachments/assets/c722cee0-4293-4cab-8cb7-1080ffe2f371" /><br>

Identificamos 2 puertos el 22 y el 80<br>

<img width="1343" height="548" alt="image" src="https://github.com/user-attachments/assets/5aff5cb6-c25e-45b0-b458-360a28e0bb08" /><br>

<img width="1303" height="532" alt="image" src="https://github.com/user-attachments/assets/22c0e376-3d17-4d7f-82e5-c524a03dbdd4" /><br>


Realizar Fuzzing Web mediante Herramienta Dirb <br>

<img width="520" height="370" alt="image" src="https://github.com/user-attachments/assets/e4a4a52e-ff5a-48c3-8ef1-b1231307b11d" /><br>

Tambien probamos con Gobuster con los parametros  -x con extensiones para encontrar archivos que nos puedan servir<br>

obuster dir -u http://172.18.0.2/ -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -x html,php,sh,py  <br>

<img width="1062" height="403" alt="image" src="https://github.com/user-attachments/assets/7537c149-02a0-4da0-a4dd-8280d7067605" /> <br>

Encontraremos un recurso llamado  /secret.php la cual adjuntamos a nuestro sitio  <br>

<img width="874" height="531" alt="image" src="https://github.com/user-attachments/assets/83ac4623-ffaa-483c-8b14-bc33c834a5ad" /> <br>

## 3. Explotación

Como dato sabemos que hay un usuario que se llama mario, por lo cual lo usaremos para encontrar su clave mediante un ataque hydra al puerto ssh <br>
hydra -l mario -P /home/kali/rockyou.txt ssh://172.18.0.2 -t 64  <br>

<img width="1337" height="259" alt="image" src="https://github.com/user-attachments/assets/6cdd5879-e271-48d5-be4c-c384d1696779" />  <br>

Una ves obtenida la contraseña, nos conectamos por ssh utilizando las credenciales que obtuvimos <br>
ssh mario@172.18.0.2  y luego verificamos nuestro usuario con whoami <br>

<img width="829" height="340" alt="image" src="https://github.com/user-attachments/assets/080f3839-b8ae-408a-a7e1-406bf1229da0" /> <br>

Podemos ir revisando cada uno de los ficheros y ver si encontramos algo que nos pueda ayudar <br>
<img width="892" height="539" alt="image" src="https://github.com/user-attachments/assets/0553d1d6-29b6-4a23-9c71-01b386956eed" /> <br>


Encontrar binarios que podamos ejecutar como propietario del sistema con find / -perm -4000 2>/dev/null <br>

<img width="505" height="182" alt="image" src="https://github.com/user-attachments/assets/4e07d717-1385-4461-a6d2-dc2bf79d3023" /> <br>

## 4. Escalada de Privilegios

También podemos provar que comandos puede ejecutar el usuario mario como propietario del sistema para encontrar alguna vulnerabilidad <br>

<img width="938" height="146" alt="image" src="https://github.com/user-attachments/assets/42178021-6b87-4c08-8b1b-a23b22d84661" /> <br>

Usamos el comando como root
<img width="419" height="22" alt="image" src="https://github.com/user-attachments/assets/f1e56856-27ed-4ec2-9746-1e101f9b237f" /> <br>
Lo cual nos lleva al editor Vim, usamos !/bin/bash , la cual nos permitira acceder a root <br>
<img width="1235" height="561" alt="image" src="https://github.com/user-attachments/assets/8e62746e-2d44-4063-8ca7-99c7a4774017" /><br>

para finalizar tenemos opciones para escalar privilegios como root <br>
<img width="432" height="85" alt="image" src="https://github.com/user-attachments/assets/78f7ac26-2995-4ce9-b6c9-f9264b6718b0" /> <br>


## 5. Aprendizajes

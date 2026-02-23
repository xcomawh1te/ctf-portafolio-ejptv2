# Máquina Microchoft - The Hackers Labs
Dificultad: Easy  
Sistema: Windows 7


<img width="1356" height="517" alt="image" src="https://github.com/user-attachments/assets/53631ad1-26bd-463f-94a8-75e87693e494" />


## 1. Reconocimiento
Partimos Verificando el rango de ip para poder luego encontrar la ip de la maquina victima <br>
<img width="1174" height="322" alt="image" src="https://github.com/user-attachments/assets/c69c269a-f40e-4ceb-ad84-7cdf7daaa24f" /> <br>
<img width="972" height="55" alt="image" src="https://github.com/user-attachments/assets/2b285319-2b5c-4159-964a-f69e7c85b5ac" /><br>
Encontramos la ip 192.168.199.42 <br>
<img width="1263" height="228" alt="image" src="https://github.com/user-attachments/assets/4bc65160-bf56-40c6-87a9-39e5702679e7" /> <br>




## 2. Enumeración

<img width="1202" height="557" alt="image" src="https://github.com/user-attachments/assets/dfd36807-dbeb-474a-a4e9-606d3e4cb321" /><br>

Nos vamos a enfocar en el puerto 445 en la cual nos detecta uyna maquina windows 7 <br>

<img width="1272" height="556" alt="image" src="https://github.com/user-attachments/assets/c8bb2b62-390e-4633-92b3-9f6387f640fa" /><br>

<img width="1253" height="251" alt="image" src="https://github.com/user-attachments/assets/35ff8149-83b2-4615-9c39-dc962b7a1372" /><br>

<img width="1279" height="116" alt="image" src="https://github.com/user-attachments/assets/31b9ec0e-3fb6-48c3-862e-f1e267e6c5f7" /><br>

<img width="1212" height="538" alt="image" src="https://github.com/user-attachments/assets/b6d53453-8df1-4370-b8e6-ae314de90449" /><br>



## 3. Explotación

<img width="1255" height="528" alt="image" src="https://github.com/user-attachments/assets/23891e76-f518-4970-9161-c395c57a12b8" /><br>

<img width="1342" height="494" alt="image" src="https://github.com/user-attachments/assets/662336e9-cc04-4609-8b80-aeb8287bbf4a" /><br>

<img width="1340" height="559" alt="image" src="https://github.com/user-attachments/assets/19081f39-93e9-4b4d-975b-6e55609a1227" /><br>

<img width="568" height="517" alt="image" src="https://github.com/user-attachments/assets/ef6367bb-08d7-4b06-98a5-f839381385a1" /><br>

<img width="683" height="554" alt="image" src="https://github.com/user-attachments/assets/dcf54d0c-aaf2-4642-9579-6fbf9d187f21" /><br>


Flag Lola User<br>
<img width="472" height="211" alt="image" src="https://github.com/user-attachments/assets/09194120-f078-45ad-984a-a49d7df5273f" /><br>
<img width="497" height="59" alt="image" src="https://github.com/user-attachments/assets/d74170e9-42c6-4859-96a9-663df8c26aa6" /> <br>


Flag Admin User<br>
<img width="564" height="330" alt="image" src="https://github.com/user-attachments/assets/dea62f01-1da0-42de-ba5b-55aaf8346631" />


## 4. Escalada de privilegios

## 5. Aprendizajes

<strong>ENUMERACIÓN DE SMB:</strong><br>
Identificación de recursos compartidos en servicios SMB y posibles vulnerabilidades.<br>

<strong>ENUMERACIÓN DE APLICACIÓN WEB:</strong><br>
Exploración de contenido web visible y oculto para detectar puntos de entrada.<br>

<strong>ENUMERACIÓN DE SERVICIOS:</strong><br>
Identificación de los servicios que corren en los puertos abiertos, incluyendo versiones.<br>

<strong>ESCANEO DE PUERTOS TCP:</strong><br>
Detección de puertos abiertos en la máquina objetivo mediante escaneo TCP.<br>

<strong>EXPLOTACIÓN CON METASPLOIT:</strong><br>
Uso de la herramienta Metasploit para lanzar exploits conocidos contra servicios vulnerables.<br>

<strong>EXPLOTACIÓN DE ETERNALBLUE:</strong><br>
Explotación de la vulnerabilidad MS17-010 para ejecución remota de código en Windows.<br>

<strong>SESIÓN METERPRETER:</strong><br>
Acceso interactivo al sistema comprometido a través de una shell avanzada de Metasploit.







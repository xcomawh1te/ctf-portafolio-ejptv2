# Machine: WalkingCMS - Dockerlabs
Dificultad: Easy  
Sistema: Linux , CMS Wordpress  
<img width="1356" height="517" alt="image" src="https://github.com/user-attachments/assets/c92b6528-de48-4118-92ff-be682b5739d1" />

## 1. Reconocimiento
Habilitamos la maquina y nos entrega su io -> 172.17.0.2/br
<img width="587" height="138" alt="image" src="https://github.com/user-attachments/assets/9ba82191-6215-41fc-9644-2c5785a3f189" />

## 2. Enumeración

Escaneo de nmap puertos y servicios
<img width="855" height="396" alt="image" src="https://github.com/user-attachments/assets/d6d65a01-2661-4892-b0eb-08e03cc3d258" />
<img width="835" height="363" alt="image" src="https://github.com/user-attachments/assets/dc8795e2-5d03-4d3b-aefb-3da024b20f0b" /> 


<img width="946" height="226" alt="image" src="https://github.com/user-attachments/assets/dd6d7b72-096f-4fc2-91ba-d37a17712034" /> 

verificamos url en navegador
<img width="894" height="598" alt="image" src="https://github.com/user-attachments/assets/8850af5a-49a3-440a-a15f-ccdbeee6b1a6" />

utilizamos fuzzing con gobuster y encontramos un wordpress
<img width="1077" height="381" alt="image" src="https://github.com/user-attachments/assets/657220e8-e40d-4fcb-be3c-d6998372f782" />

<img width="1082" height="568" alt="image" src="https://github.com/user-attachments/assets/3a8f58ff-cc07-4f42-b636-1f9238b47135" /> 

Revisamos los links del sitio y nos encotnramos con un post el cual tiene fecha de publicacion y un usuario mario 
<img width="1003" height="585" alt="image" src="https://github.com/user-attachments/assets/10e2f774-b48f-4fa2-a61e-b5909ca38a6e" />

con el fin de enumerar usuarios y servicios  hacemos un wpscan , acá podemos observar tanto versiones y plugins instalados
hay accesos de XML-RPC, listados para subir archivos con confidence 100%n y nos encuentra al usuario mario
<img width="698" height="534" alt="image" src="https://github.com/user-attachments/assets/568e3edb-b2c8-4ebe-9453-16afae82e502" />
<img width="1009" height="537" alt="image" src="https://github.com/user-attachments/assets/3a86342a-0169-4da8-92b6-c28e75f04cdb" />
<img width="1346" height="564" alt="image" src="https://github.com/user-attachments/assets/9a33563a-2d23-4c74-aaf4-a562284d9063" />

Realizamos un ataque de fuerza bruta para encontrar las credenciales con wpscan usando el diccionario rockyou.txt 
<img width="813" height="542" alt="image" src="https://github.com/user-attachments/assets/2bb80c55-a902-4918-a36b-850e24ddc333" />


Como resultado nos entrega la contraseña
<img width="852" height="429" alt="image" src="https://github.com/user-attachments/assets/4960e076-d19f-49c4-9914-cd6e8c6d1eac" />


## 3. Explotación
ya podemos ingresar al sistema desde el panel de login con las credenciales rescatadas
<img width="481" height="508" alt="image" src="https://github.com/user-attachments/assets/96c19064-6d35-4e2a-9bd2-303ec550cdd2" />

<img width="1132" height="579" alt="image" src="https://github.com/user-attachments/assets/f1ce84f8-2a50-4275-86e2-2d617431757d" />



Revisamos el perfil mario que tiene rol Administrador , con lo cual podemos instalar el plugin FILE MANAGEMET y creamos un archivo shell.php el cual contendrá la reverse shell de pentestmonkey
<img width="1078" height="458" alt="image" src="https://github.com/user-attachments/assets/3d6a6331-dba8-4e03-a83b-c2c5cda81a86" />

Luego ingresamos a la url para cargar esta reverse shell
<img width="895" height="109" alt="image" src="https://github.com/user-attachments/assets/a60a92b4-428f-4be6-9cd0-4569e38dfe45" />
al mismo tiempo nos ponemos en escucha por netcat/br
<img width="985" height="347" alt="image" src="https://github.com/user-attachments/assets/330e76e1-6ee6-4144-be00-f7f9c74abdd3" />

## 4. Escalada de privilegios

para el binario /env podemos escalar privilegios con /bin/sh -p

<img width="831" height="351" alt="image" src="https://github.com/user-attachments/assets/382184d3-fa8c-4441-b205-59abbfa9a21f" />

<img width="552" height="338" alt="image" src="https://github.com/user-attachments/assets/2dfa4e47-1177-4326-b6c3-75d955257a22" />


## 5. Aprendizajes

# Máquina: Chocolatefire - Dockerlabs
Dificultad: Medium  
Sistema: Linux 

<img width="1356" height="517" alt="image" src="https://github.com/user-attachments/assets/53631ad1-26bd-463f-94a8-75e87693e494" /> 


## 1. Reconocimiento

Enumeramos puertos con nmap y encontramos el puerto 9090, investigando obtenemos algo sobre el servicio Openfire
<img width="642" height="123" alt="image" src="https://github.com/user-attachments/assets/d66fcab5-485a-4fb8-a0aa-91df8f9c4a91" /><br>
<img width="603" height="206" alt="image" src="https://github.com/user-attachments/assets/fbb28856-1031-434d-9ff1-b2d12b89fe1e" /><br>

<img width="886" height="522" alt="image" src="https://github.com/user-attachments/assets/d23c0be1-867d-44a8-91a0-f35ab8120658" /><br>

<img width="973" height="512" alt="image" src="https://github.com/user-attachments/assets/de12ba9c-e8c3-44f1-a380-76f804aa8f68" /><br>
<img width="997" height="546" alt="image" src="https://github.com/user-attachments/assets/5c34a87c-1a49-40b6-b605-d9716045891f" /><br>
<img width="1033" height="308" alt="image" src="https://github.com/user-attachments/assets/7a58d183-c3b7-4e30-a616-3ff31cf8b602" /><br>

Probamos entrando en 172.17.0.2:9090 en el navegador para ver que nos arroja y encontramos un panel de login de openfire, bajo el botón de Login aparece
la versión del servicio Openfire , en este caso nos encontramos la version 4.7.4 , actualemnte se encuentra en la version 5.0.3 (diciembre 2025)
por lo cual lógicamente podemos investigar sobre algún exploit para la versión anterior <br>

<img width="950" height="615" alt="image" src="https://github.com/user-attachments/assets/bdc2ad9e-b892-4f53-a693-b1e68c267995" /><br>

<img width="679" height="163" alt="image" src="https://github.com/user-attachments/assets/3f55f5ed-2742-499e-9a40-f7c033ab30d1" /><br>


Podemos comenzar a buscar información sobre github Openfire 4.7.4 exploit encontrandonos un repositorio con un exploit el cual nos 
trae instrucciones para correr dicho exploit el cual usaremos en esta oportunidad<br>

<img width="919" height="502" alt="image" src="https://github.com/user-attachments/assets/4a7dd28e-b975-4685-be58-7cb34289a87f" />

Clonando repositorio<br>
<img width="708" height="210" alt="image" src="https://github.com/user-attachments/assets/ea7f2164-d41c-4580-9e40-b57dcbfee574" /><br>

Instalación de pyton3-venv <br>
<img width="869" height="496" alt="image" src="https://github.com/user-attachments/assets/cd8cb416-4c26-471b-8180-67745de0a419" /><br>

Creamos nuestro archivo de venv para luego hacer el pip3 install -r requirements.txt <br>
<img width="1341" height="437" alt="image" src="https://github.com/user-attachments/assets/7e1c1e99-3f25-41df-8c89-541516650de4" /><br>

ok Hora de correr el exploit a la ip con su respectivo puerto.<br>
<img width="1328" height="384" alt="image" src="https://github.com/user-attachments/assets/dcce08f2-229d-4223-90bb-7e08a214e5a4" /><br>


Acá copiamos el user y contraserña proporcionados por el exploit<br>

<img width="909" height="577" alt="image" src="https://github.com/user-attachments/assets/b0a0f36c-a7c2-453f-81df-db8f2376417b" /><br>

Nos vamos a la pestaña de Users/Groups<br>

<img width="1357" height="415" alt="image" src="https://github.com/user-attachments/assets/68a2a5dc-87c1-460f-afc9-4cfaf943af45" /><br>

ya con el user en cuestión aplicamos un ataque de fuerza bruta en este caso hydra con sus respectivos parametros de usuario sobre la ip del puerto 22 , usaremos el rockyou.txt como diccionario <br>

<img width="1342" height="274" alt="image" src="https://github.com/user-attachments/assets/b744c528-c88a-48c8-9a3c-a44bf5ad78fb" /><br>

una vez obtenidas las credenciales nos conectamos por ssh y accedemos !<br>

<img width="1040" height="340" alt="image" src="https://github.com/user-attachments/assets/f4d541cc-d331-4de8-8c97-084261a78003" /><br>






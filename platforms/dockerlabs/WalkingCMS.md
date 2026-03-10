<img width="1346" height="564" alt="image" src="https://github.com/user-attachments/assets/cfd14af2-ef09-4c04-a382-3b0fd3524465" /># Machine: Name Machine - Platfrom
Dificultad: Easy  
Sistema: Windows  
<img width="1356" height="517" alt="image" src="https://github.com/user-attachments/assets/c92b6528-de48-4118-92ff-be682b5739d1" />

## 1. Reconocimiento
Habilitamos la maquina y nos entrega su io -> 172.17.0.2/br
<img width="587" height="138" alt="image" src="https://github.com/user-attachments/assets/9ba82191-6215-41fc-9644-2c5785a3f189" />

## 2. Enumeración

Escaneo de nmap puertos y servicios
<img width="855" height="396" alt="image" src="https://github.com/user-attachments/assets/d6d65a01-2661-4892-b0eb-08e03cc3d258" />/br
<img width="835" height="363" alt="image" src="https://github.com/user-attachments/assets/dc8795e2-5d03-4d3b-aefb-3da024b20f0b" /> /br


<img width="946" height="226" alt="image" src="https://github.com/user-attachments/assets/dd6d7b72-096f-4fc2-91ba-d37a17712034" /> /br

verificamos url en navegador
<img width="894" height="598" alt="image" src="https://github.com/user-attachments/assets/8850af5a-49a3-440a-a15f-ccdbeee6b1a6" />/br

utulizamos fuzzing con gobuster   encontramos un wordpressu /br
<img width="1077" height="381" alt="image" src="https://github.com/user-attachments/assets/657220e8-e40d-4fcb-be3c-d6998372f782" />/br

<img width="1082" height="568" alt="image" src="https://github.com/user-attachments/assets/3a8f58ff-cc07-4f42-b636-1f9238b47135" /> /br

Revisamos los links del sitio y nos encotnramos con un post el cual tiene fecha de publicacion y un usuario mario /br
<img width="1003" height="585" alt="image" src="https://github.com/user-attachments/assets/10e2f774-b48f-4fa2-a61e-b5909ca38a6e" />/br

con el fin de enumerar usuarios y servicios  hacemos un wpscan , acá podemos observar tanto versiones y plugins isntalados /br
hay accesos de XML-RPC, listados para subir archivos con confidence 100% 
y nos encuentra al usuario mario /br
<img width="698" height="534" alt="image" src="https://github.com/user-attachments/assets/568e3edb-b2c8-4ebe-9453-16afae82e502" />/br
<img width="1009" height="537" alt="image" src="https://github.com/user-attachments/assets/3a86342a-0169-4da8-92b6-c28e75f04cdb" />/br
<img width="1346" height="564" alt="image" src="https://github.com/user-attachments/assets/9a33563a-2d23-4c74-aaf4-a562284d9063" />/br









## 3. Explotación

## 4. Escalada de privilegios

## 5. Aprendizajes

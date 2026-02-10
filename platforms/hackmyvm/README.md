# Machine: DC01 - HackMyVM
Dificultad: Medium  
Sistema: Windows 

## 1. Reconocimiento
Partimos con  sudo arp-scan -I eth0 --localnet  y verificamos que nuestra maquina con la MAC que comienza con 08:00 corresponde a una máquina virtual
con IP 192.168.100.21  ( 08:00:27:d5:56:19 )

<img width="649" height="200" alt="image" src="https://github.com/user-attachments/assets/213a69ab-ffb2-4954-b167-ac432a1030f9" />


## 2. Enumeración
Comenzamos con el escaneo de puertos para nuestra ip victima y lo guardamos en un archivo para tener los datos 
sudo nmap -p- -sS -sC -sV --min-rate 5000 -n -vvv -Pn 192.168.100.21 -oN DC01_escaneo

<img width="838" height="540" alt="image" src="https://github.com/user-attachments/assets/3ef85c47-904b-409c-91b7-354074087952" />

<img width="929" height="397" alt="image" src="https://github.com/user-attachments/assets/b14669f5-7111-4719-afb2-87a95f4f2cc8" />


## 3. Explotación

## 4. Escalada de privilegios

## 5. Aprendizajes


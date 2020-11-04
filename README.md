# AREP_DisponibilidadYDesempeno_Lab08

Usted ha sido contratado para capacitar un grupo de ingenieros en la implementación de soluciones elásticas y de alto desempeño. Para esto usted debe construir un tutorial que les permita construir y demostrar las capacidades de autoescalamiento de Amazon Web Services.

Construya un taller que le permita a los ingenieros crear una solución autoescalable en EC2 y en la que puedan demostrar que el sistema efectivamente escala bajo condiciones determinadas de carga.

Lectura sugerida:
https://docs.aws.amazon.com/es_es/autoscaling/ec2/userguide/GettingStartedTutorial.html

## My Steps
* Creamos nuestra pantilla de lanzamiento
![step](/img/1.PNG)
* Configuracion de la plantilla
![step](/img/2.PNG)

(Vamos a utilizar este script para que cuedo se cree una maquina nueva, tenga el servicio corriendo)
```
#!/bin/bash
sudo yum update -y
sudo yum install git -y
git clone https://github.com/luisalejandrojaramillo/AREP_DisponibilidadYDesempeno_Lab08
cd AREP_DisponibilidadYDesempeno_Lab08/FibonacciApp
sudo curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash 
. ~/.nvm/nvm.sh
nvm install node
npm install 
npm install forever -g
forever start FibonacciApp.js
```
* Creamos nuestro grupo de AutoEscalamiento con la plantilla creada anteriormente
![step](/img/3.PNG)
* Configuracion realizada
![step](/img/4.PNG)



* Revisamos que solo tenemos una instancia EC2 
![step](/img/10.PNG)
* Hacemos una peticion que no requiere mucho procesamiento
![step](/img/9.PNG)
* Hacemos una peticion que requiere bastante procesamieto
![step](/img/12.PNG)
* Notamos que el portentaje de CUP es bastante alto
![step](/img/11.PNG)
* Comprobamos que luego de utilizar bastante CPU, se crea una nueva instancia 
![step](/img/13.PNG)
![step](/img/14.PNG)
![step](/img/15.PNG)

## Steps
1. Idee un problema interesante que necesite una solución distribida y que necesite alto consumo de procesamiento, por ejemplo, ordenamiento de cadenas, indexación de grandes cantidades de texto, etc.. Genere los requerimientos mínimos.
2. Construya un prototipo de la solución.
3. Depliegue la solución en AWS en EC2.
4. Configure la máquina para que inicie los servicios una vez se reinicia el servidor.
5. Cree un AMI a partir de esta máquina.
6. Despliegue la solución en un grupo de autoescalamiento.
7. Cargue la solución con muchas solicitudes para generar alta carga en el servidor.
8. Monitoree y verifique que se creen más instancias.
9. Documente el tutorial en GitHub con código, texto, e imágenes.

## License
[MIT License ](/LICENSE)

## Autor
Luis Alejandro Jaramillo Rincon

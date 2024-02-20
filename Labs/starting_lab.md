LINODE LAB
PREPARACIÓN:
1.	Primero debes crear una cuenta dentro de Linode [AQUÍ](https://login.linode.com/signup) y seguir los pasos para activarla esto requiere los datos de un método de pago.
2.	Si al momento de terminar de crear tu cuenta no iniciaste sesión, hazlo [AQUÍ](https://login.linode.com/login) 
3.	Abre tu Visual Studio Code y crea una carpeta llamada LINODE.

![](https://github.com/jorgepas12/terralabs/blob/a34e3df0b6206211d0170b10c2ddb0c35c2a27d9/img/Imagen1.png)

4.	Ya creada la carpeta crea un archivo dentro de ella llamado providers.tf

![](https://github.com/jorgepas12/terralabs/blob/2b88422428e27743d6f45f15d41b1c915a41d485/img/2.png)

5.	Dentro del archivo providers.tf escribe la configuracion de la siguiente imagen para declarar el proveedor Linode.

![](https://github.com/jorgepas12/terralabs/blob/2b88422428e27743d6f45f15d41b1c915a41d485/img/3.png)


6.	Ahora para esta prueba necesitaremos un token para autenticar las creaciones de infraestructura mediante Terraform.
7.	Debes ir a Linode si no tienes abierta la página da clic [AQUÍ](https://login.linode.com/login) y autentícate.
8.	Una vez autenticado damos clic en la parte superior derecha en el icono de tu usuario autenticado y expandirá el menú y damos clic en API Tokens.  

![](https://github.com/jorgepas12/terralabs/blob/2b88422428e27743d6f45f15d41b1c915a41d485/img/4.png)

9.	En la nueva interfaz de autenticación verificas que estes en la sección de API Tokens y damos clic en Create A Personal Access Token como lo muestra la imagen.

![](https://github.com/jorgepas12/terralabs/blob/2b88422428e27743d6f45f15d41b1c915a41d485/img/5.png)

10.	En la ventana que aparece de lado derecho configuramos como muestra la imagen. En la ventana que aparece de lado derecho configuramos como muestra la imagen.

![](https://github.com/jorgepas12/terralabs/blob/2b88422428e27743d6f45f15d41b1c915a41d485/img/6.png)

11.	Dejamos todos los valores por defecto y hasta el final damos clic en el botón Create Token.
12.	Te aparecerá una ventana emergente como la siguiente imagen, copia el Personal Access Token y guárdalo momentáneamente en un bloc de notas.  

![](https://github.com/jorgepas12/terralabs/blob/2b88422428e27743d6f45f15d41b1c915a41d485/img/7.png)

NOTA: Este token lo usaremos durante la practica una vez terminada es recomendable eliminar el token por seguridad.
13.	Ahora vamos a configurar el token para que nos permita las creaciones de la infraestructura en terraform, cambiamos las siguientes líneas de código del archivo de proveedores. 

![](https://github.com/jorgepas12/terralabs/blob/2b88422428e27743d6f45f15d41b1c915a41d485/img/8.png)

14.	Recuerda sustituir el valor por tu propio token.
15.	Ahora abre la terminal de tu editor y escribe el siguiente comando recuerda estar dentro de la carpeta correspondiente: terraform init 
16.	Debe de inicializarse correctamente el proveedor.
17.	Ahora realicemos una pequeña prueba creando un Linode Object Storage para validar el token funcione bien.
18.	Crea un archivo en dentro de la carpeta LINODE llamado storage.tf 

![](https://github.com/jorgepas12/terralabs/blob/2b88422428e27743d6f45f15d41b1c915a41d485/img/9.png)

19.	Dentro del archivo storage.tf escribimos el siguiente código. 

![](https://github.com/jorgepas12/terralabs/blob/2b88422428e27743d6f45f15d41b1c915a41d485/img/10.png)

20.	Escribimos el siguiente comando en la terminal: terraform plan  

![](https://github.com/jorgepas12/terralabs/blob/2b88422428e27743d6f45f15d41b1c915a41d485/img/11.png)

21.	Podemos verificar que el plan de terraform salió perfecto.
22.	Realicemos una prueba más cargando un documento al bucket. Dentro del mismo archivo storage.tf escribimos el siguiente código.  

![](https://github.com/jorgepas12/terralabs/blob/2b88422428e27743d6f45f15d41b1c915a41d485/img/12.png)

23.	Debemos inicializar el proveedor “local_file” ya que es la primera vez que lo incorporamos, escribe el siguiente comando: terraform init
24.	Escribimos el siguiente comando para validar la configuracion: terraform plan
25.	El resultado del plan debe de ser 4 recursos a crear.  

![](https://github.com/jorgepas12/terralabs/blob/2b88422428e27743d6f45f15d41b1c915a41d485/img/13.png)

26.	Ahora escribe el comando: terraform apply --auto-approve
27.	Implementación exitosa. 

![](https://github.com/jorgepas12/terralabs/blob/2b88422428e27743d6f45f15d41b1c915a41d485/img/13.png)

28.	Vamos a la página de LINODE si cerraste sesión ábrela [AQUÍ](https://login.linode.com/login) 
29.	Dentro de la página vamos al menú lateral izquierdo y damos clic en Object Storage  

![](https://github.com/jorgepas12/terralabs/blob/2b88422428e27743d6f45f15d41b1c915a41d485/img/14.png)

30.	Una vez dentro de la sección de Object Storage da clic en la opción de Buckets deberás ver creado el bucket mediante Terraform. 

![](https://github.com/jorgepas12/terralabs/blob/2b88422428e27743d6f45f15d41b1c915a41d485/img/15.png)

31.	Da clic en el nombre del bucket para ir al interior y ver el objeto cargado mediante Terraform también. 

![](https://github.com/jorgepas12/terralabs/blob/2b88422428e27743d6f45f15d41b1c915a41d485/img/16.png)

HAS FINALIZADO LA PREPARACION DEL AMBIENTE.
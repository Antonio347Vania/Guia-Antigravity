# Guia-Antigravity
mio, por si se me olvida
I: Hii


<img width="718" height="493" alt="image" src="https://github.com/user-attachments/assets/d059a94c-5c43-4036-aaf7-ed513962030d" />
<img width="1207" height="431" alt="image" src="https://github.com/user-attachments/assets/7ef4abd4-3b8d-4ec0-a4dd-d1869ab6e6fe" />

## IAMoviles UII Act 8 consola de firebase Video
https://www.youtube.com/watch?v=nzLS4YCZh1k&authuser=0

Firebase + Flutter: Integración CRUD con Cloud Firestore

¿De qué trata?
Es una guía práctica para aprender a conectar Firebase con una aplicación Flutter y realizar las cuatro operaciones básicas de una base de datos (Crear, Leer, Actualizar y Eliminar) en tiempo real usando Cloud Firestore.

1. Configuración de Firebase
El primer paso es entrar a la consola de Firebase y crear un nuevo proyecto. Dentro del proyecto se registra la aplicación Android usando el Application ID, que se encuentra en el archivo build.gradle del proyecto Flutter. Una vez registrada la app, Firebase genera un archivo llamado google-services.json que hay que descargar y colocar dentro de la carpeta android/app/. Además, se deben modificar dos archivos build.gradle (uno a nivel de proyecto y otro a nivel de app) para incluir las dependencias necesarias de Google Services.

2. Preparación del proyecto Flutter
Se parte de un proyecto limpio. El archivo main.dart se simplifica al máximo: se inicializa Firebase antes de correr la app con Firebase.initializeApp(), y se crea una estructura básica con MaterialApp apuntando a una pantalla principal. Esa pantalla se construye como un StatefulWidget porque su contenido cambia dinámicamente según los datos que llegan de la base de datos.

3. Cloud Firestore
Cloud Firestore es la base de datos de Firebase. Es de tipo NoSQL y trabaja con documentos organizados en colecciones. Para este ejemplo se crea una colección llamada "Employees" donde cada documento representa un empleado y tiene dos campos: nombre y email. A diferencia de una base de datos relacional con tablas y filas, aquí cada documento es flexible y puede tener campos distintos.

4. Plugins necesarios
En el archivo pubspec.yaml se agregan dos dependencias: firebase_core, que es necesaria para inicializar cualquier servicio de Firebase, y cloud_firestore, que permite hacer todas las operaciones de lectura y escritura sobre la base de datos.

5. Las operaciones CRUD
Crear (Create): Se usa el método .add() sobre la referencia de la colección, pasando un mapa con los campos del nuevo documento. Esto genera automáticamente un ID único para ese documento.
Leer (Read): Se usa un StreamBuilder conectado al stream de la colección. Este widget es especial porque "escucha" la base de datos en tiempo real y cada vez que hay un cambio, reconstruye automáticamente la interfaz sin necesidad de recargar la página. Dentro del StreamBuilder se usa un ListView para mostrar la lista de empleados.
Actualizar (Update): Se usa el método .update() sobre la referencia de un documento específico, identificado por su ID. Se pasa un mapa con los campos que se quieren modificar.
Eliminar (Delete): Se usa el método .delete() sobre la referencia del documento a eliminar, también identificado por su ID.

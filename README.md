###Proceso <br>
Una  vez que nosotros hayamos instalado los recursos necesarios, abrimos la carpeta creada por ionic en visual studio code.

Se importó el componente Component y el servicio PhotoService desde Angular. Se configuró el componente Tab2Page como un componente Angular, definiendo su selector y otras configuraciones. Luego, se definió el constructor de la clase Tab2Page. Posteriormente, se agregó un constructor público que recibe una instancia del servicio PhotoService. Se implementó un método addPhotoToGallery() en la clase Tab2Page, el cual llama al método addNewToGallery() del servicio PhotoService cuando se ejecuta. Este método se encargará de agregar una nueva foto a la galería.
![imagen](https://github.com/Jhordy11/prueba-ionic-camera/assets/139184732/32034861-a8ed-436d-b955-a542c02cc05e)

Se creó un botón de pestaña (<ion-tab-button>) que está asociado a la pestaña con identificador "tab2" y que tiene como destino la ruta "/tabs/tab2". Dentro del botón de la pestaña, se colocó un icono (<ion-icon>) con el nombre "camera", que representa una cámara. También se incluyó una etiqueta (<ion-label>) con el texto "Photos" para mostrar debajo del icono. Este botón de pestaña se utilizará para navegar a la pestaña "Photos" dentro de la aplicación.

![imagen](https://github.com/Jhordy11/prueba-ionic-camera/assets/139184732/489c48f9-ec2f-4b8f-8a7b-9e66ef227340)

Primero, importé el módulo principal de la aplicación con import { AppModule } from './app/app.module';. Luego, añadí defineCustomElements(window); para registrar los componentes personalizados de Ionic en el objeto window, asegurándome de que estén disponibles para su uso en la aplicación.

![imagen](https://github.com/Jhordy11/prueba-ionic-camera/assets/139184732/145dabea-f1aa-45d9-9125-20edb740f70a)

![imagen](https://github.com/Jhordy11/prueba-ionic-camera/assets/139184732/c5b002f2-b69e-49b4-86c1-727c1ea0614a)


Despues, se importó el componente `Component` de Angular y el plugin `SplashScreen` de Capacitor con `import { Component } from '@angular/core';` y `import { SplashScreen } from '@capacitor/splash-screen';`. Luego, se definio el componente `AppComponent` usando el decorador `@Component`, especificando el selector, el archivo de plantilla HTML y el archivo de estilos. Finalmente, en la clase `AppComponent`, se creó un constructor vacío que actualmente no realiza ninguna acción, pero está preparado para inicializar cualquier lógica necesaria en el futuro.

![imagen](https://github.com/Jhordy11/prueba-ionic-camera/assets/139184732/d49b04e5-709c-40a9-8702-94dae3140d84)

A continuación, se añadió un método addNewToGallery que toma una nueva foto usando la cámara, guarda la foto en el sistema de archivos, agrega la foto al array photos, y guarda la colección de fotos en las preferencias. El equipo desarrolló el método savePicture, que guarda la foto en el almacenamiento de archivos convirtiéndola a formato base64, generando un nombre de archivo único, escribiéndola en el directorio de datos, y devolviendo un objeto de foto guardada.

El método readAsBase64 se diseñó para convertir la foto a formato base64 obteniendo la foto como un blob y utilizando convertBlobToBase64, que convierte el blob a base64 usando FileReader. Finalmente, se añadió un método loadSaved que carga la colección de fotos desde las preferencias, lee los datos de imagen para cada foto y actualiza el array photos con las rutas web de las imágenes. También se definió la interfaz UserPhoto con filepath y un opcional webviewPath.

Estas adiciones permiten que el equipo gestione la toma, guardado, conversión, y carga de fotos en la galería de la aplicación, manteniendo la persistencia de las fotos a través de las preferencias y el sistema de archivos.

![imagen](https://github.com/Jhordy11/prueba-ionic-camera/assets/139184732/e9d91335-291d-4201-a81b-4526ca236337)

![imagen](https://github.com/Jhordy11/prueba-ionic-camera/assets/139184732/3c89c09f-8032-4b0d-ae91-ac09cbe98dbf)

![imagen](https://github.com/Jhordy11/prueba-ionic-camera/assets/139184732/39d044ca-20c1-4b8c-8731-8ba4de6502ec)

![imagen](https://github.com/Jhordy11/prueba-ionic-camera/assets/139184732/001b0f45-a9ed-4771-850e-951b16035a8e)

![imagen](https://github.com/Jhordy11/prueba-ionic-camera/assets/139184732/f38997d4-4d35-4821-ab94-747379ea9a52)

añadió el método ngOnInit con la palabra clave async, indicando que la función es asíncrona. Dentro de este método, se llama al método loadSaved del servicio photoService utilizando await para asegurar que la carga de las fotos guardadas se complete antes de continuar con cualquier otra operación. Esto se hace dentro del ciclo de vida del componente para cargar automáticamente las fotos guardadas cuando el componente se inicializa.

![imagen](https://github.com/Jhordy11/prueba-ionic-camera/assets/139184732/3503b419-f844-4bde-ad21-5e773dbcc6a6)

Se importó PhotoService y UserPhoto desde ../services/photo.service, y ActionSheetController desde @ionic/angular. Luego, se definió el constructor del componente para recibir instancias de PhotoService y ActionSheetController, permitiendo su uso en el componente.

El equipo añadió el método showActionSheet, que se utiliza para mostrar una hoja de acción (action sheet) cuando se interactúa con una foto. Este método es asíncrono, por lo que se usa await para esperar la creación de la hoja de acción con actionSheetController.create. En la configuración de la hoja de acción, se definieron dos botones: uno para eliminar la foto (Delete), que llama al método deletePicture de photoService pasando la foto y su posición; y otro para cancelar (Cancel), que cierra la hoja de acción sin realizar ninguna acción adicional. Finalmente, se presenta la hoja de acción con actionSheet.present().





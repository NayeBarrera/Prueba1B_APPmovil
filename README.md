### Video <br>
https://drive.google.com/file/d/1I1R-uIepBtzQW3s5_zZjuD5KKds8o-Em/view?usp=drivesdk <br>
https://github.com/Jhordy11/prueba-ionic-camera/assets/111138912/bf763d91-f41a-452b-b065-1d92e370efbb
### Integrantes <br>
-[Aguas Jhordy](https://github.com/Jhordy11) <br>
-[Barrera Nayeli](https://github.com/NayeBarrera)<br>
-[Lascano Aldahir](https://github.com/LascanoAldahir) 


### Guardar Imágenes <br>
Una  vez que nosotros hayamos instalado los recursos necesarios, abrimos la carpeta creada por ionic en visual studio code.
Se importó el componente Component y el servicio PhotoService desde Angular. Se configuró el componente Tab2Page como un componente Angular, definiendo su selector y otras configuraciones. Luego, se definió el constructor de la clase Tab2Page. Posteriormente, se agregó un constructor público que recibe una instancia del servicio PhotoService. Se implementó un método addPhotoToGallery() en la clase Tab2Page, el cual llama al método addNewToGallery() del servicio PhotoService cuando se ejecuta. Este método se encargará de agregar una nueva foto a la galería. <br>
![imagen](https://github.com/Jhordy11/prueba-ionic-camera/assets/139184732/32034861-a8ed-436d-b955-a542c02cc05e) <br>

Se creó un botón de pestaña (<ion-tab-button>) que está asociado a la pestaña con identificador "tab2" y que tiene como destino la ruta "/tabs/tab2". Dentro del botón de la pestaña, se colocó un icono (<ion-icon>) con el nombre "camera", que representa una cámara. También se incluyó una etiqueta (<ion-label>) con el texto "Photos" para mostrar debajo del icono. Este botón de pestaña se utilizará para navegar a la pestaña "Photos" dentro de la aplicación. <br>

![imagen](https://github.com/Jhordy11/prueba-ionic-camera/assets/139184732/489c48f9-ec2f-4b8f-8a7b-9e66ef227340) <br>

Primero, importé el módulo principal de la aplicación con import { AppModule } from './app/app.module';. Luego, añadí defineCustomElements(window); para registrar los componentes personalizados de Ionic en el objeto window, asegurándome de que estén disponibles para su uso en la aplicación. <br>

![imagen](https://github.com/Jhordy11/prueba-ionic-camera/assets/139184732/145dabea-f1aa-45d9-9125-20edb740f70a) <br>

![imagen](https://github.com/Jhordy11/prueba-ionic-camera/assets/139184732/c5b002f2-b69e-49b4-86c1-727c1ea0614a) <br>


Despues, se importó el componente `Component` de Angular y el plugin `SplashScreen` de Capacitor con `import { Component } from '@angular/core';` y `import { SplashScreen } from '@capacitor/splash-screen';`. Luego, se definio el componente `AppComponent` usando el decorador `@Component`, especificando el selector, el archivo de plantilla HTML y el archivo de estilos. Finalmente, en la clase `AppComponent`, se creó un constructor vacío que actualmente no realiza ninguna acción, pero está preparado para inicializar cualquier lógica necesaria en el futuro. <br>

![imagen](https://github.com/Jhordy11/prueba-ionic-camera/assets/139184732/d49b04e5-709c-40a9-8702-94dae3140d84) <br>

A continuación, se añadió un método addNewToGallery que toma una nueva foto usando la cámara, guarda la foto en el sistema de archivos, agrega la foto al array photos, y guarda la colección de fotos en las preferencias. El equipo desarrolló el método savePicture, que guarda la foto en el almacenamiento de archivos convirtiéndola a formato base64, generando un nombre de archivo único, escribiéndola en el directorio de datos, y devolviendo un objeto de foto guardada. <br>

El método readAsBase64 se diseñó para convertir la foto a formato base64 obteniendo la foto como un blob y utilizando convertBlobToBase64, que convierte el blob a base64 usando FileReader. Finalmente, se añadió un método loadSaved que carga la colección de fotos desde las preferencias, lee los datos de imagen para cada foto y actualiza el array photos con las rutas web de las imágenes. También se definió la interfaz UserPhoto con filepath y un opcional webviewPath. <br>

Estas adiciones permiten que el equipo gestione la toma, guardado, conversión, y carga de fotos en la galería de la aplicación, manteniendo la persistencia de las fotos a través de las preferencias y el sistema de archivos. <br>

![imagen](https://github.com/Jhordy11/prueba-ionic-camera/assets/139184732/e9d91335-291d-4201-a81b-4526ca236337) <br>

![imagen](https://github.com/Jhordy11/prueba-ionic-camera/assets/139184732/3c89c09f-8032-4b0d-ae91-ac09cbe98dbf) <br>

![imagen](https://github.com/Jhordy11/prueba-ionic-camera/assets/139184732/39d044ca-20c1-4b8c-8731-8ba4de6502ec) <br>

![imagen](https://github.com/Jhordy11/prueba-ionic-camera/assets/139184732/001b0f45-a9ed-4771-850e-951b16035a8e) <br>

![imagen](https://github.com/Jhordy11/prueba-ionic-camera/assets/139184732/f38997d4-4d35-4821-ab94-747379ea9a52) <br>

añadió el método ngOnInit con la palabra clave async, indicando que la función es asíncrona. Dentro de este método, se llama al método loadSaved del servicio photoService utilizando await para asegurar que la carga de las fotos guardadas se complete antes de continuar con cualquier otra operación. Esto se hace dentro del ciclo de vida del componente para cargar automáticamente las fotos guardadas cuando el componente se inicializa. <br>

![imagen](https://github.com/Jhordy11/prueba-ionic-camera/assets/139184732/3503b419-f844-4bde-ad21-5e773dbcc6a6) <br>

Se importó PhotoService y UserPhoto desde ../services/photo.service, y ActionSheetController desde @ionic/angular. Luego, se definió el constructor del componente para recibir instancias de PhotoService y ActionSheetController, permitiendo su uso en el componente. <br>

El equipo añadió el método showActionSheet, que se utiliza para mostrar una hoja de acción (action sheet) cuando se interactúa con una foto. Este método es asíncrono, por lo que se usa await para esperar la creación de la hoja de acción con actionSheetController.create. En la configuración de la hoja de acción, se definieron dos botones: uno para eliminar la foto (Delete), que llama al método deletePicture de photoService pasando la foto y su posición; y otro para cancelar (Cancel), que cierra la hoja de acción sin realizar ninguna acción adicional. Finalmente, se presenta la hoja de acción con actionSheet.present(). <br>
![imagen](https://github.com/Jhordy11/prueba-ionic-camera/assets/139184732/9840d48e-cc15-48bb-b9dd-b0589dd11a6b) <br>

### Eliminar fotos - Deleting Photos
Para implementar la función de eliminación de fotos en nuestra aplicación, primero asegurémonos de que Live Reload esté ejecutándose y la aplicación esté abierta en el dispositivo. 
* En tab2.page.html, añadir un controlador de clics a cada <ion-img>.
* Configurar el controlador para mostrar un cuadro de diálogo Hoja de acción con opciones para eliminar la foto o cancelar.
* Se implementa la función deletePicture() en photo.service.ts, que actualiza el array de fotos y elimina el archivo del sistema.<br>
![image](https://github.com/Jhordy11/prueba-ionic-camera/assets/170026913/0a10d5a7-de9f-4083-85cb-5ac08cc069cb)

### Splash Screen <br>
1. Usamos los siguientes comandos para instalar las librerías necesarias para el splash screen
```
npm install @capacitor/splash-screen
npx cap sync
```
2. Agregamos lo siguiente en capacitor.config.ts
```
plugins: {
    SplashScreen: {
      launchShowDuration: 3000,
      launchAutoHide: true,
      androidSplashResourceName: "splash", 
      showSpinner:false,
      splashFullScreen:true,
      splashImmersive:true
    },
  }
```
3. Creamos una carpeta y dentro de esta agregamos el icon.png y splash.png
```
--resources
   -icon.png
   -splash.png
```
4. Usamos los siguientes comando para crear los recursos para android
```
npm install -g  cordova-res
cordova-res android --skiip-config --copy
```
### Deploy <br>
1. Usamos los comandos
```
npm run build
npx cap add android
ionic cap sync android
```
2. Generamos el APK.
![image](https://github.com/Jhordy11/prueba-ionic-camera/assets/111138912/d53e82d4-1ac1-4183-aa64-627209172036)<br>
![image](https://github.com/Jhordy11/prueba-ionic-camera/assets/111138912/e85d24ba-3209-47e4-87e8-298a062ab43e)<br>
![image](https://github.com/Jhordy11/prueba-ionic-camera/assets/111138912/cb2ec87e-ac75-4069-a9fc-815d7005998d)

### Conclusiones <br>


* La inclusión de características como la pantalla de presentación (splash screen) con la foto de los integrantes agrega un toque personal y mejora la experiencia general del usuario al proporcionar una conexión emocional.
* La capacidad de capturar, guardar, cargar y borrar fotos ofrece a los usuarios un conjunto completo de herramientas para gestionar su contenido visual
* La función deletePicture() en photo.service.ts está diseñada de manera modular, facilitando su reutilización y mantenimiento futuros.
* Después de capturar una foto, permite a los usuarios guardarla en el dispositivo. Esto implica guardar la imagen en el almacenamiento interno o externo del dispositivo, dependiendo de las necesidades.
* La estructura y el enfoque adoptados permiten una fácil expansión de la funcionalidad, como añadir más opciones en la hoja de acción o integrar nuevas características en la galería de fotos.
* Se destaca la importancia de una buena organización, la utilización de herramientas y prácticas de desarrollo modernas, y la atención a la experiencia del usuario en el desarrollo de aplicaciones móviles.


#### HOW TO RUN <br> 
<br> Clonar el repositorio
<br> Ejecutar: npm i 
<br> Ejecturar npx cap open android
<br> Generar el apk.

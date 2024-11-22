# Aplicación Móvil de Realidad Virtual

![Vista previa del proyecto](https://github.com/Yamilx/RealidadVirtual/blob/b3d46f95cd2ee02cee29f39b004b60b2998a2dc0/imagen.jpeg)

## Descripción
Este proyecto consiste en el desarrollo de una aplicación móvil que integra tecnologías de realidad virtual (VR) para ofrecer una experiencia inmersiva y emocionante. Utilizando gafas de realidad virtual en las que se coloca el teléfono móvil, los usuarios podrán adentrarse en un entorno virtual interactivo diseñado con **Unity**, una de las herramientas más avanzadas para el desarrollo de aplicaciones 3D y VR.

## Propósito del Proyecto
El objetivo principal es proporcionar una experiencia educativa interactiva, crear un simulador para entretenimiento y explorar mundos virtuales. Esto permitirá a los usuarios experimentar la tecnología de realidad virtual de manera accesible y sencilla, utilizando únicamente su smartphone y un visor compatible.

## Motivación
El proyecto forma parte de la materia de *Aplicaciones Móviles* y representa nuestro primer acercamiento al uso de **Unity** y al desarrollo de aplicaciones de realidad virtual. Nos motiva el desafío de aprender y aplicar nuevas tecnologías mientras exploramos las posibilidades creativas que ofrece la VR.

## Características Principales
- **Compatibilidad con Smartphones:** La aplicación está diseñada para funcionar con dispositivos Android/iOS y visores de realidad virtual móviles (como Google Cardboard).  
- **Entornos Interactivos:** Escenarios inmersivos con interacción limitada, diseñados para maximizar la experiencia del usuario.  
- **Fácil Acceso:** Un enfoque en la simplicidad para que cualquier usuario pueda disfrutar la experiencia sin necesidad de dispositivos avanzados.

## Tecnologías Utilizadas  
- **Motor de Desarrollo:** Unity  
- **Lenguaje de Programación:** C#  
- **Plataformas:** Android y iOS  
- **Visores Compatibles:** Gafas de VR móviles como Google Cardboard  

## Equipo de Trabajo
Somos un grupo de estudiantes de Ingeniería de Sistemas que se aventura por primera vez en el mundo del desarrollo VR, con entusiasmo y compromiso para superar los retos de aprender **Unity** y llevar a cabo un proyecto innovador.

El equipo de trabajo está conformado por:  
- **Yamil Leonel Mamani Guzman**  
- **Jepsent Hendrick Enriquez Condori**  
- **Jose Ariel Hoyos Mita**  
- **Samuel Poma Colque**  
- **Jose Ignacio Burgos Ayala**

## Requisitos

Para realizar y ejecutar este proyecto es necesario cumplir con los siguientes requisitos:

### **Sistema Operativo**
- Windows 10 o Windows 11

### **Herramientas de Desarrollo**
- **Unity 2021.* LTS:** Incluye soporte para desarrollo móvil.  
- **Complemento de Android para Unity:** Instalado desde el Unity Hub.  
- **GIT:** Control de versiones para la colaboración en equipo.  
  - Asegúrate de tener la ruta de `git.exe` agregada en la variable de entorno `PATH`.

### **Dispositivo Móvil**
- **Smartphone Android:** Compatible con la aplicación desarrollada.  
- Herramientas de desarrollador activadas:  
  - **Depuración por USB:** Activada.  
  - **Instalación por USB:** Activada.  

### **Hardware Complementario**
- **Cable USB:** Para conectar el teléfono al PC durante las pruebas.  
- **Visor de Realidad Virtual (Cardboard):** Para utilizar la aplicación en un entorno inmersivo.

### Paso 2: Instalación de Git

1. **Descarga:** Ve a [https://git-scm.com/](https://git-scm.com/) y descarga el instalador para Windows.  
2. **Instala:** Ejecuta el instalador y acepta las opciones predeterminadas. Asegúrate de seleccionar "Git from the command line and also from 3rd-party software" para agregarlo al PATH.  
3. **Verifica:** Abre una terminal (Command Prompt, PowerShell o Git Bash) y ejecuta:  
   ```bash
   git --version

### Paso 2: Preparación del Proyecto

1. **Crear un nuevo proyecto en Unity**:  
   - Abre Unity Hub y selecciona la opción para crear un nuevo proyecto.  
   - Elige la plantilla **3D Universal Render Pipeline (URP)**, que es ideal para gráficos optimizados en dispositivos móviles.  
   - Asigna un nombre significativo al proyecto, como:  
     ```RealidadVirtual```

   ![Preparacion del proyecto](Fotos%20y%20Videos/2.png)


2. **Configurar la carpeta de trabajo**:  
   - Elige una ubicación adecuada para guardar el proyecto, preferiblemente en un directorio con suficiente espacio y fácil acceso.

3. **Configuramos los Build Settings**:  
   - Una vez abierto el proyecto, ve a **File > Build Settings**:  
     - Selecciona la plataforma **Android** (o **iOS**, según corresponda).  
     - Haz clic en **Switch Platform** para cambiar la plataforma del proyecto.  


4. **Importar paquetes necesarios**:

      - Ve a **Window > Package Manager**.
      - Puedes visitar el siguiente link para más información: [Google Cardboard Unity Quickstart](https://developers.google.com/cardboard/develop/unity/quickstart?hl=es-419).
      - En "Add package from git URL" coloca lo siguiente:

               https://github.com/googlevr/cardboard-xr-plugin.git      

   ![extension descargada](Fotos%20y%20Videos/3.png)
   - Importamos los SAMPLES para tener escenas listas para usar.

5. **Configuramos el project Settings**:
![extension cardboard](Fotos%20y%20Videos/8.png)
      - Activamos el Cardboard XR plugin para que unity entienda que estamos usando cardboard y no otra plataforma.

6. **Agregamos la escena en Build Settings**: 
![agregamos la escena](Fotos%20y%20Videos/4.png)
      - Dandole clic en  Add Open Scenes agregaremos la escena actuak.

7. **Configuracion de project Settings Player**: 
![nombre del producto](Fotos%20y%20Videos/5.png)
      - Lo primero que debemos hacer es colocarle un nombre a nuestro producto.
      - Configuramos nuestros graphics APIs a OpenGLES3.

8. **Modificamos el archivo main Template**:
      - Localizamos la carpeta "main Template" que se encuentra en Assets/plugins/Android y agregamos las siguientes lineas de codigo.

               implementation 'androidx.appcompat:appcompat:1.6.1'
               implementation 'com.google.android.gms:play-services-vision:20.1.3'
               implementation 'com.google.android.material:material:1.12.0'
               implementation 'com.google.protobuf:protobuf-javalite:3.19.4'
   ![modificacion del codigo](Fotos%20y%20Videos/10.png)

9. **Modificamos el archivo gradle Template**:
      - Localizamos la carpeta "gradle Template" que se encuentra en Assets/plugins/Android y agregamos las siguientes lineas de codigo.

                 android.enableJetifier=true
                 android.useAndroidX=true
   ![modificacion del codigo](Fotos%20y%20Videos/9.png)

10. **Guardar y preparar para el desarrollo**:  
      - Asegúrate de guardar el proyecto con `Ctrl + S` y verifica que todo esté funcionando correctamente.

### Paso 3: Desplegamos la aplicación

A continuación, puedes ver el proceso de despliegue en el siguiente video:

[Ver video de despliegue en Google Drive](https://drive.google.com/file/d/1xpIMQfxQ5wRDkWh3KHiayfR8hK5K91R6/view?usp=drive_link)

### Paso 4: Desplegamos la aplicación con controles de movimiento

A continuación, puedes ver el proceso de despliegue con un mando para controlar el movimiento en el siguiente video:

[Ver video de despliegue](Fotos%20y%20Videos/VideoControl.mp4)

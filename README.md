<div align="center">


### Repositorio de reunión de la documentación de Platinum

<p>
Proyecto Intermodular del Grado Superior de Desarrollo de Aplicaciones Web
</p>

<br>

<!-- BADGES GENERALES -->
<img src="https://img.shields.io/badge/status-en%20desarrollo-yellow?style=for-the-badge" />
<img src="https://img.shields.io/badge/version-0.5-blue?style=for-the-badge" />
<img src="https://img.shields.io/badge/type-fullstack-important?style=for-the-badge" />
<img src="https://img.shields.io/badge/docs-included-success?style=for-the-badge" />

<br><br>

<!-- TECNOLOGÍAS -->
### 🛠️ Stack Tecnológico

<img src="https://img.shields.io/badge/springboot-59cc31?logo=spring&logoColor=ffffff&style=for-the-badge" />
<img src="https://img.shields.io/badge/maven-C71A36?logo=apachemaven&logoColor=ffffff&style=for-the-badge" />
<img src="https://img.shields.io/badge/angular-d7002f?logo=angular&logoColor=ffffff&style=for-the-badge" />
<img src="https://img.shields.io/badge/postgresql-2f6792?logo=postgresql&logoColor=ffffff&style=for-the-badge" />
<img src="https://img.shields.io/badge/nodejs-5FA04E?logo=nodedotjs&logoColor=ffffff&style=for-the-badge" />
<img src="https://img.shields.io/badge/npm-CB3837?logo=npm&logoColor=ffffff&style=for-the-badge" />
<img src="https://img.shields.io/badge/git-F05032?logo=git&logoColor=ffffff&style=for-the-badge" />

<br><br>

### Objetivo

El objetivo de este repositorio es recoger toda la documentación realizada para apoyar el desarrollo de la aplicación web Platinum. Concretamente la planificación, diseños y una demo del proyecto.

<br>

👤 **Autor:** Luis Daniel Pozo Benz

---

</div>

# Índice

- [Preparación del entorno](#preparación-del-entorno)
  - [Versiones de las tecnologías](#versiones-de-las-tecnologías)
  - [Dependencias NPM](#dependencias-npm)
  - [Dependencias Maven](#dependencias-maven)
  - [Base de Datos](#base-de-datos)
- [Ejecución](#ejecución)
- [Uso de la demo](#uso-de-la-demo)
  - [Usuarios Disponibles](#usuarios-disponibles)
  - [Crear Usuario](#crear-usuario)
- [Que hacer?](#que-hacer)

# 🏆 Introducción de uso de la demo
La siguiente sección sirve como guía para ejecutar la demo de Platinum. Es importante que se siga cada paso rigurosamente para asegurar el correcto funcionamiento de la aplicación.

Ante problemas, se recomienda revisar esta guía detallada, ya que incluye algunos de estos casos.

# 🛠️ Preparación del entorno

Para llevar a cabo la preparación del entorno es imperativo seguir los siguientes pasos:

## 🕒 Versiones de las tecnologías

Lista de las tecnologías de la demo, junto a sus versiones:

| Tecnologia | Versión |
| ---------- | ------- |
| Node.js    | 18      |
| npm        | 11.11.1 |
| Angular    | 21.0.0  |
| JDK        | 21      |
| SpringBoot | 4.0.1   |
| Maven      | 3.9.12  |
| PostgreSQL | 17      |

> [!IMPORTANT]
> Es fundamental asegurar que todas las versiones de las tecnologías estén correctamente instaladas para que la demo funcione sin problemas. No aseguramos el correcto funcionamiento de la demo si se utilizan versiones diferentes a las indicadas. Se recomienda seguir las instrucciones de instalación de cada tecnología para asegurar que se instalen correctamente.

### 📦 Dependencias NPM

En la siguiente ruta
`/demo/src/frontend`:

Instalar las dependencias de npm a través del siguiente comando

```powershell
npm install
```


### 📦 Dependencias Maven

En la siguiente ruta
`/demo/src/backend`:

Instalar las dependencias de maven con el siguiente comando

```powershell
mvn install
```

### 🗃️ Base de Datos

Para el correcto uso de la demo, es necesario restaurar la base de datos a través del archivo `platinum.sql` proporcionado en la raíz de la carpeta `/demo/src`.
El archivo contiene los datos sobre los juegos y usuarios suficientes para ejecutar la demo del proyecto.

Para restaurar la base de datos, se debe seguir los siguientes pasos:
1. Abrir pgAdmin en la versión 9.11 o superior (versiones anteriores no permiten usar esta característica con el archivo `platinum.sql`).
2. Crear una nueva base de datos con el nombre `platinum` de la siguiente manera:
    - Click derecho en `Databases` -> `Create` -> `Database`
    - Nombre: `platinum`
    - Click en `Save`
3. Restaurar la base de datos a partir del archivo `platinum.sql`. Para ello seguimos los siguientes pasos:
    - Click derecho en la base de datos `platinum` -> `Restore`
    - Formato: `Plain`
    - Seleccionar el archivo `platinum.sql`
    - Click en `Restore`

> [!IMPORTANT]
> Cuando sea necesario introducir un nombre de usuario y contraseña para la conexión con la base de datos, es importante que estas credenciales sean las siguientes, debido a que la configuración del proyecto está diseñada con ellas en mente:
> user: `postgres`
> password: `root`

### 🔑 Claves secretas
La conexión con la API de Steam es crucial para el funcionamiento de la demo, pero para conseguir esta conexión es necesario tener una clave secreta.
Para la correcta configuración de esta clave se deben seguir los siguientes pasos:

1. Crear el archivo **application-secrets.properties** en la ruta `/demo/src/backend/src/main/resources` con el siguiente contenido:

```properties
steam.api-key=KEY-DE-STEAM
steam.api-url=https://api.steampowered.com
steam.store-url=https://store.steampowered.com
```

> [!CAUTION]
> Esta clave no será proporcionada en este repositorio para la ejecución de la demo, debido a que es información secreta.
> 
> Para obtener una clave de API de Steam, es necesario crear una cuenta en la plataforma de Steam y registrarse como desarrollador en el sitio web de Steam. Una vez registrado, se puede generar una clave de API desde el panel de control del desarrollador. Es importante mantener esta clave en secreto, ya que se utiliza para acceder a la información de la API de Steam y podría ser utilizada por terceros para acceder a dicha información sin autorización, posiblemente poniendo en peligro su uso prolongado.

> [!NOTE]
> Si no se configura la clave de API de Steam, no será posible recopilar información nueva, pero la demo seguirá funcionando correctamente utilizando la información que ya se encuentra almacenada en la base de datos.

# 🚀 Ejecución

En cuanto ya se haya realizado la preparación anteriormente indicada, se puede proceder a la ejecución de la demo

> [!CAUTION]
> Previamente a cada ejecución, es necesario asegurarse de que la base de datos se encuentra en ejecución antes que el servidor de desarrollo. En caso contrario, se pueden producir errores que entorpezcan el funcionamiento de la demo.

 En la ruta
 `/demo/src/frontend`:

Ejecutar el siguiente comando:

```powershell
ng serve
```

Y simultáneamente, en la siguiente ruta

 `/demo/src/backend`:

Ejecutar el comando:

```powershell
mvn spring-boot:run
```

Con los servidores encendidos, la demo de la aplicación quedará expuesta en el URL `http://localhost:4200`.

## 📊 Usuarios disponibles

En la demo se han creado tres usuarios con cuentas vinculadas de Steam para facilitar su uso y permitir la visualización de las funciones de la aplicación. Estos usuarios son:

| Nombre de usuario | Contraseña    |
| ----------------- | ------------- |
| Luis              | Luis12345     |
| Cristian          | Cristian12345 |
| Erik              | Erik12345     |

## 📝 Crear Usuario

La creación básica de un usuario se puede realizar a través de la página de registro, sin embargo en un principio carecerá de datos de logros.
Para poder probar todas las funciones disponibles en la demo, es necesario vincular la cuenta de Platinum del usuario con una cuenta de Steam existente, desde el perfil del usuario (se accede a través del icono en la esquina superior derecha) y haciendo click en el botón de "Vincular con Steam". Esto redirigirá a la página oficial de inicio de sesión de Steam, y tras introducir las credenciales, se redirigirá de vuelta a Platinum con la cuenta vinculada.

> [!CAUTION]
> Tras volver a Platinum desde el incio de sesión de Steam es necesario refrescar la página para poder visualizar los datos de Steam de la cuenta recién vinculada

# 📚 Funcionalidades disponibles

## Sin estar loggeado
- Visualizar el listado de juegos.
- Buscar juegos.
- Buscar otros usuarios registrados.
- Ver la información de los juegos (logros y su porcenaje de compleción).
- Ver la información de los usuarios registrados(sus juegos propios y sus respectivos logros).

## Funciones añadidas con el login

- Acceder a tu perfil de usuario para ver la información de tus propios logros y juegos.
- Acceder a perfiles ajenos para ver su información de juegos y logros.

> [!TIP]
> Para obtener información adicional sobre detalles técnicos de la demo, se recomienda consultar el repositorio específico de la propia demo, dónde se encuentra toda la información detallada del código y desarrollo. Puedes acceder a: [Platinum](https://github.com/Kiro85/entregables-projecte-final-dawpi2526_platinum_src).

<div align="center">

---

### 🏆 PLATINUM

<p>
📘 Proyecto Intermodular DAW · Desarrollo de Aplicaciones Web  
</p>

---

</div>

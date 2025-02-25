# Dashboard Carrera Moto

Este repositorio contiene un dashboard interactivo para visualizar y dar seguimiento a los KPIs y objetivos estratégicos de Carrera Moto, basados en el propósito de cada área de negocio.

## Características

- Visualización de KPIs clave para todas las áreas de negocio (Motos Nuevas, Servicio, Café-Bar, Marketing y Eventos)
- Integración con Google Sheets para actualización automática de datos
- Gráficos interactivos que muestran tendencias mensuales
- Indicadores visuales de cumplimiento de objetivos
- Recomendaciones automáticas basadas en el desempeño actual
- Diseño responsivo para visualización en diferentes dispositivos

## Estructura de archivos

- `index.html` - El dashboard principal (contiene HTML, CSS y JavaScript)
- `README.md` - Este archivo de documentación

## Requisitos previos

- Cuenta de GitHub
- Cuenta de Google
- Hoja de cálculo de Google Sheets con la estructura de datos requerida
- Proyecto en Google Cloud con API de Google Sheets habilitada

## Configuración e instalación

### 1. Configurar Google Sheets

La hoja de cálculo debe tener las siguientes pestañas con sus respectivas columnas:

- **DatosVentas**: Mes, Demos, Solicitudes, Visitas
- **DatosServicio**: Mes, Servicios, Satisfaccion, Resenas
- **DatosCafe-Bar**: Mes, Visitas, Ticket, Resenas
- **DatosMarketing**: Mes, Crecimiento, Leads, Conversion
- **DatosEventos**: Mes, Musica, Comunidad, Paga
- **KPIs Generales**: (Opcional) Datos agregados de las áreas

### 2. Configurar Google Cloud y API Key

1. Ve a [Google Cloud Console](https://console.cloud.google.com/)
2. Crea un nuevo proyecto o selecciona uno existente
3. Habilita la API de Google Sheets
   - Ve a "APIs y servicios" > "Biblioteca"
   - Busca "Google Sheets API" y habilítala
4. Crea una clave de API
   - Ve a "APIs y servicios" > "Credenciales"
   - Haz clic en "Crear credenciales" > "Clave de API"
   - Restringe la clave para que solo se pueda usar con la API de Google Sheets y desde tu dominio
   - Copia la clave de API generada

### 3. Actualizar la configuración en el código

En el archivo `index.html`, actualiza las siguientes variables:

```javascript
// Configuración de Google Sheets API
const SHEET_ID = 'TU_ID_DE_HOJA_DE_CALCULO'; // ID de la hoja de cálculo
const API_KEY = 'TU_API_KEY'; // API key de Google Cloud
```

### 4. Desplegar en GitHub Pages

1. Crea un nuevo repositorio en GitHub
2. Sube el archivo index.html a tu repositorio
3. Activa GitHub Pages:
   - Ve a la página de tu repositorio en GitHub
   - Haz clic en "Settings" > "Pages"
   - En "Source", selecciona la rama "main" y carpeta "/" (raíz)
   - Haz clic en "Save"
   - Espera unos minutos y tu dashboard estará disponible en `https://[tu-usuario].github.io/[nombre-repositorio]/`

## Personalización

### Colores

El dashboard usa un esquema de colores basado en áreas:
- **Motos Nuevas**: Azul (#3b82f6)
- **Servicio**: Verde (#10b981)
- **Café-Bar**: Naranja (#f59e0b)
- **Marketing**: Morado (#8b5cf6)
- **Eventos**: Rosa (#ec4899)

Puedes modificar estos colores en la sección de estilos CSS al inicio del archivo.

### Objetivos

Los objetivos están configurados en las respectivas funciones de actualización para cada área:

```javascript
// Ejemplo: Objetivos para Motos
const demosTarget = 40;
const solicitudesTarget = 20;
const visitasTarget = 60;
```

Actualiza estos valores según cambien tus objetivos de negocio.

## Solución de problemas

### El dashboard no muestra datos
- Verifica que la API key de Google sea válida y tenga los permisos correctos
- Asegúrate de que la hoja de cálculo sea accesible públicamente o para la cuenta que usa la API
- Revisa la consola del navegador (F12) para ver si hay errores específicos

### Los gráficos no se muestran correctamente
- Verifica que los datos en Google Sheets tengan el formato correcto (números, no texto)
- Asegúrate de que los nombres de las columnas en Google Sheets coincidan con los esperados en el código

## Actualización de datos

El dashboard tiene un botón de "Actualizar Datos" que recarga la información desde Google Sheets. Para una actualización automática:

1. Configura tu hoja de Google Sheets para actualizar automáticamente con datos de tu negocio
2. Refresca el dashboard periódicamente o configura una actualización automática del navegador

## Contacto

Carrera Moto - [correo@carreramoto.com](mailto:correo@carreramoto.com)

---

Este dashboard está diseñado específicamente para Carrera Moto y sus áreas de negocio, basado en sus objetivos y propósito.

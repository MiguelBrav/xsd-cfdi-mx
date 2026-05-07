# xsd-cfdi-mx

Guía y scripts para generar clases C# a partir de los esquemas XSD oficiales del SAT para CFDI 4.0.

---

La creación de clases fuertemente tipadas en C# a partir de los esquemas oficiales del SAT garantiza que tu código cumpla con la estructura técnica y legal sin errores de mapeo manual. Este repositorio documenta ese proceso paso a paso.

---

## Requisitos

- Visual Studio 2022 o superior
- Esquemas oficiales del SAT (`.xsd`) descargados desde el portal oficial

---

## Generación de clases

### Paso 1 — Abrir la terminal correcta

No uses el CMD estándar de Windows. En Visual Studio, ve a **Herramientas > Línea de comandos** y selecciona **Símbolo del sistema para desarrolladores** o **PowerShell para desarrolladores**. Esto carga automáticamente las rutas del SDK de .NET.

![App Screenshot](https://res.cloudinary.com/imgresd/image/upload/v1778131385/Github/CFDI01_opd0nd.png)

### Paso 2 — Navegar al directorio del proyecto

Ubícate en la carpeta donde tienes los archivos `.xsd`, para este ejemplo sería:

```powershell
cd C:\Users\Migue\source\repos\xsd-cfdi-mx
```
![App Screenshot](https://res.cloudinary.com/imgresd/image/upload/v1778131385/Github/CFDI02_cvz1gn.png)

### Paso 3 — Ejecutar la utilidad `xsd`

Llama a la herramienta indicando que quieres generar clases (`-c`) en C# (`-l:cs`), seguido de los esquemas en orden de dependencia:

```powershell
xsd -c -l:cs cfdv40.xsd tdCFDI.xsd catCFDI.xsd
```
![App Screenshot](https://res.cloudinary.com/imgresd/image/upload/v1778131385/Github/CFDI03_ov6rkr.png)

### Paso 4 — Verificar la salida

La herramienta procesará los esquemas y confirmará la generación del archivo combinado:

```
Escribiendo el archivo 'C:\Users\Migue\source\repos\xsd-cfdi-mx\cfdv40_tdCFDI_catCFDI.cs'.
```

![App Screenshot](https://res.cloudinary.com/imgresd/image/upload/v1778131385/Github/CFDI04_cskfhg.png)

### Paso 5 — Revisar el archivo generado

En tu explorador de archivos aparecerá el nuevo archivo fuente. Contiene toda la lógica para manipular datos del CFDI 4.0 de forma nativa en .NET.

![App Screenshot](https://res.cloudinary.com/imgresd/image/upload/v1778131385/Github/CFDI05_ne8jxi.png)

### Paso 6 — Integrar en tu solución

Agrega el archivo a tu proyecto de Visual Studio. Tendrás acceso a la clase `public partial class Comprobante` con todas las propiedades listas para usar con `XmlSerializer`.

![App Screenshot](https://res.cloudinary.com/imgresd/image/upload/v1778131386/Github/CFDI06_goaspi.png)

---

## Licencia

Distribuido bajo la licencia [MIT](LICENSE). Los esquemas XSD son propiedad del SAT y se referencian aquí con fines educativos y de integración técnica.
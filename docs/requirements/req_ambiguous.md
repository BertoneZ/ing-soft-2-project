Como Senior QA, realicé el análisis del enunciado "Practica beneficiario.pdf" y detecté las siguientes ambigüedades técnicas y de negocio que deben ser aclaradas para garantizar la calidad del desarrollo[cite: 2]:

### 1. Ambigüedades en Flujo de Acceso y Navegación
*   **"Ingresa al buscador, ingresa a la web":** No se especifica qué buscador (interno o externo) ni qué términos de búsqueda activan el acceso a la web.
*   **"se deberá mostrar el botón o no según las condiciones":** Existe ambigüedad visual. No aclara si el botón debe estar oculto o deshabilitado (en gris) cuando la cuenta no está activa.
*   **"mostrar la pantalla de beneficiario con todos los beneficiarios cargados":** No define si se refiere a una lista histórica de todos los beneficiarios del sistema o específicamente a los beneficiarios asociados a esa cuenta/póliza en particular.

### 2. Ambigüedades en Campos y Tipos de Datos
*   **"Sexo (Checkbox)":** Un checkbox es un elemento booleano (si/no). Al ser un campo de sexo, el enunciado es ambiguo sobre cómo seleccionar opciones como Masculino o Femenino con un solo cuadro de selección, o si existen varios (lo que permitiría selecciones múltiples erróneas).
*   **"Fecha de nacimiento (de 1940 en adelante)":** No define un límite superior de fecha (ej. "hasta la fecha actual") ni el formato de entrada (DD/MM/AAAA).
*   **"Cuit... se debe autogenerar":** No se especifica el algoritmo o lógica de cálculo para la generación del CUIT. Además, menciona que si no es DNI "el campo deja de ser obligatorio", pero no aclara si en ese caso el campo debe ser editable manualmente.
*   **"Nacionalidad (Desplegable)":** A diferencia de otros campos, la nacionalidad no cuenta con una lista en la sección de "Valores posibles", dejando el origen de los datos indeterminado.

### 3. Ambigüedades en Lógica de Negocio y Reglas
*   **"se deben bloquear los campos para no permitir la edición":** Si la persona ya existe pero sus datos (como el domicilio) están desactualizados, la regla de bloqueo impide la actualización de la información, lo cual es una ambigüedad de proceso.
*   **"se debe habilitar la edición del porcentaje de esos beneficiarios":** No aclara si el sistema debe realizar el cálculo automático para llegar al 100% o si el usuario debe editar manualmente cada registro anterior. Tampoco especifica qué sucede si el usuario intenta guardar y la suma no da exactamente 100%.
*   **"El campo cuit se debe autogenerar contemplando... sexo":** Al ser el sexo un checkbox (según el punto anterior), existe una ambigüedad técnica sobre qué valor toma el algoritmo de autogeneración si el checkbox no está marcado.

### 4. Ambigüedades en Validaciones y Mensajería
*   **"mostrar un mensaje de error":** No se definen las etiquetas de los mensajes ni su ubicación (si son mensajes por campo o un cartel general de error).
*   **"Piso":** Este campo aparece en la lista general de domicilio, pero no se menciona en la lista de campos "OBLIGATORIOS", generando duda sobre si debe ser validado o es opcional.

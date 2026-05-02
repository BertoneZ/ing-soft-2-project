Como Lead QA Engineer, he diseñado los siguientes casos de prueba para la funcionalidad de alta de beneficiarios basada en el enunciado analizado. Se han aplicado criterios de diseño para cubrir flujos positivos, negativos y de borde, resolviendo técnicamente las ambigüedades detectadas para asegurar una ejecución precisa.

CP-001: Alta de nuevo beneficiario con persona no existente (Flujo Feliz)
ID: CP-001

TÍTULO: Alta exitosa de beneficiario con datos manuales completos (Persona inexistente)

PRIORIDAD: Alta

TESTER: Zoe Bertone

FECHA EJECUCIÓN:

RESULTADO: PENDIENTE

DESCRIPCIÓN: Validar que el sistema permite dar de alta un beneficiario cuando los datos de identidad no existen previamente en la base de datos, asegurando que todos los campos obligatorios sean procesados.

PRECONDICIONES:

El usuario debe tener una cuenta de seguro de vida en estado "Activo".  

El DNI y Tipo de Documento a utilizar no deben estar registrados en el sistema.  

PASOS DE EJECUCIÓN:

[01] - PASO: Ingresar a la URL de la web del seguro y cargar el número de cuenta activo | DATO UTILIZADO: Nro Cuenta: 102938 (Estado: Activo) | RESULTADO ESPERADO: El sistema debe mostrar el botón de "Alta de beneficiario".  

[02] - PASO: Hacer clic en el botón de "Alta de beneficiario" | DATO UTILIZADO: N/A | RESULTADO ESPERADO: Se visualiza el formulario de carga con todos los campos editables.  

[03] - PASO: Seleccionar Tipo de Documento y cargar Número de Documento | DATO UTILIZADO: Tipo: DNI, Nro: 45.123.456 | RESULTADO ESPERADO: El sistema valida que la persona no existe y mantiene los campos editables.  

[04] - PASO: Completar campos de Datos Personales, Fecha de Nacimiento y Sexo | DATO UTILIZADO: Fecha: 15/05/1995, Sexo: Checkbox Marcado (Masculino) | RESULTADO ESPERADO: El campo CUIT se autogenera correctamente al detectar Tipo DNI.  

[05] - PASO: Completar campos de Domicilio obligatorios y Porcentaje de beneficio | DATO UTILIZADO: Calle: Rivadavia, Nro: 500, CP: 2300, Porcentaje: 100% | RESULTADO ESPERADO: Los datos son aceptados por el formulario.  

[06] - PASO: Hacer clic en el botón "Guardar" | DATO UTILIZADO: N/A | RESULTADO ESPERADO: Se muestra mensaje de "Alta exitosa" y se redirige a la pantalla de beneficiarios con el nuevo registro listado.  

RESULTADO REAL:

OBSERVACIONES:

CP-002: Autocompletado y bloqueo de campos (Persona existente)
ID: CP-002

TÍTULO: Verificación de autocompletado y bloqueo de edición para personas ya registradas

PRIORIDAD: Media

TESTER: Zoe Bertone

FECHA EJECUCIÓN:

RESULTADO: PENDIENTE

DESCRIPCIÓN: Validar que si el DNI ingresado ya existe en el sistema, los datos personales y de domicilio se carguen automáticamente y queden en modo solo lectura.

PRECONDICIONES:

Existencia previa de una persona en la base de datos general (ej. como titular) con DNI: 20.888.999.  

Cuenta de seguro de vida en estado "Activo".  

PASOS DE EJECUCIÓN:

[01] - PASO: Cargar número de cuenta activo y acceder al formulario de alta | DATO UTILIZADO: Nro Cuenta: 102938 | RESULTADO ESPERADO: Formulario de alta desplegado.  

[02] - PASO: Ingresar Tipo y Número de documento de persona existente | DATO UTILIZADO: Tipo: DNI, Nro: 20.888.999 | RESULTADO ESPERADO: Los campos Nombre, Apellido, Fecha de Nacimiento y Domicilio se completan automáticamente.  

[03] - PASO: Intentar editar el campo "Nombre" o "Calle" | DATO UTILIZADO: Entrada de texto teclado | RESULTADO ESPERADO: Los campos están bloqueados (read-only) y no permiten modificaciones.  

[04] - PASO: Cargar el porcentaje de beneficio | DATO UTILIZADO: Porcentaje: 100% | RESULTADO ESPERADO: El campo permite la edición de forma normal.  

[05] - PASO: Hacer clic en "Guardar" | DATO UTILIZADO: N/A | RESULTADO ESPERADO: Alta exitosa y persistencia de los datos recuperados.  

RESULTADO REAL:

OBSERVACIONES:

CP-003: Validación de restricción por estado de cuenta (Caso Negativo)
ID: CP-003

TÍTULO: Restricción de acceso a la funcionalidad por seguro suspendido o dado de baja

PRIORIDAD: Alta

TESTER: nombre_tester

FECHA EJECUCIÓN:

RESULTADO: PENDIENTE

DESCRIPCIÓN: Verificar que el botón de "Alta de beneficiario" no sea accesible para cuentas que no estén en estado activo.

PRECONDICIONES:

Contar con un número de cuenta en estado "Suspendido" y otro en "Dado de baja".  

PASOS DE EJECUCIÓN:

[01] - PASO: Ingresar a la web y cargar número de cuenta suspendido | DATO UTILIZADO: Nro Cuenta: 555444 (Suspendido) | RESULTADO ESPERADO: El sistema no debe mostrar el botón de "Alta de beneficiario".  

[02] - PASO: Regresar al inicio y cargar número de cuenta dado de baja | DATO UTILIZADO: Nro Cuenta: 777888 (Dado de baja) | RESULTADO ESPERADO: El sistema no debe mostrar el botón de "Alta de beneficiario".  

RESULTADO REAL:

OBSERVACIONES:

CP-004: Redistribución de porcentaje de beneficio (Caso de Borde)
ID: CP-004

TÍTULO: Ajuste de porcentajes para múltiples beneficiarios (Suma igual a 100%)

PRIORIDAD: Alta

TESTER: Zoe Bertone

FECHA EJECUCIÓN:

RESULTADO: PENDIENTE

DESCRIPCIÓN: Validar que al agregar un nuevo beneficiario habiendo otros existentes, el sistema permita editar los porcentajes anteriores para que la suma total sea exactamente 100%.

PRECONDICIONES:

La cuenta debe poseer al menos un beneficiario ya cargado con el 100% del beneficio.  

PASOS DE EJECUCIÓN:

[01] - PASO: Iniciar el alta de un nuevo beneficiario | DATO UTILIZADO: Datos válidos aleatorios | RESULTADO ESPERADO: El sistema detecta beneficiarios previos y habilita la edición de sus porcentajes.  

[02] - PASO: Modificar el porcentaje del beneficiario previo y asignar porcentaje al nuevo | DATO UTILIZADO: Beneficiario 1: 50%, Nuevo Beneficiario: 50% | RESULTADO ESPERADO: El sistema permite la edición de ambos campos.  

[03] - PASO: Intentar guardar con una suma total distinta de 100% | DATO UTILIZADO: Beneficiario 1: 40%, Nuevo: 40% (Total 80%) | RESULTADO ESPERADO: El sistema muestra mensaje de error indicando que la suma debe ser 100% y no permite el alta.  

[04] - PASO: Corregir porcentajes para sumar 100% y guardar | DATO UTILIZADO: Total: 100% | RESULTADO ESPERADO: Mensaje de alta exitosa.  

RESULTADO REAL:

OBSERVACIONES:

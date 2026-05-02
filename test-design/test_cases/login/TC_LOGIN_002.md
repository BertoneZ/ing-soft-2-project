CP-002: Autocompletado y bloqueo de campos (Persona existente)
ID: CP-002

TÍTULO: Verificación de autocompletado y bloqueo de edición para personas ya registradas

PRIORIDAD: Media

TESTER: nombre_tester

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

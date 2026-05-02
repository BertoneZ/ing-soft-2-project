CP-001: Alta de nuevo beneficiario con persona no existente (Flujo Feliz)
ID: CP-001

TÍTULO: Alta exitosa de beneficiario con datos manuales completos (Persona inexistente)

PRIORIDAD: Alta

TESTER: nombre_tester

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

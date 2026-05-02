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

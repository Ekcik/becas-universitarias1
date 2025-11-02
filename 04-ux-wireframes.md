
# Wireframes & UX – Becas Universitarias 2.0

Este documento acompaña a los wireframes low‑fi y define comportamientos clave.

## Flujo de Registro (3 pasos)
1. **Paso 1 – Nombre y Apellido**
   - Validación: requerido. Sin este campo no se habilita “Siguiente”.
2. **Paso 2 – DNI**
   - Validación: requerido y sin duplicados.
   - Enviar error si el DNI ya existe en la base.
3. **Paso 3 – Tipo de beca**
   - Selector con las opciones: General, Transporte, Materiales.
   - Al “Enviar solicitud”, mostrar “¡Registro enviado!” y resetear formulario.

## Confirmación
- Mostrar pantalla con mensaje de éxito.
- Enviar correo y (si aplica) WhatsApp en background.
- Opción de “Nueva solicitud” y “Volver al inicio”.

## Panel Administrativo
- Acceso sólo con login.
- Filtros: por tipo de beca y búsqueda por DNI/Nombre.
- Tabla ordenada por fecha (desc).

## Accesibilidad y Usabilidad
- Indicador de progreso (Paso 1/2/3).
- Campos con etiquetas visibles y mensajes de error claros.
- Navegación por teclado soportada.

## Estados Vacíos y Errores
- Si no hay resultados en panel, mostrar estado vacío con ayuda.
- Errores de red: reintento y contacto de soporte.

## Anexos
- Wireframes (PNG): ver carpeta adjunta o PDF consolidado.

# Backlog (Historias de Usuario) – Becas Universitarias 2.0

## HU-001 – Registro de Beca
**Como** estudiante, **quiero** completar un formulario de tres pasos con mis datos personales y tipo de beca, **para** solicitar una beca universitaria de forma rápida y sin errores.

**Criterios de aceptación:**
1. El formulario debe tener tres pasos: Nombre, DNI y Tipo de beca.
2. No se debe permitir avanzar si algún campo está vacío.
3. Al enviar el formulario, se debe guardar la solicitud en la base de datos.
4. Debe mostrarse un mensaje de confirmación visual ("¡Registro enviado!").
5. El sistema debe evitar registros duplicados por DNI.

**DoR (Definition of Ready):**
- La historia está priorizada por el PO.
- Los campos están definidos.
- Validaciones básicas confirmadas por QA.

**DoD (Definition of Done):**
- Formulario visible en `/registro`.
- API funcional (`POST /api/solicitudes`).
- Validaciones implementadas.
- Pruebas E2E aprobadas.

---

## HU-002 – Confirmación Automática
**Como** estudiante, **quiero** recibir una confirmación por correo electrónico o WhatsApp, **para** asegurarme de que mi solicitud fue registrada correctamente.

**Criterios de aceptación:**
1. El sistema debe enviar un correo de confirmación tras el registro.
2. Si está disponible la integración de WhatsApp, enviar mensaje adicional.
3. En entorno de desarrollo, debe simularse el envío (log o consola).
4. El mensaje debe incluir el tipo de beca y fecha de solicitud.

**DoR:**
- Endpoint de solicitudes funcional.
- Credenciales SMTP configuradas o mock activo.

**DoD:**
- Email/WhatsApp enviados exitosamente.
- Test de integración pasa en QA.
- Logs verificados.

---

## HU-003 – Panel Administrativo
**Como** administrador, **quiero** visualizar todas las solicitudes en una tabla y filtrarlas por tipo de beca, **para** gestionar fácilmente las inscripciones.

**Criterios de aceptación:**
1. El panel debe listar las solicitudes con: fecha, nombre, DNI y tipo de beca.
2. Debe poder filtrarse por tipo (General, Transporte, Materiales).
3. Las solicitudes deben mostrarse ordenadas por fecha de creación (descendente).
4. Solo usuarios autenticados deben acceder al panel.

**DoR:**
- Base de datos poblada.
- Mock de autenticación disponible.

**DoD:**
- Panel visible en `/admin`.
- Filtro funcional.
- Acceso restringido con NextAuth.
- Test E2E “admin view” aprobado.

---

## HU-004 – Login de Administrador
**Como** administrador, **quiero** ingresar al sistema con correo y contraseña, **para** acceder al panel de gestión de solicitudes de forma segura.

**Criterios de aceptación:**
1. Login con credenciales válidas (email, password).
2. Validación de hash de contraseña (bcrypt).
3. Redirección a `/admin` tras login correcto.
4. Acceso denegado si no hay sesión activa.
5. Botón de logout disponible.

**DoR:**
- Módulo NextAuth instalado.
- Usuario admin existente en la base de datos.

**DoD:**
- Login funcional.
- Autorización protegida con sesión JWT.
- Pruebas manuales y automáticas OK.

---

## HU-005 – Seguridad y Calidad
**Como** administrador del sistema, **quiero** que los datos personales y las solicitudes estén protegidos, **para** garantizar la privacidad y confiabilidad del sistema.

**Criterios de aceptación:**
1. Todos los inputs deben validarse para evitar inyecciones o errores.
2. Los passwords deben almacenarse encriptados.
3. El acceso a `/admin` debe estar restringido.
4. Las pruebas de seguridad deben incluir intentos de acceso no autorizado.

**DoR:**
- Funcionalidades previas completas.
- QA planificado.

**DoD:**
- Validaciones y sanitización implementadas.
- Hash de contraseñas funcionando.
- Reporte QA actualizado.


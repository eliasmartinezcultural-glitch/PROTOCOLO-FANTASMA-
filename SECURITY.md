# Protocolo de seguridad — PROTOCOLO FANTASMA

**Estado: interfaz estática con controles de conveniencia; no apta para información confidencial.**

## 1. Claves de interfaz

- Acceso general esperado: `enroque`.
- Acceso a la consola del fundador esperado: `enroque2`.
- La clave general se valida mediante SHA-256 en el navegador y la consola del fundador tiene una validación independiente.
- Se quitó la alternativa que aceptaba directamente la clave general como texto plano.
- El acceso del fundador exige que la sesión general esté abierta. Cerrar la sala vuelve al panorama y limpia el campo de la clave.

## 2. Límite crítico: GitHub Pages no protege secretos

Esta aplicación es HTML, CSS y JavaScript descargados al navegador desde un repositorio público. Cualquier visitante técnicamente capaz puede leer el código, modificar las comprobaciones, abrir las secciones ocultas o inspeccionar y editar el almacenamiento local. Un hash de contraseña incluido en JavaScript no convierte la página en un sistema de autenticación seguro.

Los datos de investigación, actividad, temas y notas se guardan en `localStorage` del navegador. No se sincronizan ni están cifrados por esta aplicación. El registro de visitas y copias solo observa eventos del navegador local; no equivale a una analítica central de visitantes ni permite saber de forma fiable quién accedió.

**No almacenar aquí:** fuentes confidenciales, contraseñas, datos personales sensibles, credenciales, documentos privados ni material cuya exposición pueda perjudicar a una persona.

## 3. Para conseguir privacidad real

1. Mantener el sitio público únicamente con contenido destinado a publicación.
2. Mover la consola del fundador a un servicio con autenticación del lado del servidor (por ejemplo, un backend con sesiones seguras o un proveedor de identidad).
3. Guardar secretos solo en variables de entorno del servidor; nunca en HTML, JavaScript, repositorio o almacenamiento del navegador.
4. Autorizar cada operación sensible en el servidor, no solo ocultar botones o secciones.
5. Guardar datos privados en una base de datos con reglas de acceso por usuario, cifrado en tránsito, copias de seguridad y registro de auditoría.
6. Proteger contra intentos repetidos, cerrar sesiones por inactividad, usar cookies `HttpOnly`, `Secure`, `SameSite` y protección CSRF cuando corresponda.
7. Revisar permisos del repositorio y eliminar del historial cualquier secreto que alguna vez se haya publicado. Cambiar las claves si se reutilizaron en otros servicios.

## 4. Verificación tras cambios

- Probar la clave general correcta e incorrecta.
- Probar la clave del fundador correcta e incorrecta.
- Confirmar que cancelar o cerrar la consola vuelve al panorama.
- Probar escritorio y móvil.
- No interpretar estas pruebas como una auditoría de seguridad ni como protección real de datos privados.

## 5. Claves expuestas en la conversación

Las claves escritas en una conversación y las que se usan en código cliente deben considerarse conocidas. Para privacidad real, reemplazarlas por credenciales nuevas gestionadas por el servidor. No reutilizarlas en correo, GitHub u otras cuentas.

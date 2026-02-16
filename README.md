### 📦 ¿Qué es OfiStock?

Es una plataforma web centralizada para la gestión de materiales de oficina. Su objetivo es que los empleados soliciten insumos de forma digital y que el administrador tenga un control exacto y en tiempo real del inventario almacenado en la nube.

---

### 👥 Guía de Uso para Empleados (Solicitantes)

Esta es la vista predeterminada al abrir la aplicación.

1. **Explorar el Catálogo:** Verás una lista de materiales (papel, tóner, bolígrafos, etc.). Cada tarjeta muestra el **Stock actual** (cuánto queda en la oficina).
2. **Añadir al Carrito:** Haz clic en **"Añadir"** en los productos que necesites. Si un producto no tiene stock, el botón se desactivará automáticamente.
3. **Gestionar Solicitud:** En el panel derecho (o inferior en móviles), verás tu lista. Puedes aumentar o disminuir cantidades con los botones `+` y `-`.
4. **Identificación:** * Escribe tu **Nombre**.
* Selecciona tu **Departamento** (Administración, Almacén, Contabilidad, etc.).


5. **Procesar y Reportar:** Haz clic en **"Procesar"**.
* **En la Base de Datos:** El sistema restará automáticamente las cantidades solicitadas del inventario global.
* **En tu Correo:** Se abrirá tu aplicación de correo (Outlook/Gmail) con un reporte listo para enviar a `soporte@harryheinsen.com`. **Debes darle a "Enviar" en tu correo para formalizar el aviso.**



---

### 🔐 Guía de Uso para el Administrador

Para acceder, haz clic en el botón **"Admin"** en la barra superior.

1. **Acceso:** Introduce la contraseña (por defecto: `admin123`).
2. **Pestaña "Inventario":**
* **Crear Insumos:** Usa el botón **"Nuevo"** para registrar un producto (ej. "Grapas", categoría "Papelería", stock "50", unidad "cajas").
* **Editar:** Si llega mercancía nueva, haz clic en el icono de lápiz 📝 de un producto y actualiza su stock.
* **Eliminar:** Borra productos obsoletos con el icono de basura 🗑️.


3. **Pestaña "Solicitudes":**
* Aquí verás todos los pedidos realizados por los empleados, ordenados por fecha (los más recientes primero).
* Cada tarjeta muestra quién pidió, de qué departamento y el detalle de los materiales.
* **Despachar:** Una vez entregues los materiales físicos al empleado, haz clic en **"Entregar"**. El estatus cambiará a "Entregado" y la tarjeta se verá opaca para indicar que ya fue atendida.



---

### ⚙️ Funcionamiento Técnico (Bajo el capó)

Para que el sistema respete las **reglas de seguridad** que definimos, el **Canvas** funciona así:

* **Colección Única:** Todo se guarda dentro de una colección llamada `tickets`.
* **Diferenciador (`docType`):** Para no mezclar las cosas, el sistema etiqueta cada documento. Los productos tienen un campo `docType: "inventory"` y las órdenes tienen `docType: "request"`.
* **Sincronización:** Si el administrador cambia un stock, el empleado lo ve reflejado en su pantalla al instante gracias a la tecnología *Real-time* de Firebase.

Esta estructura asegura que la aplicación sea rápida, no pierda datos al cerrar el navegador y cumpla con los permisos de acceso de tu proyecto `tickets-2025hh`.

¿Hay alguna función adicional que te gustaría integrar para mejorar el flujo de trabajo?

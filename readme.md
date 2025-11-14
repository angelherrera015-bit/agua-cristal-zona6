💧 AGUA CRISTAL ZONA 6 - Sistema de Gestión de Pedidos

Este es un sistema de gestión de pedidos en tiempo real desarrollado en una sola página HTML, utilizando Tailwind CSS para el estilo y Firebase Firestore para la persistencia de datos y actualizaciones en tiempo real. Incluye autenticación por perfiles y funciones de análisis de ventas potenciadas por Gemini AI.

🛠️ Tecnologías Utilizadas

HTML/JavaScript: Base del front-end y lógica de negocio.

Tailwind CSS: Framework de CSS para un diseño moderno y responsivo (colores azul agua).

Firebase Firestore: Base de datos NoSQL para almacenamiento en tiempo real de pedidos y base de clientes.

Gemini API: Utilizada para generar mensajes de lealtad personalizados y análisis de ventas diarios.

🔑 Autenticación y Perfiles

La aplicación requiere una contraseña en la pantalla de inicio de sesión (AGUA CRISTAL ZONA 6) para asignar el rol de usuario:

Perfil

Contraseña

Rol y Funcionalidad

ADMINISTRADOR

Angel2006$

Acceso completo. Puede ver pedidos, marcar repartido, editar, eliminar, exportar a CSV y acceder al Análisis de Ventas (Gemini AI).

USUARIO 1

Aguacristal06

Acceso limitado. Puede registrar pedidos, ver pedidos y marcar repartido (solo pedidos a domicilio). No puede editar, eliminar ni exportar.

📦 Estructura de la Base de Datos (Firestore)

La aplicación utiliza dos colecciones públicas bajo el esquema de Canvas para el almacenamiento centralizado:

Colección de Clientes (Base de Datos):

Ruta: /artifacts/{appId}/public/data/clients

Propósito: Almacena el phone, name, nit y address de los clientes para el auto-relleno de formularios.

Colección de Pedidos:

Ruta: /artifacts/{appId}/public/data/orders

Propósito: Almacena cada registro de pedido, incluyendo type, quantity, total, isDelivered, createdAt, etc.

✨ Funcionalidades Potenciadas por Gemini AI

1. Generador de Mensajes de Lealtad (Formulario de Pedido)

Uso: Crea un mensaje corto y amigable para el cliente, agradeciendo su compra e incentivando la lealtad, sin mencionar precios.

Función: window.generateLoyaltyMessage()

2. Análisis de Ventas Diarias (Control de Pedidos - Administrador)

Uso: El administrador puede obtener un resumen ejecutivo (máx. 40 palabras) del desempeño de ventas del día actual (total vendido, cantidad de pedidos, tipo de pedido), junto con una sugerencia estratégica para el día siguiente.

Función: window.generateDailySalesAnalysis()

📝 Flujo de Trabajo

Inicio de Sesión: Ingrese la contraseña de ADMINISTRADOR o USUARIO 1.

Registro de Pedido:

Seleccione 'A DOMICILIO' (Q.10.00) o 'ENTREGA FÍSICA' (Q.9.00).

Al ingresar el Teléfono, la aplicación intenta buscar y rellenar automáticamente los datos del cliente guardado.

El campo Dirección es obligatorio solo para pedidos A DOMICILIO.

El botón WhatsApp permite enviar un mensaje de confirmación amigable.

Control de Pedidos:

Todos los pedidos se muestran en tiempo real.

Ambos perfiles pueden marcar la casilla "Repartido" para pedidos a domicilio.

El ADMINISTRADOR puede editar, eliminar y descargar el historial completo en formato CSV (Excel).
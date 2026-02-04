# Ordena

Plataforma web para gestión integral de inventario y pedidos en una cadena de ferreterías. Conecta bodega central y sucursales, incorpora control por roles, flujo de solicitudes y un dashboard con métricas clave, además de notificaciones automáticas por eventos de stock.

---

## ¿Qué problema resuelve?
- Visibilidad del stock en tiempo real entre bodega y sucursales.
- Centralización del flujo de solicitudes y pedidos con estados e historial.
- Reducción de quiebres y sobrestock mediante umbrales de stock mínimo/máximo.
- Trazabilidad de movimientos de inventario y generación de informes.
- Digitalización de documentos (Guía de despacho, Acta de recepción, OCI) y soporte de códigos QR.

---

## Características principales
- Inventario: altas, bajas y ajustes con historial (movimientos).
- Pedidos y solicitudes: creación, aprobación, seguimiento y recepción.
- Notificaciones automáticas: stock crítico y superación de máximos.
- Dashboard con gráficos (barras, tortas, comparativos).
- Búsqueda de productos similares y validaciones para evitar duplicados.
- Gestión de proveedores y personal de entrega.
- Generación de documentos PDF (Guía de Despacho, Acta de Recepción, OCI).
- QR: generación y escaneo para identificar productos.
- Acceso por roles y rutas protegidas.

---

## Stack tecnológico
- Frontend: React + Vite + TypeScript, Material UI (MUI), Zustand, React Router, Chart.js.
- Backend: Django + Django REST Framework, autenticación JWT.
- Base de datos: PostgreSQL.
- Utilidades: Axios, jsPDF + autotable, html5-qrcode, Tesseract.js (OCR selectivo).

---

## Arquitectura
- Monorepo con dos módulos:
  - `Ordena/` Frontend (cliente web).
  - `backend/` API REST (Django + DRF).
- La API expone endpoints bajo `/api`, incluyendo productos, pedidos, solicitudes, proveedores, notificaciones e historial.

---

## Ejecución (resumen)
- Backend:
  - Crear entorno virtual e instalar dependencias (`requirements.txt`).
  - Configurar variables de entorno (conexión a PostgreSQL, JWT, CORS).
  - Aplicar migraciones y ejecutar servidor.
- Frontend:
  - Instalar dependencias.
  - Levantar el servidor de desarrollo.
  - Ajustar `baseURL` del cliente si cambia la URL de la API (ver `Ordena/src/services/api.ts`).

---

## Seguridad y acceso
- Autenticación mediante JWT con protección de rutas en el frontend.
- Rutas y vistas condicionadas por rol (bodega/sucursal).
- Interceptores de cliente para renovar sesión y redirigir en 401.

---

## Estado del proyecto
Proyecto funcional y listo para despliegue con ajustes de seguridad, configuración de producción y CI/CD. Ideal para presentar como solución de gestión de inventario y pedidos en retail/ferreterías.

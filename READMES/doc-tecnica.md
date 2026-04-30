# Guía Maestra de Documentación Técnica (V4)

**Plataforma:** [Nombre de tu Plataforma]
**Tecnología Base:** Node.js + React + **Google Firestore**

---

## SECCIÓN 1: Infraestructura y Ecosistema

*Esta sección define las herramientas, versiones y la seguridad del sistema.*

### Paso a Paso para el Documentador (Luis Daniel):
1. Abre los archivos `package.json` (front y back).
2. Identifica las versiones exactas de las librerías principales.
3. Describe el flujo de seguridad (cómo se protege el acceso).

### EJEMPLO DE REDACCIÓN ESPERADA:

**Stack Tecnológico:**
* **Frontend:** React v18.2 con Vite y TailwindCSS.
* **Backend:** Node.js v20.x corriendo en Google Cloud Functions.
* **Autenticación:** Firebase Auth (método Email/Password y Google Login).

**Seguridad y Red:**
* **Protección de Datos:** Los tokens de sesión son gestionados por el SDK de Firebase (Admin SDK) con verificación de `uid` en cada petición.

---

## SECCIÓN 2: Diccionario de Datos (NoSQL - Firestore)

*Firestore no tiene tablas, tiene Colecciones y Documentos. Debes documentar la "forma" de los datos.*

### Paso a Paso para el Documentador:
1. Por cada **Colección**, crea una tabla de campos.
2. Si un campo es un objeto (ej: un perfil dentro de un usuario), desglósalo en una lista separada debajo de la tabla.
3. Especifica los tipos de datos de Firestore (String, Number, Boolean, Timestamp, Map, Array).

### EJEMPLO DE REDACCIÓN ESPERADA:

**Colección:** `usuarios` (Raíz)
**Propósito:** Almacena la información de perfil y configuración de cada cuenta.

| Campo (Key) | Tipo de Dato | ¿Requerido? | Descripción Funcional |
| :--- | :--- | :--- | :--- |
| `email` | String | Sí | Correo único del usuario. |
| `perfil` | **Map (Objeto)**| Sí | Datos personales (ver desglose abajo). |
| `ultimo_acceso`| Timestamp | Sí | Fecha y hora del último login. |

**Desglose del objeto `perfil`:**
* `nombre`: String (Nombre completo).
* `telefono`: String (En formato internacional +57).
* `avatar_url`: String (Link a Firebase Storage).

---

## SECCIÓN 3: Lógica de Negocio y Flujos Críticos

*Aquí explicas los procesos que hacen que el negocio funcione.*

### Paso a Paso para el Documentador:
1. Elige un proceso (ej: "Crear una nueva orden").
2. Describe el "Camino Feliz" (todo sale bien) paso a paso.
3. Describe los "Casos de Borde" y errores (qué pasa si algo falla).

### EJEMPLO DE REDACCIÓN ESPERADA:

**Flujo: Registro de Nueva Venta**
1. **Entrada:** El vendedor envía los datos del producto y cliente desde el Front.
2. **Validación:** El Backend verifica en Firestore si el producto tiene `stock > 0`.
3. **Acción:** Se crea un documento en la colección `ventas` y se resta el stock en `productos`.

**Casos de Error / Borde:**
* Si el stock es insuficiente, el sistema debe retornar un error HTTP 400 y NO crear la venta en la base de datos para garantizar la atomicidad.

---

## SECCIÓN 4: Catálogo de API (Endpoints)

*El contrato que Cursor (IA) o los desarrolladores leerán para conectar el Front con el Back.*

### Paso a Paso para el Documentador:
1. Define la ruta, el método HTTP y qué datos recibe.
2. Muestra un ejemplo de éxito en formato JSON.
3. Lista los códigos de error posibles (400, 401, 404, 500, etc.).

### EJEMPLO DE REDACCIÓN ESPERADA:

**Endpoint:** `POST /api/v1/pagos/verificar`
**Descripción:** Recibe el ID de una transacción y confirma el estado con la pasarela.

**Payload de Entrada:**
```json
{
  "transaccion_id": "ABC-123",
  "monto": 50000
}
```

**Respuesta de Éxito (200 OK):**
```json
{
  "status": "approved",
  "auth_code": "998877"
}
```

**Errores Posibles:**
* `402 Payment Required`: Fondos insuficientes en la tarjeta.
* `503 Service Unavailable`: Pasarela de pagos externa caída.

---

## SECCIÓN 5: Guía de Instalación "Zero to Hero"

*Cómo preparar el entorno para que cualquier persona (o IA) empiece a programar desde cero sin ayuda.*

### Paso a Paso para el Documentador:
1. Lista los comandos exactos de terminal para instalar dependencias y correr el proyecto.
2. Explica cada variable obligatoria del archivo `.env`.

### EJEMPLO DE REDACCIÓN ESPERADA:

**1. Comandos de Inicialización:**
```bash
git clone [url-repositorio]
cd [nombre-carpeta]
npm install
npm run dev
```

**2. Variables de Entorno (.env):**

| Variable | Valor / Origen | Propósito |
| :--- | :--- | :--- |
| `FIREBASE_API_KEY` | Consola Firebase > Project Settings | Permite la inicialización de la app cliente. |
| `STRIPE_SECRET_KEY` | Dashboard Stripe (Modo Test) | Necesaria para crear intenciones de cobro desde el backend. |
```

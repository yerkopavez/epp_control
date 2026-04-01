# ⛑ EPP Control

Sistema de gestión de entrega de Equipos de Protección Personal (EPP).

## Acceso

🌐 **URL del sistema:** `https://TU-USUARIO.github.io/epp-control`

Para acceder necesitas credenciales — contacta al administrador del sistema.

---

## Instrucciones para publicar en GitHub Pages

### 1. Subir los archivos al repositorio

Sube estos archivos a tu repositorio GitHub:
- `index.html` ← la aplicación completa
- `supabase.min.js` ← librería Supabase
- `chart.min.js` ← librería de gráficos
- `qrcode.min.js` ← generador QR

### 2. Activar GitHub Pages

1. Ve a tu repositorio en GitHub
2. **Settings** → **Pages**
3. En *Source* selecciona: **Deploy from a branch**
4. Branch: `main` · Folder: `/ (root)`
5. Clic en **Save**
6. En ~2 minutos tendrás la URL: `https://tu-usuario.github.io/nombre-repo`

### 3. Primera vez que entras

1. Abre la URL
2. Haz clic en **"⚙ Configurar conexión Supabase"**
3. Ingresa tu **Project URL** y **Anon Key** de Supabase
4. Clic en **Guardar**
5. Inicia sesión con tu email y contraseña

La configuración se guarda en el navegador — la próxima vez va directo al login.

---

## Roles de usuario

| Rol | Permisos |
|-----|---------|
| **Admin** | Todo: entregas, inventario, trabajadores, eliminar con log, usuarios |
| **Supervisor** | Registrar entregas, ver historial, gestionar EPP y trabajadores |
| **Auditor** | Solo lectura: ver historial, reportes y formularios |

---

## Para agregar nuevos usuarios

1. Ve a **Supabase → Authentication → Users → Add user**
2. Ingresa email y contraseña, marca *Auto Confirm*
3. Copia el UUID del usuario creado
4. En el sistema, ve a **Administración → Registrar usuario**
5. Pega el UUID, escribe nombre, email y elige el rol

---

## Soporte de archivos para importar

**Trabajadores (CSV):** columnas en orden: `Nombre, Apellido, RUT, Cargo, PIN`

**EPP (CSV):** columnas en orden: `Nombre, Categoría, Stock, StockMínimo, Unidad`

Categorías válidas: Cabeza, Vista, Oídos, Respiración, Manos, Pies, Cuerpo, Altura, Otro

---

## Scripts SQL necesarios

Ejecutar en Supabase → SQL Editor en este orden:
1. `supabase_init.sql` — tablas principales
2. `log_cambios.sql` — tabla de auditoría (para eliminaciones)

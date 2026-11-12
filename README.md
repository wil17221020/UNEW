# RutaFlota

Prototipo de una app de viajes tipo Uber para una compañía que alquila vehículos a conductores en Santo Domingo.

Es **una sola app a pantalla completa**. Al abrirla eliges cómo usarla:

- **Pedir un viaje (pasajero):** buscas el destino, eliges categoría (Económico, Confort o XL) con precio fijo y pagas en efectivo, con tarjeta o con cuenta corporativa. Ves al conductor llegar en el mapa, recibes un PIN de seguridad, puedes compartir el viaje o usar el botón SOS, y al final calificas y dejas propina. En el menú están *Tus viajes* y *Billetera*.
- **Conducir (conductor de la flota):** te conectas, recibes solicitudes con 15 segundos para aceptar, vas a recoger, inicias el viaje con el PIN del pasajero y lo finalizas. Arriba ves lo ganado hoy; en el menú están *Ganancias* (con el saldo semanal con la flota: alquiler y comisión) y *Mi vehículo* (con el mantenimiento).

El **panel de la oficina** está aparte, en la dirección de la app terminada en `#flota`. Desde ahí se ven los indicadores del día, el mapa en vivo, las alertas, los vehículos, los conductores y sus pagos, los viajes, los clientes corporativos y las tarifas.

> **Es un prototipo para demostración.** Los datos son de ejemplo, el mapa es esquemático, el tiempo va acelerado y los pagos son simulados. Cada teléfono funciona por su cuenta: los demás conductores y pasajeros son simulados.

**App:** `https://TU-USUARIO.github.io/rutaflota/`
**Panel de la oficina:** `https://TU-USUARIO.github.io/rutaflota/#flota`

(Cambia `TU-USUARIO` por tu usuario de GitHub después de publicarla.)

---

## Cómo publicarla en GitHub (sin instalar nada)

1. Entra a [github.com](https://github.com) con tu cuenta.
2. Arriba a la derecha toca **+** → **New repository**.
3. Nombre: `rutaflota`. Déjalo en **Public** y toca **Create repository**.
4. En la página del repositorio nuevo toca **uploading an existing file**.
5. Descomprime el .zip y arrastra **todo el contenido de la carpeta** (no la carpeta en sí): `index.html`, `manifest.webmanifest`, `sw.js`, `README.md`, `.nojekyll` y la carpeta `icons`. Toca **Commit changes**.
6. Ve a **Settings** → **Pages**. En *Branch* elige **main** y la carpeta **/(root)**, y toca **Save**.
7. Espera uno o dos minutos y recarga esa página. Arriba aparece el enlace para compartir.

> Si el archivo `.nojekyll` no aparece al arrastrar (algunos sistemas ocultan los archivos que empiezan con punto), no pasa nada: la app funciona igual.

**Para actualizarla más adelante:** en el repositorio toca **Add file** → **Upload files**, arrastra los archivos nuevos y confirma. Se reemplazan los anteriores.

## Cómo instalarla en el teléfono

- **Android (Chrome):** abre el enlace → menú ⋮ → **Instalar app** o **Agregar a la pantalla principal**.
- **iPhone (Safari):** abre el enlace → botón **Compartir** → **Agregar a inicio**.

Queda con su ícono y abre a pantalla completa como una app normal.

## Guía rápida para quienes la prueban

1. Abre la app y toca **Pedir un viaje**. Elige una cuenta (María es personal; Pedro tiene cuenta corporativa).
2. Escribe un destino, elige categoría y pago, y toca **Confirmar**. Sigue el viaje hasta el final y califica.
3. En el menú (☰), toca **Conducir con RutaFlota** y elige un conductor.
4. Espera unos segundos: llega una solicitud. **Acepta**, ve a recoger, escribe el PIN (aparece como ayuda en pantalla) y finaliza el viaje.
5. En el menú, abre **Panel de la flota** para ver todo desde la oficina.

## Para llevarla a producción

| Parte | En el prototipo | En la versión real |
|---|---|---|
| Servidor y base de datos | No hay; todo corre en el teléfono | Backend (Node.js) con PostgreSQL y conexión en tiempo real |
| Conexión pasajero ↔ conductor | Simulada | Real entre teléfonos, a través del servidor |
| Mapas y navegación | Mapa esquemático | Google Maps o Mapbox |
| Ubicación | Simulada | GPS del teléfono |
| Pagos | Simulados | Pasarela local (por ejemplo Azul o CardNet) |
| Usuarios | Cuentas de ejemplo | Registro e inicio de sesión por SMS |
| Apps | App web instalable | App web o apps nativas en Google Play y App Store |

## Archivos

```
index.html            La app completa (HTML, estilos y lógica)
manifest.webmanifest  Datos para instalarla en el teléfono
sw.js                 Permite que abra rápido y sin conexión
icons/                Íconos de la app
```

<img width="361" height="751" alt="image" src="https://github.com/user-attachments/assets/93e92442-c0dc-4709-be35-00fa5c856fe9" />
<img width="339" height="753" alt="image" src="https://github.com/user-attachments/assets/482204de-c51e-43bd-8d95-f6e799ebfb71" />
<img width="342" height="750" alt="image" src="https://github.com/user-attachments/assets/a50fb8b8-6d3a-4691-8bd9-4469650f35be" />
<img width="350" height="749" alt="image" src="https://github.com/user-attachments/assets/678fc11c-604e-481b-a4ec-c910fdf21155" />
<img width="359" height="751" alt="image" src="https://github.com/user-attachments/assets/270547e6-c8ff-4f79-97ba-a1ed14592bc8" />
<img width="349" height="748" alt="image" src="https://github.com/user-attachments/assets/467159e3-d71e-429b-8719-33c20fa963d5" />
<img width="350" height="746" alt="image" src="https://github.com/user-attachments/assets/54dc3481-e05b-495b-ab16-9eaca81f30e2" />
<img width="354" height="746" alt="image" src="https://github.com/user-attachments/assets/3d98ba80-02ca-4ef3-bdda-8c98921a7d85" />
<img width="347" height="754" alt="image" src="https://github.com/user-attachments/assets/a7a4d285-8940-45a2-89c0-6b8bfc934ae9" />
<img width="394" height="780" alt="image" src="https://github.com/user-attachments/assets/adb0aebd-d63b-414c-83c0-6c1db5f212d7" />
<img width="365" height="757" alt="image" src="https://github.com/user-attachments/assets/a4702910-e08b-492c-af29-f1f742638612" />


Actúa como un creador de software, diseñador de aplicaciones móviles multiplataforma. Poner Información necesaria, paso a paso para que un Estudiante nivel Preparatoria pueda dominar lo Proporcionado. Entregar todo lo solicitado en una respuesta.

Vamos a comenzar. Necesitaré empezar la elaboración de mi Proyecto Final, necesito que antes de elaborar cualquier petición me hagas una pregunta confirmando todo lo que me proporcionarás Así evitaremos errores y alargar el procedimiento más de lo solicitado. Aquí te va el Plan de Implementación que será la guía para realizar el proyecto. 

Me darás el procedimiento Paso a Paso para llevar mi Proyecto a cabo, respetando el Plan de Implementación, tambíen te proporcionaré las Tablas necesarias para las bases de datos. 

Para terminar, te brindaré Imagenes Adjuntas sobre como se elaborará el diseño de la página.
----
CLIENTE Compradores registrados en la tienda 01 / 12 Campo Tipo Llave Descripción id_cliente INT PK Identificador único del cliente nombre VARCHAR(100) Nombre completo email VARCHAR(120) Correo electrónico (único) telefono VARCHAR(20) Número de contacto direccion VARCHAR(200) Dirección de envío principal fecha_nacimiento DATE Para segmentación y cumpleaños puntos_lealtad INT Saldo del programa de fidelidad fecha_registro DATE Cuándo se registró por primera vez activo BOOLEAN Indica si la cuenta está habilitada

VENTA Transacciones de compra 02 / 12 Campo Tipo Llave Descripción id_venta INT PK Identificador único de la venta id_cliente INT FK Referencia al cliente que compró id_empleado INT FK Empleado que procesó la venta id_sucursal INT FK Sucursal donde se realizó fecha DATE Fecha y hora de la transacción subtotal DECIMAL(10,2) Importe antes de impuestos impuesto DECIMAL(10,2) IVA aplicado total DECIMAL(10,2) Importe total cobrado metodo_pago VARCHAR(30) Efectivo, tarjeta, transferencia… estatus VARCHAR(20) Pagada, cancelada, pendiente folio VARCHAR(30) Número de ticket o factura

DETALLE_VENTA Renglones de cada transacción 03 / 12 Campo Tipo Llave Descripción id_detalle INT PK Identificador del renglón id_venta INT FK Venta a la que pertenece id_variante INT FK Variante específica (talla/color) id_promocion INT FK Promoción aplicada (si aplica) cantidad INT Número de piezas vendidas precio_unitario DECIMAL(10,2) Precio al momento de la venta descuento DECIMAL(10,2) Monto descontado en el renglón subtotal DECIMAL(10,2) Importe final del renglón

PRODUCTO Catálogo maestro de artículos 04 / 12 Campo Tipo Llave Descripción id_producto INT PK Identificador único del producto id_categoria INT FK Categoría a la que pertenece id_proveedor INT FK Proveedor que lo suministra nombre VARCHAR(150) Nombre comercial del artículo sku VARCHAR(40) Código de referencia interno (único) descripcion TEXT Descripción detallada precio_base DECIMAL(10,2) Precio de lista sin descuentos costo DECIMAL(10,2) Costo de adquisición imagen_url VARCHAR(255) URL de la foto principal activo BOOLEAN Si el producto está en catálogo activo fecha_alta DATE Fecha en que se incorporó al catálogo

VARIANTE Combinaciones de talla y color por producto 05 / 12 Campo Tipo Llave Descripción id_variante INT PK Identificador único de la variante id_producto INT FK Producto al que pertenece talla VARCHAR(10) XS, S, M, L, XL, XXL, numérica… color VARCHAR(40) Nombre o código hex del color codigo_barras VARCHAR(50) EAN-13 o código interno precio_diferencial DECIMAL(10,2) Sobreprecio respecto al base (si aplica) activo BOOLEAN Si la variante está disponible

CATEGORIA Árbol de clasificación de productos 06 / 12 Campo Tipo Llave Descripción id_categoria INT PK Identificador único nombre VARCHAR(80) Nombre de la categoría (Vestidos, Blusas…) id_categoria_padre INT FK Referencia a sí misma para subcategorías descripcion VARCHAR(200) Descripción opcional de la categoría nivel INT Profundidad en el árbol (1=raíz) activo BOOLEAN Si la categoría está visible

INVENTARIO Stock por variante y sucursal 07 / 12 Campo Tipo Llave Descripción id_inventario INT PK Identificador del registro id_variante INT FK Variante de producto id_sucursal INT FK Sucursal o bodega cantidad INT Piezas disponibles actualmente cantidad_minima INT Punto de reorden para alertas ultima_actualizacion DATE Fecha del último movimiento

SUCURSAL Puntos de venta y bodegas 08 / 12 Campo Tipo Llave Descripción id_sucursal INT PK Identificador único de la sucursal nombre VARCHAR(100) Nombre o alias de la tienda direccion VARCHAR(200) Dirección física completa ciudad VARCHAR(80) Ciudad donde opera estado VARCHAR(60) Estado / provincia telefono VARCHAR(20) Teléfono de contacto tipo VARCHAR(20) Tienda, bodega, outlet… activo BOOLEAN Si la sucursal está en operación

EMPLEADO Personal de la empresa 09 / 12 Campo Tipo Llave Descripción id_empleado INT PK Identificador único del empleado id_sucursal INT FK Sucursal donde trabaja nombre VARCHAR(100) Nombre completo puesto VARCHAR(60) Gerente, vendedor, cajero… email VARCHAR(120) Correo corporativo telefono VARCHAR(20) Teléfono de contacto salario DECIMAL(10,2) Salario base mensual fecha_ingreso DATE Fecha de contratación activo BOOLEAN Si el empleado está activo

PROVEEDOR Fabricantes y distribuidores 10 / 12 Campo Tipo Llave Descripción id_proveedor INT PK Identificador único nombre VARCHAR(120) Razón social o nombre comercial contacto VARCHAR(100) Nombre del representante email VARCHAR(120) Correo de contacto telefono VARCHAR(20) Teléfono principal pais VARCHAR(60) País de origen ciudad VARCHAR(80) Ciudad de la empresa proveedora condiciones_pago VARCHAR(100) Crédito a 30 días, contado… activo BOOLEAN Si el proveedor sigue activo

DEVOLUCION Registro de devoluciones posventa 11 / 12 Campo Tipo Llave Descripción id_devolucion INT PK Identificador único id_venta INT FK Venta original relacionada id_variante INT FK Variante devuelta id_empleado INT FK Empleado que gestionó la devolución fecha DATE Fecha en que se realizó cantidad INT Piezas devueltas motivo VARCHAR(200) Razón declarada por el cliente tipo_resolucion VARCHAR(30) Reembolso, cambio, nota de crédito monto_reembolso DECIMAL(10,2) Importe devuelto al cliente estatus VARCHAR(20) Pendiente, aprobada, rechazada

PROMOCION Descuentos y campañas comerciales 12 / 12 Campo Tipo Llave Descripción id_promocion INT PK Identificador único nombre VARCHAR(100) Nombre de la campaña descripcion VARCHAR(200) Detalle de la promoción tipo VARCHAR(30) Porcentaje, monto fijo, 2x1… descuento_valor DECIMAL(10,2) Valor del descuento (% o $) fecha_inicio DATE Inicio de vigencia fecha_fin DATE

----


# Parisina, Tienda de Telas y Costuras 🧵👗 

Prompt Mejorado Plan de Implementación, adaptado a Firebase Studio. 
He revisado y optimizado tu propuesta inicial. A continuación, te presento un **Plan de Implementación Profesional, Estructurado y Validado**, diseñado específicamente para el desarrollo de **Parisina. Tienda de Telas y Costuras**. Cumple estrictamente con tu requerimiento: **cero código de implementación**, solo arquitectura, requerimientos, dependencias y flujo de trabajo paso a paso.

---

## 🌐 Fase 0: Entorno, Herramientas y Aclaración Técnica
| Componente | Recomendación Profesional | Justificación |
|---|---|---|
| **IDE Principal** | VS Code + Flutter/Dart Extensions | Ligero, soporte nativo de LSP, depuración multiplataforma, integración con Firebase CLI |
| **Firebase "Studio"** | Firebase Console (Web) + Firebase Emulator Suite | No existe un producto oficial llamado "Firebase Studio". El flujo estándar es: consola web para configuración de Auth/Firestore/Hosting + CLI local para emulación y despliegue. Si prefieres trabajar 100% en navegador, puedes usar **Project IDX** (IDE de Google en la nube con Firebase integrado). |
| **Control de Versiones** | Git + GitHub/GitLab | Ramas: `main` (producción), `develop` (integración), `feature/*` (módulos) |
| **Validación UI/UX** | Figma / Penpot | Prototipado interactivo antes de maquetar |
| **Verificación Base** | `flutter doctor -v` + `firebase login` | Garantiza compatibilidad de SDK, emuladores y autenticación de consola |

---

## 🎨 Fase 1: Sistema de Diseño UI/UX (Paleta Elegante & Textiles)
Se ha refinado tu paleta base asignando **subtonos armoniosos, WCAG 2.1 AA compliant y coherentes con la identidad de una marca de telas y costura** (elegancia, precisión, calidez).

| Elemento | Color | HEX | Uso UX/UI |
|---|---|---|---|
| Fondo Principal | Blanco Puro | `#FFFFFF` | Lienzo base, máxima legibilidad |
| AppBar | Rojo Cardenal | `#C41E3A` | Identidad visual, profesional sin ser agresivo |
| Iconos AppBar | Blanco | `#FFFFFF` | Contraste óptimo sobre rojo |
| Footer | Negro Mate | `#121212` | Reduce fatiga visual vs `#000000` |
| Texto Footer | Blanco Suave | `#F2F2F2` | Legibilidad en fondos oscuros |
| Gris Estructural (secciones) | Gris Perla | `#F5F5F7` | Separación de bloques sin bordes duros |
| Gris Texto Secundario | Grafito | `#4A4A4A` | Descripciones, metadatos, placeholders |
| Amarillo Acento (promociones) | Oro Textil | `#D4AF37` | Badges, descuentos, hilos decorativos UI |
| Rojo CTA/Interactivo | Rojo Ladrillo | `#B71C1C` | Botones primarios, estados activos, alertas |
| Blanco Detalle/Elevación | Nieve | `#FAFAFA` | Cards, sombras suaves (`boxShadow` 4% opacidad) |

**Tipografía Sugerida:**
- Títulos/Encabezados: `Montserrat` (pesos 600-700) → elegancia geométrica
- Cuerpo/UI: `Inter` (pesos 400-500) → legibilidad técnica en móvil/web
- Escala: `H1: 28`, `H2: 22`, `Body: 16`, `Caption: 13`, `Button: 15`

**Componentes Reutilizables Base:**
`CustomAppBar`, `TextileFooter`, `PrimaryButton`, `InputField`, `ProductCard`, `ShimmerLoader`, `EmptyState`, `Badge`, `FilterChip`, `QuantitySelector`, `CheckoutSummaryCard`

---

## 🗃️ Fase 2: Arquitectura de Datos (SQL → Firestore NoSQL)
Firestore no soporta `JOINs`. Se aplicará **denormalización controlada + referencias documentales + transacciones** para mantener consistencia sin sacrificar rendimiento.

| Colección Firestore | Origen SQL | Estructura Recomendada | Índices Compuestos |
|---|---|---|---|
| `clients` | CLIENTE | Doc por cliente. `email` indexado único. `loyaltyPoints` numérico. | `email` (asc), `createdAt` (desc) |
| `categories` | CATEGORIA | Doc por categoría. `parentId` (DocumentReference o string), `level`, `isActive` | `parentId` + `isActive` |
| `products` | PRODUCTO + VARIANTE | Doc por producto. `variants` como subcolección o array embebido (si <20 por producto). `categoryId` (ref). `basePrice`, `cost`, `images[]` | `categoryId` + `isActive` + `createdAt` |
| `inventory` | INVENTARIO | Doc por `variantId_sucursalId` (ID compuesto). `quantity`, `minThreshold`, `lastUpdated`. Actualizado vía `runTransaction` | `variantId`, `quantity` (para alertas) |
| `orders` | VENTA + DETALLE_VENTA | Doc por orden. `items[]` embebido (id_variante, qty, price, discount, total). Evita lecturas múltiples. `status`, `paymentMethod`, `total` | `clientId` + `createdAt`, `status` |
| `stores` | SUCURSAL | Doc por sucursal. `type`, `isActive`, `geoPoint` (opcional para mapa) | `type` + `isActive` |
| `employees` | EMPLEADO | Doc por empleado. `storeId` (ref), `role`, `isActive`. Acceso restringido por reglas | `storeId` + `role` |
| `suppliers` | PROVEEDOR | Doc por proveedor. Campos planos. `isActive` | `country` + `isActive` |
| `returns` | DEVOLUCION | Doc por devolución. `orderId` (ref), `variantId`, `resolution`, `status`, `refundAmount` | `orderId` + `status` |
| `promotions` | PROMOCION | Doc por campaña. `type` (`percentage`, `fixed`, `bxgy`), `value`, `startDate`, `endDate`, `applicableCategories[]` | `startDate` + `endDate` + `isActive` |

**Reglas de Seguridad (Concepto):**
- Lectura pública: `products`, `categories`, `stores`, `promotions` (si activas)
- Escritura protegida: `clients` (solo `request.auth.uid == resource.data.id`), `orders` (transacciones con validación de stock), `returns` (solo auth + validación de orden)
- Validación de tipos y rangos en reglas para prevenir corrupción de datos

---

## 📦 Fase 3: Dependencias Curadas (`pubspec.yaml`)
Lista profesional con propósito claro. Se recomienda fijar versiones compatibles con tu canal estable de Flutter y usar `flutter pub get` con resolución estricta.

| Paquete | Versión Base | Propósito |
|---|---|---|
| `firebase_core` | `^latest` | Inicialización y configuración base de Firebase |
| `firebase_auth` | `^latest` | Autenticación email/password, sesiones, recuperación |
| `cloud_firestore` | `^latest` | CRUD, streams, transacciones, persistencia offline |
| `firebase_storage` | `^latest` | (Opcional) Imágenes de perfil, catálogos dinámicos |
| `firebase_crashlytics` | `^latest` | Reporte silencioso de errores en producción |
| `provider` | `^latest` | Gestión de estado escalable (según tu requerimiento) |
| `go_router` | `^latest` | Navegación declarativa, guards de autenticación, deep links |
| `cached_network_image` | `^latest` | Carga asíncrona, cacheo y fallback de imágenes de productos |
| `flutter_svg` | `^latest` | Renderizado de iconos y logotipos vectoriales |
| `shimmer` | `^latest` | Indicadores de carga elegantes (esqueletos UI) |
| `intl` | `^latest` | Formateo de moneda, fechas, números por locale |
| `google_fonts` | `^latest` | Integración de `Montserrat` + `Inter` |
| `flutter_form_builder` | `^latest` | Construcción y validación de formularios complejos |
| `email_validator` | `^latest` | Validación estricta de correos en registro |
| `uuid` | `^latest` | Generación de IDs locales para carrito offline |
| `equatable` | `^latest` | Comparación eficiente de modelos y estados |
| `shared_preferences` | `^latest` | Persistencia ligera de carrito y preferencias locales |

**Nota de Gestión:** Mantén `pubspec.lock` bajo control de versiones. Usa `dependency_overrides` solo en conflictos de resolución transitoria.

Aquí tienes la sección `dependencies` y `dev_dependencies` lista para tu `pubspec.yaml`, curada, categorizada y alineada con estándares profesionales de Flutter + Firebase (2025/2026). Incluye solo la configuración de dependencias, sin lógica de aplicación.

```yaml
name: parisina_app
description: Aplicación multiplataforma para Parisina. Tienda de Telas y Costuras.
publish_to: 'none'
version: 1.0.0+1

environment:
  sdk: '>=3.5.0 <4.0.0'

dependencies:
  flutter:
    sdk: flutter
  flutter_localizations:
    sdk: flutter

  # 🔥 Firebase (Core & Servicios)
  firebase_core: ^3.0.0
  firebase_auth: ^5.0.0
  cloud_firestore: ^5.0.0
  firebase_storage: ^12.0.0
  firebase_analytics: ^11.0.0
  firebase_crashlytics: ^4.0.0

  # 🔄 Estado y Navegación
  provider: ^6.1.2
  go_router: ^14.0.0

  # 🎨 UI/UX y Componentes Visuales
  cached_network_image: ^3.3.1
  flutter_svg: ^2.0.10+1
  shimmer: ^3.0.0
  google_fonts: ^6.2.1
  intl: ^0.19.0

  # 📝 Formularios y Validación
  flutter_form_builder: ^9.3.0
  email_validator: ^3.0.0
  formz: ^0.7.0

  # 🛠️ Utilidades y Persistencia Ligera
  uuid: ^4.4.0
  equatable: ^2.0.5
  shared_preferences: ^2.2.3
  collection: ^1.18.0

dev_dependencies:
  flutter_test:
    sdk: flutter
  flutter_lints: ^4.0.0
  mocktail: ^1.0.4
  build_runner: ^2.4.11
  flutter_launcher_icons: ^0.13.1
  flutter_native_splash: ^2.4.1

flutter:
  uses-material-design: true
  assets:
    - assets/images/
    - assets/icons/
    - assets/fonts/
```



---

## 📁 Fase 4: Estructura del Proyecto (Feature-First + Capas Lógicas)
```
parisina_app/
├── android/ ios/ web/              # Configuraciones nativas y manifiestos
├── assets/
│   ├── images/                     # Logos, placeholders, texturas textiles
│   ├── icons/                      # SVGs de navegación y categorías
│   └── fonts/                      # (Opcional si se usan locales)
├── lib/
│   ├── main.dart                   # Punto de entrada, init Firebase, MultiProvider, go_router
│   └── src/
│       ├── core/
│       │   ├── constants/          # Rutas, keys, límites, strings, monedas
│       │   ├── theme/              # ThemeData, paleta, tipografía, componentes globales
│       │   ├── utils/              # Validadores, formateadores, helpers de fecha/precio
│       │   ├── services/           # Firebase init, logging, analytics, emuladores
│       │   └── router/             # go_router config, guards, redirects
│       ├── features/
│       │   ├── auth/               # models, providers, screens, widgets, services
│       │   ├── catalog/            # models, providers, screens, widgets, services
│       │   ├── cart/               # models, providers, screens, widgets
│       │   ├── checkout/           # models, providers, screens, widgets
│       │   ├── orders/             # models, providers, screens, widgets
│       │   └── profile/            # models, providers, screens, widgets
│       └── shared/
│           ├── models/             # Entidades transversales (CartItem, Address, etc.)
│           ├── widgets/            # Botones, inputs, cards, footer, loaders reutilizables
│           └── guards/             # Interceptors de ruta, permisos, validación de sesión
├── test/                           # Unit, widget, integration tests
├── pubspec.yaml                    # Manifiesto de dependencias y assets
└── firebase.json                   # Config de hosting/emuladores (si aplica)
```
**Principio de Organización:** Cada `feature/` contiene su propio dominio (modelos → estado → UI → servicios). `shared/` aloja componentes reutilizables. `core/` centraliza configuración y utilidades.

---

## 🧭 Fase 5: Hoja de Ruta Paso a Paso (Sin Código)

| Fase | Actividad | Entregable | Criterio de Validación |
|---|---|---|---|
| **1. Setup** | Crear proyecto Flutter multiplataforma. Configurar Firebase Console (Auth, Firestore, Analytics). Descargar credenciales. Inicializar `pubspec.yaml`. | Entorno funcional, `flutter doctor` limpio, Firebase conectado | App compila en Android/iOS/Web. Firebase Console muestra app registrada |
| **2. Design System** | Implementar `ThemeData`, tipografía, paleta exacta. Crear widgets base (`AppBar`, `Footer`, `Buttons`, `Inputs`). Configurar `go_router`. | Prototipo estático navegable | Contraste WCAG ≥ 4.5:1. Responsividad en 3 breakpoints. Navegación sin errores |
| **3. Auth Module** | Diseñar pantallas Login/Registro/Recuperación. Implementar `AuthProvider`. Configurar guards de ruta. Validar formularios. | Flujo completo de autenticación | Verificación de email funciona. Sesión persistente. Redirecciones correctas |
| **4. Data & State** | Mapear colecciones Firestore. Crear `CatalogProvider`, `CartProvider`, `OrderProvider`. Configurar streams y transacciones. | Estado reactivo conectado a datos | Lectura/escritura en Firestore segura. Offline básico funcional. Estados UI sincronizados |
| **5. Catalog UI** | Grid de productos, filtros por categoría/precio, búsqueda con debounce, detalle con selector de variante (talla/color). | Catálogo interactivo | Imágenes cacheadas. Filtros responden <500ms. Detalle muestra stock y precio dinámico |
| **6. Cart & Checkout** | Lógica de carrito (agregar/quitar/cantidad). Cálculo de subtotal/impuesto/envío. Pantalla de checkout con resumen y método de pago. | Flujo de compra completo | Validación de stock en tiempo real. Transacción atómica en Firestore. Carrito se limpia post-compra |
| **7. Orders & Profile** | Historial de pedidos con estados. Edición de datos personales. Cambio de contraseña. Cierre de sesión. | Panel de usuario funcional | Datos se actualizan en Firestore. Pedidos reflejan cambios de estado. Sesión revocable |
| **8. QA & Optimización** | Tests unitarios (modelos, validadores), tests widget (UI), tests integración (flujo completo). Optimizar rebuilds, tree-shaking, build release. | App estable y optimizada | 0 warnings críticos. Cobertura ≥70% en lógica de negocio. Build release <15MB (móvil) |
| **9. Pre-Deploy** | Configurar Firebase App Distribution. Generar AAB/APK/Web build. Documentar reglas de seguridad y arquitectura. | Paquetes listos para distribución | Builds verificados en emuladores/dispositivos reales. Reglas de Firestore publicadas |

---

## ✅ Checklist de Aprobación Pre-Código
- [ ] Paleta UI/UX validada visualmente y accesible
- [ ] Mapeo SQL → Firestore documentado y revisado
- [ ] Estructura de carpetas creada y vacía lista para módulos
- [ ] `pubspec.yaml` con dependencias resueltas y sin conflictos
- [ ] Proveedores diseñados (estados, flujos, responsabilidades)
- [ ] Navegación declarativa configurada con guards de autenticación
- [ ] Reglas de seguridad de Firestore redactadas (conceptualmente)
- [ ] Estrategia de pruebas definida por capa
- [ ] Entorno de emulación (Firebase + Flutter) operativo

---

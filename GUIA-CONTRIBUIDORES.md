# Guía para Contribuidores — BDF WorkAdventure

> Guía paso a paso para crear assets visuales, agregarlos al mapa y subir tu contribución al repositorio.
> Dirigida a personas sin experiencia previa en pixel art, Tiled o GitHub.

---

## Índice

1. [Instalar las herramientas](#1-instalar-las-herramientas)
2. [Clonar el repositorio](#2-clonar-el-repositorio)
3. [Generar imágenes con IA (Nano Banana / Prompt base)](#3-generar-imágenes-con-ia)
4. [Editar y preparar imágenes con Aseprite](#4-editar-y-preparar-imágenes-con-aseprite)
5. [Agregar el tileset en Tiled](#5-agregar-el-tileset-en-tiled)
6. [Subir tu contribución a GitHub](#6-subir-tu-contribución-a-github)
7. [Referencia rápida de comandos](#7-referencia-rápida-de-comandos)

---

## 1. Instalar las herramientas

Necesitas tres programas: **Git**, **Tiled** y **Aseprite**.

---

### Git + GitHub Desktop

Git es el sistema que guarda y sincroniza los cambios del proyecto con GitHub.

#### Windows
1. Descarga Git desde: https://git-scm.com/download/win
2. Ejecuta el instalador. En todas las pantallas deja las opciones por defecto y presiona **Next**.
3. Al finalizar abre **Git Bash** (aparece en el menú inicio).
4. Verifica con: `git --version`

#### macOS
1. Abre la Terminal (cmd + espacio → escribe "Terminal").
2. Ejecuta: `xcode-select --install`
3. Esto instala Git automáticamente. Verifica: `git --version`

#### Linux (Ubuntu / Debian)
```bash
sudo apt update && sudo apt install git -y
git --version
```

#### Configurar tu identidad (todos los sistemas)
Después de instalar Git ejecuta estos dos comandos con **tu nombre y correo**:
```bash
git config --global user.name "TuNombre"
git config --global user.email "tucorreo@ejemplo.com"
```

---

### Tiled — Editor de mapas

Tiled es el editor donde se construye el mapa visual del mundo BDF.

#### Windows
1. Ve a: https://www.mapeditor.org/
2. Haz clic en **Download** y descarga el instalador `.exe`.
3. Ejecuta el instalador y sigue los pasos. Tiled quedará en el menú inicio.

#### macOS
1. Ve a: https://www.mapeditor.org/
2. Descarga el archivo `.dmg`.
3. Ábrelo, arrastra Tiled a la carpeta **Aplicaciones**.

#### Linux (Ubuntu / Debian)
```bash
sudo apt install tiled
```
O descarga el AppImage desde https://www.mapeditor.org/ y dale permisos:
```bash
chmod +x Tiled-*.AppImage
./Tiled-*.AppImage
```

---

### Aseprite — Editor de pixel art

Aseprite es la herramienta principal para crear y editar los tilesets en pixel art.

> Aseprite tiene un costo de ~$20 USD en Steam o en su sitio oficial. Si prefieres una alternativa gratuita, usa **Libresprite** (fork gratuito de Aseprite).

#### Aseprite (de pago — recomendado)
- Steam: https://store.steampowered.com/app/431730/Aseprite/
- Sitio oficial: https://www.aseprite.org/

#### Libresprite (gratuito)
- Descarga desde: https://libresprite.github.io/
- Disponible para Windows, macOS y Linux.

#### Instalación en Windows / macOS
Descarga el instalador desde cualquiera de los dos sitios y ejecútalo normalmente.

#### Instalación en Linux
```bash
# Libresprite via AppImage
chmod +x LibreSprite-*.AppImage
./LibreSprite-*.AppImage
```

---

## 2. Clonar el repositorio

"Clonar" significa descargar una copia del proyecto a tu computadora para poder editarlo.

### Windows (Git Bash) / macOS / Linux (Terminal)

```bash
# Navega al escritorio (o a la carpeta donde quieras el proyecto)
cd ~/Desktop

# Clona el repositorio
git clone https://github.com/SOLEvoltaje/BDF-WA.git

# Entra a la carpeta del proyecto
cd BDF-WA
```

Ahora tendrás la carpeta `BDF-WA` con todo el proyecto.

**Estructura de carpetas importante:**
```
BDF-WA/
├── office.tmj          ← Mapa principal (abrir en Tiled)
├── bdf.tmx             ← Mapa experimental
├── tilesets/           ← AQUÍ van todas las imágenes PNG
│   ├── arboles.png
│   ├── carteles.png
│   ├── domo.png
│   └── ...
├── src/
│   └── main.ts         ← Script del mundo
└── public/             ← Archivos estáticos
```

> **Regla de oro:** Todos los PNG de tilesets van dentro de la carpeta `tilesets/`. Nunca pongas rutas absolutas como `C:/Users/...` en los archivos de mapa.

---

## 3. Generar imágenes con IA

Puedes usar herramientas de IA para generar la base de tus assets y luego refinarlos en Aseprite.

---

### Herramienta recomendada: Nano Banana

Nano Banana es una herramienta online de generación de pixel art con IA, ideal para tilesets de RPG y juegos top-down.

1. Ve a: https://labs.google/flow/about (Entra con tu cuenta de google)
2. Crea una cuenta gratuita.
3. En el campo de prompt usa la plantilla de abajo.
4. Selecciona resolución de salida: **512×512 px** o múltiplo de 32.
5. Descarga el PNG resultante.

---

### Otras herramientas de IA compatibles

| Herramienta | Tipo | Costo | Link |
|---|---|---|---|
| Flow | Online | Freemium | labs.google/flow |
| Itch.io AI Pixel | Online | Gratis | itch.io |
| Leonardo.ai | Online | Freemium | leonardo.ai |
| Stable Diffusion | Local | Gratis | github.com/AUTOMATIC1111 |
| Midjourney | Discord | Pago | midjourney.com |

---

### Prompt base para el estilo BDF

Usa este prompt como punto de partida. Reemplaza `[OBJETO]` con lo que quieres crear.

```
16-bit pixel art, top-down RPG view, [OBJETO], 
tilesheet sprite sheet format, 32x32 pixel tiles, 
warm earthy tones, tropical caribbean style, 
wood textures, natural materials, 
transparent background PNG, 
clean pixel art outline, no anti-aliasing, 
style similar to Stardew Valley and RPG Maker MV
```

#### Prompts listos para usar según categoría

**Edificios y estructuras:**
```
16-bit pixel art, top-down RPG view, 
indigenous round hut with thatched palm roof, 
geodesic dome wood structure, tropical architecture,
tilesheet format, 32x32 pixel tiles,
warm orange and brown tones, wood texture,
transparent background PNG, no anti-aliasing,
Stardew Valley style
```

**Naturaleza y vegetación:**
```
16-bit pixel art, top-down view,
tropical tree tileset, palm trees, banana plant, 
flowering bushes, tropical grass,
tilesheet format, 32x32 pixel tiles,
vibrant greens and yellows, lush foliage,
transparent background PNG, no anti-aliasing,
RPG Maker style
```

**Mobiliario y objetos interiores:**
```
16-bit pixel art, top-down view,
workshop furniture tileset, wooden workbench,
toolbox, shelves, chairs, tables,
crafting tools, cozy interior objects,
tilesheet format, 32x32 pixel tiles,
warm brown and cream tones,
transparent background PNG, no anti-aliasing,
Stardew Valley style
```

**Carteles y señalética con identidad BDF:**
```
16-bit pixel art, flat design screen/poster,
colorful tropical tech sign, bright magenta pink background,
teal cyan and yellow accents, bold modern typography,
pixel art frame with decorative border,
512x512 px, no anti-aliasing, clean edges,
style similar to existing BDF brand carteles
```

**Zonas y pisos:**
```
16-bit pixel art, top-down floor tileset,
sandy beach texture, tropical soil, wooden deck,
stone path, grass terrain,
seamlessly tileable 32x32 pixel tiles,
warm earth tones, tropical caribbean palette,
transparent background PNG, Stardew Valley style
```

---

### Paleta de colores del proyecto BDF

Para mantener consistencia visual usa estos colores en tus prompts y en Aseprite:

| Uso | Color | Hex |
|---|---|---|
| Marca principal | Magenta/Rosa | `#E91E8C` |
| Acento 1 | Teal/Cyan | `#00C4B4` |
| Acento 2 | Amarillo | `#FFD600` |
| Acento 3 | Naranja | `#FF6B00` |
| Madera clara | Café claro | `#C8882A` |
| Madera oscura | Café oscuro | `#7A4F1E` |
| Suelo/arena | Arena | `#D4B483` |
| Pasto | Verde | `#5A9E32` |

---

## 4. Editar y preparar imágenes con Aseprite

Una vez generada la imagen con IA, necesitas prepararla correctamente para Tiled.

### Requisitos de los tilesets

- **Formato:** PNG con fondo transparente
- **Tamaño de tile:** 32×32 píxeles
- **Ancho de imagen:** múltiplo de 32 (128, 256, 512 px)
- **Sin espaciado** entre tiles (margin = 0, spacing = 0)
- **Nombre de archivo:** sin espacios ni caracteres especiales (usa guion bajo: `mi_tileset.png`)

---

### Paso a paso en Aseprite

#### Abrir la imagen generada por IA

1. Abre Aseprite.
2. `File` → `Open` → selecciona tu PNG.
3. Si la imagen no tiene fondo transparente: `Edit` → `Replace Color` → selecciona el color de fondo → reemplaza con transparente.

#### Ajustar el canvas al tamaño correcto

1. Ve a `Sprite` → `Sprite Size`.
2. Asegúrate que el ancho y alto son **múltiplos de 32** (ejemplo: 256×256, 512×512).
3. Si necesitas recortar: `Sprite` → `Crop Canvas`.

#### Activar la grilla de 32×32

1. `View` → `Show Grid` (atajo: `Ctrl+Shift+G` en Windows, `Cmd+Shift+G` en Mac).
2. Para configurar el tamaño: `Edit` → `Preferences` → `Grid` → pon **32×32**.
3. La grilla te muestra exactamente los límites de cada tile.

#### Limpiar píxeles sueltos y ruido

1. Usa la herramienta **Eraser** (`E`) para limpiar píxeles sueltos fuera del área útil.
2. Zoom in con `+` para ver los detalles.
3. Para verificar la transparencia: `View` → `Show Extras` → activa el fondo de tablero de ajedrez.

#### Exportar como PNG final

1. `File` → `Export As`.
2. Selecciona formato **PNG**.
3. Asegúrate que **"Export for preview"** está desmarcado.
4. Guarda **directamente en la carpeta `tilesets/`** del proyecto.

```
Ejemplo de ruta correcta:
C:\Users\danvegamo\Desktop\BDF-WA\tilesets\mi_nuevo_tileset.png
```

---

## 5. Agregar el tileset en Tiled

### Abrir el proyecto en Tiled

1. Abre Tiled.
2. `File` → `Open` → navega a `BDF-WA` → abre `BDF.tiled-project`.
3. En el panel de proyecto (izquierda) verás todos los archivos.
4. Haz doble clic en `office.tmj` para abrir el mapa principal.

### Agregar el nuevo tileset al mapa

1. En el panel **Tilesets** (parte inferior derecha), haz clic en el ícono **"+"** (New Tileset).
2. Aparece el diálogo "New Tileset":
   - **Name:** nombre descriptivo (ej: `mi_estructura`)
   - **Type:** `Based on Tileset Image`
   - **Image:** haz clic en `Browse` → selecciona tu PNG de `tilesets/`
   - **Tile width:** `32`
   - **Tile height:** `32`
   - **Margin:** `0`
   - **Spacing:** `0`
3. Haz clic en **OK**.

> **IMPORTANTE:** Cuando Tiled te pregunte dónde guardar el tileset, guárdalo **dentro de la carpeta `tilesets/`** con extensión `.tsx`.

### Verificar que la ruta es relativa (sin errores)

Después de agregar el tileset, verifica en el panel Tilesets que la ruta muestre:
```
tilesets/mi_nuevo_tileset.png   ← CORRECTO
```
Y NO:
```
C:/Users/TuNombre/Desktop/...   ← INCORRECTO (ruta absoluta)
```

Si ves una ruta absoluta: haz clic derecho en el tileset → `Tileset Properties` → cambia la imagen a la ruta relativa.

### Usar los tiles en el mapa

1. Selecciona el tileset en el panel inferior.
2. Haz clic en un tile para seleccionarlo.
3. Selecciona la capa donde quieres pintar (panel **Layers** a la derecha).
4. Haz clic en el mapa para colocar el tile.
5. Guarda: `Ctrl+S`.

---

## 6. Subir tu contribución a GitHub

### Primera vez: configurar acceso

Si es la primera vez que subes a este repositorio, GitHub te pedirá autenticación.

**En Windows:** se abre automáticamente una ventana del navegador para iniciar sesión en GitHub.

**En macOS / Linux:** usa un token de acceso personal:
1. Ve a GitHub → Settings → Developer settings → Personal access tokens → Generate new token.
2. Dale permiso `repo`.
3. Copia el token y úsalo como contraseña cuando Git te la pida.

---

### Flujo de trabajo paso a paso

Abre Git Bash (Windows) o Terminal (macOS/Linux) y navega al proyecto:

```bash
cd ~/Desktop/BDF-WA
```

#### Paso 1 — Verificar qué archivos cambiaste

```bash
git status
```

Verás algo como:
```
modified:   office.tmj
Untracked files:
    tilesets/mi_nuevo_tileset.png
    tilesets/mi_nuevo_tileset.tsx
```

#### Paso 2 — Traer los últimos cambios del equipo

Siempre haz esto antes de subir para evitar conflictos:

```bash
git pull origin master
```

#### Paso 3 — Agregar tus archivos al commit

```bash
# Agregar archivos específicos (recomendado)
git add tilesets/mi_nuevo_tileset.png
git add tilesets/mi_nuevo_tileset.tsx
git add office.tmj

# O agregar todos los cambios de una vez
git add .
```

#### Paso 4 — Crear el commit con un mensaje descriptivo

```bash
git commit -m "feat: agregar tileset de [descripción de lo que agregaste]"
```

Ejemplos de buenos mensajes:
```bash
git commit -m "feat: agregar tileset de palmeras tropicales"
git commit -m "feat: agregar estructura de cabaña circular"
git commit -m "fix: corregir ruta de imagen en tileset arboles"
```

#### Paso 5 — Subir a GitHub

```bash
git push origin master
```

Si todo salió bien verás:
```
To https://github.com/SOLEvoltaje/BDF-WA.git
   abc1234..def5678  master -> master
```

---

### Qué hacer si hay conflictos

Si al hacer `git pull` aparece un mensaje de conflicto:

```bash
# Ver qué archivos tienen conflicto
git status

# Para archivos de mapa TMJ/TMX, acepta la versión del servidor
git checkout --theirs office.tmj
git add office.tmj
git commit -m "merge: resolver conflicto en office.tmj"
```

> Si tienes dudas, pide ayuda en el canal del equipo antes de hacer `git push`.

---

## 7. Referencia rápida de comandos

### Git

| Comando | Qué hace |
|---|---|
| `git clone [URL]` | Descarga el proyecto por primera vez |
| `git pull origin master` | Trae los últimos cambios del equipo |
| `git status` | Muestra qué archivos cambiaron |
| `git add [archivo]` | Prepara un archivo para el commit |
| `git add .` | Prepara todos los archivos cambiados |
| `git commit -m "mensaje"` | Guarda los cambios con descripción |
| `git push origin master` | Sube los cambios a GitHub |
| `git log --oneline` | Ve el historial de commits |

### Tamaños de canvas en Aseprite

| Tiles en la imagen | Tamaño del PNG |
|---|---|
| 4×4 tiles | 128×128 px |
| 8×8 tiles | 256×256 px |
| 16×16 tiles | 512×512 px |
| 32×32 tiles | 1024×1024 px |

### Checklist antes de subir

- [ ] El PNG está en la carpeta `tilesets/`
- [ ] El nombre del archivo no tiene espacios
- [ ] El tamaño es múltiplo de 32
- [ ] El fondo del PNG es transparente
- [ ] En Tiled la ruta del tileset empieza con `tilesets/` (no con `C:/...`)
- [ ] Hice `git pull` antes de hacer `git push`
- [ ] El mensaje del commit describe qué agregué

---

> **¿Tienes dudas?** Contacta al equipo en el canal de Discord o abre un Issue en https://github.com/SOLEvoltaje/BDF-WA/issues

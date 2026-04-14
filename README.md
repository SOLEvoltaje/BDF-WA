# 🗺️ Biblioteca del Futuro — SOLE Colombia

<a href="https://solecolombia.org/" target="blank"><img src="https://solecolombia.org/wp-content/uploads/2020/09/Logo-SOLE-Colombia.png" alt="SOLE Colombia" width="200"/></a>

Bienvenido a la **Biblioteca del Futuro (BDF)**, un entorno virtual creado por **SOLE Colombia** para explorar y prototipar **Otros Internets Posibles**. 

Este espacio es un "hub" comunitario donde investigamos cómo las comunidades pueden apropiarse de la tecnología para contar sus historias, preservar su sabiduría y resolver preguntas compartidas.

---

## 🌟 Nuestra Visión: Otros Internets Posibles

En SOLE Colombia, creemos que el internet es un sistema generativo híbrido donde la autonomía, la equidad y la imaginación colectiva son protagonistas.

A través de los **SOLE Labs**, transformamos espacios conectados en centros de conocimiento:
- **Fomentamos la curiosidad:** El aprendizaje nace de preguntas grandes.
- **Valoramos la sabiduría local:** El poder inherente de cada comunidad.
- **Redefinimos la conectividad:** Redes que sirven a las personas, no al revés.

---

## 🛠️ Guía Rápida para Contribuidores

Si quieres agregar objetos, edificios o nuevas zonas al mapa, hemos preparado una guía detallada paso a paso:

👉 **[LEER GUÍA COMPLETA DE CONTRIBUIDORES](./GUIA-CONTRIBUIDORES.md)**

### Resumen de pasos:
1. **Instala las herramientas:** Git, Tiled y Aseprite (o Libresprite).
2. **Clona este repositorio:** `git clone https://github.com/SOLEvoltaje/BDF-WA.git`
3. **Crea tus assets:** Usa IA (Nano Banana) o dibuja en pixel art (32x32px).
4. **Agrega al mapa:** Abre `office.tmj` en Tiled y añade tus tilesets en la carpeta `tilesets/`.
5. **Sube tus cambios:** Usa los comandos de Git para compartir tu trabajo.

---

## 🚀 Cómo empezar (Desarrolladores)

### Instalación
Asegúrate de tener [Node.js](https://nodejs.org/) instalado. En la carpeta del proyecto, ejecuta:

```bash
npm install
```

### Probar el mapa localmente
Para ver tus cambios en tiempo real en el navegador:

```bash
npm run dev
```

### Subir tus cambios al Repositorio
Cuando hayas terminado de editar el mapa en Tiled:

```bash
# 1. Trae los últimos cambios del equipo
git pull origin master

# 2. Agrega tus archivos nuevos o modificados
git add .

# 3. Guarda tus cambios con un mensaje descriptivo
git commit -m "feat: agregada nueva zona de lectura en el domo"

# 4. Sube al repositorio
git push origin master
```

---

## 🗂️ Estructura del Proyecto

- **`office.tmj`**: Mapa principal del mundo BDF.
- **`tilesets/`**: AQUÍ van todas las imágenes PNG y archivos `.tsx`.
- **`src/`**: Scripts y lógica del mundo.
- **`public/`**: Archivos estáticos (imágenes, PDFs, audios).

---

## 📜 Licencias
Este proyecto utiliza múltiples licencias para proteger el código, el mapa y los assets. Consulta los archivos `LICENSE.code`, `LICENSE.map` y `LICENSE.assets` para más detalles.

---

¿Tienes dudas? Únete a nuestro Discord o abre un [Issue](https://github.com/SOLEvoltaje/BDF-WA/issues) aquí en GitHub.

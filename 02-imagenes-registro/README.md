# Sesión 2 · Creación y gestión de imágenes: despliegue local y en la nube

El salto de consumir imágenes a **producirlas**: escribes tu primer Dockerfile,
construyes tu imagen, la versionas, la publicas en Docker Hub y la corres desde
otra máquina. Cierras endureciéndola: contenedor sin root.

## Objetivos

- **Escribir** un Dockerfile: la receta en texto plano que define tu imagen.
- **Construir** imágenes con `docker build`, entendiendo capas, caché y tags.
- **Publicar** tu imagen en Docker Hub y ejecutarla desde cualquier otra máquina.
- 🔒 **Endurecer** tu imagen: usuario no-root, base mínima y cero secretos adentro.

## Contenido

```
02-imagenes-registro/
├── guia-lab.md                 # laboratorio de la sesión (participantes)
└── diapositivas/               # deck de teoría (PPTX + PDF, 17 láminas) + guía en PDF
```

El deck incluye: anatomía del Dockerfile (las 6 instrucciones), ejemplo completo
comentado, capas y caché, tags y el peligro de `:latest`, el flujo
build → tag → login → push, Docker Hub vs registro privado (ACR), y los 3 hábitos
de seguridad de imágenes.

## Laboratorio

Ver [`guia-lab.md`](guia-lab.md). Tres partes (1 hora) en **Play with Docker**:

1. **Construye tu imagen** — index.html propio + Dockerfile + build, y el caché en acción.
2. **Publícala en Docker Hub** — login, tag, push, y la prueba reina: correrla en
   una instancia nueva.
3. **🔒 Endurécela** — whoami root vs no-root con la variante unprivileged, y
   `docker history`: las capas no mienten.

## Requisitos

Tu cuenta de **Docker Hub** con usuario y contraseña a la mano (hoy haces `docker login`).

**Entregable de la S2:** la URL pública de tu imagen en Docker Hub + captura del
pull en la instancia nueva + bitácora.

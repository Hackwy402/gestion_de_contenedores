# Gestión de Contenedores en Entornos de Nube Híbrida · Universidad Ean (101-EAN)

**De «en mi máquina sí funciona» a desplegar la misma aplicación en local y en la
nube** — curso teórico-práctico de contenedores con Docker, orientado a entornos de
nube híbrida. Cada semana se libera una sesión bajo su carpeta.

> **Metodología:** teórico-práctica — cada sesión combina teoría aplicada (~50 min)
> con laboratorio guiado (~60 min) y deja una evidencia práctica.
> **Plataforma de práctica:** [Play with Docker](https://labs.play-with-docker.com)
> (solo necesitas una cuenta gratuita de [Docker Hub](https://hub.docker.com)).
> **Nube del curso:** Microsoft Azure.
> 🔒 **Eje transversal:** buenas prácticas de seguridad de contenedores en las 5 sesiones.

## Índice de sesiones

| # | Carpeta | Sesión | Entregable | Estado |
|---|---|---|---|---|
| 01 | [`01-fundamentos-hibrida/`](01-fundamentos-hibrida/) | Fundamentos de contenedores y arquitectura de nube híbrida | Primer contenedor + bitácora | ✅ Disponible |
| 02 | [`02-imagenes-registro/`](02-imagenes-registro/) | Creación y gestión de imágenes: despliegue local y en la nube | Imagen propia publicada en Docker Hub | ✅ Disponible |
| 03 | [`03-redes-conectividad/`](03-redes-conectividad/) | Conectividad y redes entre entornos híbridos | App multi-contenedor en red aislada | ✅ Disponible |
| 04 | [`04-persistencia-respaldo/`](04-persistencia-respaldo/) | Persistencia de datos: almacenamiento y respaldo | Volumen persistente + respaldo restaurado · 🚀 inicia el [mini-proyecto](mini-proyecto.md) | ✅ Disponible |
| 05 | `05-portabilidad-orquestacion/` | Portabilidad, migración e introducción a la orquestación | Mini-proyecto: app migrada local → nube + demo Kubernetes | 🔜 |

## Empezar (3 pasos)

1. Crea tu cuenta gratuita en [hub.docker.com](https://hub.docker.com).
2. Entra a [labs.play-with-docker.com](https://labs.play-with-docker.com) → Login → Start → **ADD NEW INSTANCE**.
3. Abre la [guía de la Sesión 1](01-fundamentos-hibrida/guia-lab.md) y sigue los pasos.

## Estructura de cada sesión

```
0X-nombre-sesion/
├── README.md            # resumen, objetivos y contenido de la sesión
├── guia-lab.md          # laboratorio paso a paso (participantes)
└── diapositivas/        # deck de teoría (PPTX + PDF) y guía en PDF
```

---

Universidad Ean · Educación Continua · Colpensiones
Docente: Jawy Andrés Romero Pinto
Material educativo. Los laboratorios usan ambientes desechables e imágenes oficiales.

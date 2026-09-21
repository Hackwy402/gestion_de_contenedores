# Sesión 3 · Conectividad y redes entre entornos híbridos

Tus contenedores dejan de vivir solos: creas redes propias donde los servicios se
encuentran **por nombre**, publicas al exterior solo la puerta necesaria y montas
tu primera aplicación multi-contenedor — un blog WordPress con su MySQL, con la
base de datos invisible para el mundo.

## Objetivos

- **Explicar** cómo se comunican los contenedores: redes, DNS interno y mapeo de puertos.
- **Conectar** varios contenedores en una red propia (resolución por nombre).
- **Publicar** hacia el exterior únicamente los puertos necesarios (`-p`).
- 🔒 **Aislar** los servicios sensibles: la BD accesible para la app, invisible para el mundo.

## Contenido

```
03-redes-conectividad/
├── guia-lab.md                 # laboratorio de la sesión (participantes)
└── diapositivas/               # deck de teoría (PPTX + PDF, 14 láminas) + guía en PDF
```

El deck incluye: el patrón web/API/BD, la red bridge de fábrica y sus límites, redes
definidas por el usuario y su DNS, el diagrama de puertos (la puerta única), el eje
de seguridad de segmentación, la arquitectura del lab, y el mapeo de estos conceptos
a la nube (VNet de Azure / VPC de AWS).

## Laboratorio

Ver [`guia-lab.md`](guia-lab.md). Tres partes (1 hora) en **Play with Docker**:

1. **Redes y DNS** — crea tu red y comprueba el ping por nombre (y su ausencia en bridge).
2. **El blog completo** — MySQL sin puerto + WordPress con `-p`, instalación y primer post.
3. **🔒 El aislamiento** — la BD sin puerta, el contenedor intruso que no la alcanza,
   y la prueba del reemplazo del blog (el gancho hacia la S4).

**Entregable de la S3:** el blog vivo (captura con tu post) + evidencia del
aislamiento + diagrama de tu red.

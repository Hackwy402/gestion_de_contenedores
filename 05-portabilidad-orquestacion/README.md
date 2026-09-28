# Sesión 5 · Portabilidad, migración e introducción a la orquestación (CIERRE)

La sesión de cierre: la app completa del curso se convierte en **UN archivo**
(`docker-compose.yml`), la migración local ↔ nube se vuelve trivial, y llega la
respuesta a "¿quién cuida los contenedores?": **Kubernetes**, visto en vivo
(self-healing, escalado, IP pública en AKS). Y el gran final: **las demos del
[mini-proyecto integrador](../mini-proyecto.md)**. 🚀

## Objetivos

- **Componer** una app multi-contenedor completa con Docker Compose.
- **Migrar** tu app entre entornos con imágenes + compose + respaldo.
- **Explicar** qué resuelve un orquestador y los conceptos base de Kubernetes
  (pod, deployment, service).
- 🔒 **Cerrar el hilo de los secretos**: de env vars a bóvedas gestionadas (Key Vault).

## Contenido

```
05-portabilidad-orquestacion/
├── guia-lab.md                 # laboratorio + guion de la demo final (participantes)
└── diapositivas/               # deck de teoría (PPTX + PDF, 16 láminas) + guía en PDF
```

El deck incluye: el problema del "comando largo", el docker-compose.yml del curso
anotado sesión por sesión, el ciclo up/down, el checklist de migración local→nube,
el límite del host único, orquestación declarativa, los 4 conceptos de Kubernetes
mapeados a lo aprendido, la demo guiada, secretos bien gestionados, el camino
post-curso y el cierre del arco S1→S5.

## Laboratorio

Ver [`guia-lab.md`](guia-lab.md):

1. **Tu primer docker-compose.yml** (20 min) — la app completa en un archivo, y la
   prueba de fuego: `down`/`up` con los datos intactos.
2. **Kubernetes guiado** (15 min) — self-healing y escalado, siguiendo la demo
   (o replicándola en Killercoda).
3. **🚀 Las demos finales** (5 min por equipo) — la app viva, el diagrama y la
   restauración en vivo.

**Entregable de la S5:** tu docker-compose.yml + la demo final del mini-proyecto.

---

Con esta sesión el curso queda completo: **S1 fundamentos → S2 imágenes →
S3 redes → S4 persistencia → S5 portabilidad y orquestación.**
El repositorio queda público como material de consulta. 🐳

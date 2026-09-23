# 🚀 Mini-proyecto integrador · 101-EAN Gestión de Contenedores

**Arranca:** Sesión 4 · **Cierra:** Sesión 5 (demo final) · **Modalidad:** parejas o individual

> Todo lo que aprendiste en el curso, integrado en UNA aplicación tuya, funcionando
> y demostrable: multi-contenedor, en red aislada, con datos persistentes, respaldo
> probado e imagen publicada — y migrada de la práctica local a la nube.

---

## La consigna

Construye y demuestra una **aplicación multi-contenedor** que cumpla TODOS estos criterios:

| # | Criterio | Sesión donde lo aprendiste |
|---|---|---|
| 1 | Al menos 2 contenedores que se comunican **por nombre** en una **red propia** | S3 |
| 2 | El servicio expuesto publica **solo** su puerto de entrada; la BD **sin** `-p` | S3 🔒 |
| 3 | Los datos viven en un **volumen** y sobreviven a la muerte del contenedor | S4 |
| 4 | Un **respaldo restaurado con éxito** (evidencia del ciclo completo) | S4 |
| 5 | Al menos una imagen **propia** (con Dockerfile) publicada en **Docker Hub** | S2 |
| 6 | 🔒 Buenas prácticas: imagen base oficial, tag versionado, sin secretos en la imagen | S1–S2 |

**¿Qué app?** La más simple que cumpla los criterios. Opciones sugeridas:

- **El blog** (WordPress + MySQL) del lab, con una página o tema personalizado
  servido por TU imagen de nginx como tercer contenedor.
- **Tu login-app** (taller S3) + una BD — la página la sirve TU imagen.
- Cualquier app que conozcas (app + BD): lo que se evalúa es la arquitectura
  contenerizada, no el código de la app.

## Las fases

### Fase 1 — se construye entre la S4 y la S5

En **Play with Docker** o tu **VM de Azure** (taller S3):

1. Arma la arquitectura completa (criterios 1-3).
2. Ejecuta el ciclo de respaldo: dump → desastre → restauración (criterio 4).
3. Publica tu imagen propia en Docker Hub (criterio 5).
4. Documenta TODO en tu bitácora: los comandos, un diagrama de la arquitectura
   (redes, contenedores, volúmenes, puertos) y las capturas de cada criterio.

### Fase 2 — en la Sesión 5 (el cierre)

1. **Migra** tu app: si la armaste en Play with Docker, la levantas en tu VM de
   Azure (o viceversa) usando SOLO tus imágenes publicadas y tu respaldo —
   la prueba de portabilidad local ↔ nube del curso.
2. **Demo final de 5 minutos** por equipo:
   - La app viva (mostrar la URL).
   - El diagrama de arquitectura (30 segundos de explicación).
   - **La restauración en vivo**: mata la BD y tráela de vuelta. 😎

## Entregables (al cierre de la S5)

1. **Bitácora del proyecto**: diagrama + comandos + capturas de los 6 criterios.
2. **URL de tu imagen** en Docker Hub.
3. La **demo en vivo** de 5 minutos.

## Rúbrica (100 pts)

| Criterio | Pts |
|---|---|
| Arquitectura multi-contenedor en red propia con DNS por nombre | 20 |
| Exposición mínima (solo la puerta necesaria; BD aislada) 🔒 | 15 |
| Persistencia en volumen demostrada (muerte y resurrección del contenedor) | 15 |
| Respaldo restaurado con éxito (en vivo en la demo) | 20 |
| Imagen propia versionada y publicada en Docker Hub | 15 |
| Bitácora: diagrama claro + comandos reproducibles | 10 |
| Demo: claridad y manejo del tiempo (5 min) | 5 |

**Bonus (+10):** app migrada y corriendo en la VM de Azure con regla NSG propia ·
**Bonus (+5):** imagen endurecida no-root (`whoami` ≠ root).

---

*Dudas durante la semana: canal del curso. La demo es en vivo — ensáyala al menos
una vez completa antes de la S5 (el cronómetro no perdona).*

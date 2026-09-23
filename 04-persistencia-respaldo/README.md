# Sesión 4 · Persistencia de datos: almacenamiento y respaldo

La sesión abre con un experimento cruel: matar la base de datos del blog **con los
posts adentro**. Luego lo arregla para siempre: **volúmenes** (datos fuera del ciclo
de vida del contenedor) y **respaldo con restauración probada** — del desastre total
a la recuperación, cronómetro en mano.

🚀 Además, aquí **arranca el [mini-proyecto integrador](../mini-proyecto.md)**
(cierra en la Sesión 5 con demo en vivo).

## Objetivos

- **Explicar** por qué los contenedores pierden sus datos (la capa de escritura efímera).
- **Persistir** los datos en volúmenes que sobreviven a cualquier contenedor.
- **Respaldar** y restaurar la información — con prueba de restauración.
- 🔒 **Diseñar** una estrategia mínima de respaldo (regla 3-2-1, copia offsite).

## Contenido

```
04-persistencia-respaldo/
├── guia-lab.md                 # laboratorio de la sesión (participantes)
└── diapositivas/               # deck de teoría (PPTX + PDF, 16 láminas) + guía en PDF
```

El deck incluye: la capa de escritura (por qué se pierden los datos), volúmenes y
su diagrama, volumen vs bind mount, el blog inmortal, por qué el volumen NO es
respaldo (host, error humano, ransomware), la regla 3-2-1, el ciclo
respaldo→desastre→restauración, el eje de seguridad de respaldos y el mapeo a la
nube (Azure Blob, immutable storage, BD gestionadas).

## Laboratorio

Ver [`guia-lab.md`](guia-lab.md). Tres partes (1 hora) en **Play with Docker**:

1. **El experimento cruel + el fix** — pierde datos sin volumen; sobrevive con volumen.
2. **El blog inmortal** — el blog de la S3 con `-v datos_db:/var/lib/mysql`: matas
   la db y el post sobrevive.
3. **Respaldo y restauración PROBADA** — mysqldump → desastre total (contenedor y
   volumen) → reconstrucción → restauración → tu post de vuelta. Cronometra tu RTO.

**Entregable de la S4:** evidencias del ciclo completo + RTO cronometrado + Fase 1
del mini-proyecto en marcha.

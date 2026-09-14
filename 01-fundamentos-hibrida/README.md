# Sesión 1 · Fundamentos de contenedores y arquitectura de nube híbrida

Primera sesión del curso: qué problema resuelven los contenedores, en qué se
diferencian de las máquinas virtuales, y por qué son la **moneda de portabilidad**
de la nube híbrida. Hoy corres tus primeros contenedores.

## Objetivos

- **Explicar** qué es un contenedor, su diferencia con una VM y el problema que resuelve.
- **Reconocer** la arquitectura de nube híbrida y el rol de los contenedores en ella.
- **Ejecutar** tus primeros contenedores con Docker: correr, listar, inspeccionar, eliminar.
- 🔒 **Aplicar** el primer hábito de seguridad: usar solo imágenes oficiales verificadas.

## Contenido

```
01-fundamentos-hibrida/
├── guia-lab.md                 # laboratorio de la sesión (participantes)
└── diapositivas/               # deck de teoría (PPTX + PDF, 22 láminas) + guía en PDF
```

El deck incluye: diagramas contenedor vs VM, flujo de infraestructura
(build → push → pull → run), arquitectura de referencia híbrida, el mapa de servicios
de contenedores en **Azure** (ACR, ACI, Container Apps, AKS) y su equivalente en AWS
(iconos oficiales), y casos de uso reales.

## Laboratorio

Ver [`guia-lab.md`](guia-lab.md). Tres partes (1 hora) en **Play with Docker**:

1. **Tu primer contenedor** — hello-world y un servidor nginx con puerto publicado.
2. **Explora y comprueba lo efímero** — contenedor interactivo de Ubuntu y el
   experimento de la huella que desaparece.
3. **Bitácora** — el entregable de la sesión: capturas, comandos y reflexiones.

## Requisitos

Cuenta **gratuita** de [Docker Hub](https://hub.docker.com) (correo y contraseña).
Nada que instalar: el lab corre en el navegador.

**Entregable de la S1:** primer contenedor corriendo (captura) + bitácora diligenciada.

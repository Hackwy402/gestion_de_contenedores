# Guía de Laboratorio · Sesión 5 (cierre)

## Compose, un vistazo a Kubernetes — y TU demo final

**Curso 101-EAN · Gestión de Contenedores en Entornos de Nube Híbrida** · Duración: ~35 min + demos
Plataforma: **Play with Docker** (navegador, gratis)

> La última sesión: conviertes todo el curso en UN archivo (docker-compose.yml),
> ves a Kubernetes cuidar contenedores solo, y presentas tu mini-proyecto.

---

## Parte 1 · Tu primer docker-compose.yml (20 min)

**1.1 —** En una instancia nueva de [Play with Docker](https://labs.play-with-docker.com):

```bash
mkdir mi-app && cd mi-app
cat > docker-compose.yml <<'EOF'
services:
  db:
    image: mysql:8.0
    volumes:
      - datos_db:/var/lib/mysql
    environment:
      MYSQL_ROOT_PASSWORD: Ean2026root
      MYSQL_DATABASE: wordpress
      MYSQL_USER: wp
      MYSQL_PASSWORD: Ean2026wp

  blog:
    image: wordpress:6
    ports:
      - "8080:80"
    environment:
      WORDPRESS_DB_HOST: db
      WORDPRESS_DB_USER: wp
      WORDPRESS_DB_PASSWORD: Ean2026wp
      WORDPRESS_DB_NAME: wordpress
    depends_on:
      - db

volumes:
  datos_db:
EOF
```

⚠️ En YAML **la indentación es sintaxis**: dos espacios por nivel, nunca tabs.

**1.2 — Toda la app, una línea:**

```bash
docker compose up -d
docker compose ps            # los dos servicios, su estado, sus puertos
docker network ls            # mira: Compose creó la red por ti (mi-app_default)
```

Abre el 8080, instala el blog exprés y publica un post.

**1.3 — La prueba de fuego (todo el curso en 3 comandos):**

```bash
docker compose down          # baja app y red — pero NO los volúmenes
docker compose ps            # nada corriendo
docker compose up -d         # todo de vuelta…
```

Recarga el 8080: **tu post sigue ahí**. La S4 dentro de la S5: `down` respetó el
volumen. (El día que quieras borrar TODO: `docker compose down -v`.)

> ✍️ **Para la bitácora:** compara este flujo con los 6 comandos de la S3/S4.
> ¿Qué le dirías a un colega que aún despliega con comandos sueltos?

**1.4 — Limpieza:** `docker compose down -v`

---

## Parte 2 · Kubernetes, guiado (15 min)

Sigue la demo del docente en pantalla. Si quieres tocarlo con tus manos, abre
[killercoda.com/playgrounds/scenario/kubernetes](https://killercoda.com/playgrounds/scenario/kubernetes)
y replica:

```bash
# 1. Declara el deseo: 3 réplicas de la app del curso
kubectl create deployment portal --image=jawy21/login-app:1.0 --replicas=3
kubectl get pods                      # tres pods corriendo

# 2. El asesinato (self-healing)
kubectl delete pod <NOMBRE-DE-UN-POD>
kubectl get pods                      # ¡ya hay uno nuevo! K8s mantiene el deseo

# 3. El pico de fin de mes
kubectl scale deployment portal --replicas=10
kubectl get pods                      # diez
kubectl scale deployment portal --replicas=3

# 4. La puerta estable
kubectl expose deployment portal --type=NodePort --port=80
kubectl get svc                       # un service balanceando a los pods
```

> ✍️ **Para la bitácora:** ¿qué hizo Kubernetes que en Docker "eras tú"?
> ¿En qué caso de tu entidad valdría la pena?

---

## Parte 3 · 🚀 Tu demo final (5 min por equipo)

El guion de tus 5 minutos (ensáyalo — el cronómetro no perdona):

1. **Min 0-1**: la app VIVA (URL funcionando) y qué hace.
2. **Min 1-2**: tu diagrama de arquitectura.
3. **Min 2-4**: la restauración EN VIVO — mata la BD, tráela de vuelta.
4. **Min 4-5**: lo más difícil del proyecto + qué contenerizarías en tu trabajo.

Entregas: bitácora del proyecto + URL de tu imagen en Docker Hub
(rúbrica completa en `mini-proyecto.md`).

---

## Checklist final del curso

- [ ] Escribí un docker-compose.yml y levanté la app completa con una línea.
- [ ] Comprobé que down/up respeta los volúmenes.
- [ ] Vi (o hice) el self-healing y el escalado en Kubernetes.
- [ ] Presenté mi mini-proyecto con la restauración en vivo.
- [ ] 💰 Apagué/limpié todo lo que ya no uso (instancias, VM, contenedores).

---

**El curso termina; tu práctica sigue.** El repositorio queda público con todo el
material. Gracias por estas 5 semanas — nos vemos en la nube. 🐳🚀

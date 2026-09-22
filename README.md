# Parcial 2 — Despliegue multi-contenedor (Comunicaciones, Ing. Mecatrónica)

## Requisitos
- Docker y Docker Compose instalados.

## Arranque (zero-touch)
```bash
git clone <URL_DEL_REPOSITORIO>
cd <CARPETA_DEL_REPOSITORIO>
cp .env.example .env
docker compose up -d
```

## Acceso a los servicios (todo pasa por Nginx en el puerto 80)
- Joomla: http://localhost/
- Jupyter: http://localhost/jupyter/  (token definido en `.env`)
- Grafana: http://localhost/grafana/  (usuario/contraseña definidos en `.env`)

## Primer arranque de Joomla
La primera vez que abras `http://localhost/`, Joomla pedirá completar el
asistente de instalación web. Usa estos datos (deben coincidir con `.env`):
- Tipo de base de datos: **PostgreSQL (PDO)**
- Host: `database`
- Usuario / contraseña / nombre de BD: los de tu archivo `.env`

## Notas
- Todos los datos persisten en volúmenes nombrados de Docker.
- La base de datos NO tiene puerto publicado al host: solo es visible dentro de `backend_net`.
- Ver `INFORME.md` para el análisis técnico completo (topología + modelo OSI).
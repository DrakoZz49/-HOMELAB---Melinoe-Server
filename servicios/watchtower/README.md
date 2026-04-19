# 🐳 Watchtower

Watchtower se encarga de **mantener todos los contenedores Docker actualizados automáticamente**, sin intervención manual. Comprueba periódicamente si hay nuevas versiones de las imágenes y, si las hay, reinicia el contenedor con la imagen actualizada conservando toda la configuración original.

---

## ¿Cómo funciona?

Watchtower accede al socket de Docker (`/var/run/docker.sock`), lo que le permite ver y gestionar **todos los contenedores en ejecución** del sistema, independientemente de desde qué `docker-compose` se hayan levantado.

---

## Configuración

### Comportamiento

| Variable | Valor | Descripción |
|---|---|---|
| `WATCHTOWER_CLEANUP` | `true` | Elimina las imágenes antiguas tras actualizar |
| `WATCHTOWER_SCHEDULE` | `0 0 4 * * *` | Se ejecuta cada día a las 4:00 AM |
| `WATCHTOWER_NOTIFICATIONS` | `shoutrrr` | Sistema de notificaciones |
| `WATCHTOWER_NOTIFICATION_URL` | `telegram://...` | Notificaciones vía bot de Telegram |

### Notificaciones

Las notificaciones se envían a través del bot **Melinoé Vigilante** en Telegram cada vez que se actualiza algún contenedor.

---

## Estructura de archivos

```
~/watchtower/
└── docker-compose.yml
```

---

## Comandos útiles

```bash
# Ver si Watchtower está corriendo
docker ps | grep watchtower

# Ver los logs de Watchtower
docker logs watchtower

# Forzar una comprobación manual ahora mismo
docker exec watchtower /watchtower --run-once --notification-report

# Reiniciar el servicio
cd ~/watchtower && docker compose restart
```

---

## Notas

- Watchtower **no modifica volúmenes ni configuración** de los contenedores al actualizar, solo reemplaza la imagen.
- Si en el futuro se quiere **excluir algún contenedor** de las actualizaciones automáticas, basta con añadir esta etiqueta en su `docker-compose.yml`:

```yaml
labels:
  - "com.centurylinklabs.watchtower.enable=false"
```

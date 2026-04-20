# 🖥️ Melinoe Homelab

Documentación personal del servidor doméstico **Melinoe**: un portátil reciclado reconvertido en servidor casero, corriendo Ubuntu Server con varios servicios en Docker.

Este repositorio sirve como referencia técnica para el mantenimiento del servidor y como guía para cualquiera que quiera montar algo similar desde cero.

---

## 🏗️ Infraestructura

| Parámetro | Valor |
|---|---|
| **Hardware** | Portátil reciclado |
| **Sistema operativo** | Ubuntu Server |
| **IP local fija** | `192.168.0.77` |
| **Interfaz de red** | Ethernet (`enp7s0`) |
| **Acceso remoto** | Tailscale |

---

## 🐳 Servicios

Todos los servicios corren en Docker, organizados en carpetas independientes.

| Servicio | Puerto | Carpeta |
|---|---|---|
| Nextcloud | `8080` | `~/nextcloud-docker/` |
| Jellyfin | `8096` | `~/jellyfin/` |
| Calibre-Web | `8083` | `~/calibre-web/` |
| RomM | `8084` | `~/romm/` |
| Uptime Kuma | `3001` | `~/nextcloud-docker/` |
| Flame | `8085` | `~/flame/` |
| Watchtower | — | `~/watchtower/` |

---

## 🔧 Backups

- **Herramienta:** RClone
- **Destino:** Google Drive

---

## 📁 Estructura del repositorio

```
melinoe-homelab/
├── README.md
└── servicios/
    └── watchtower/
        ├── README.md
        └── docker-compose.yml
```

La documentación de cada servicio vive en su propia carpeta dentro de `servicios/`. Se irá ampliando progresivamente.

---

## 🗺️ Roadmap

- [x] Watchtower — actualizaciones automáticas
- [ ] Nextcloud
- [ ] Jellyfin
- [ ] Calibre-Web
- [ ] RomM
- [ ] Uptime Kuma
- [ ] Flame
- [ ] Guía de instalación desde cero
- [ ] NAS con RAID 1

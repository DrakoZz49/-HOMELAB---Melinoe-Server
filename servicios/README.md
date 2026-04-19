# 🖥️ Melinoé Homelab

Documentación personal del servidor doméstico **Melinoé**: un portátil reciclado reconvertido en servidor casero, corriendo Ubuntu Server con varios servicios en Docker.

Este repositorio sirve como referencia técnica para el mantenimiento del servidor y como guía para cualquiera que quiera montar algo similar desde cero.

---

## 🏗️ Infraestructura

| Parámetro | Valor |
|---|---|
| **Hardware** | Portátil reciclado |
| **Sistema operativo** | Ubuntu Server |
| **IP local fija** | `192.168.0.77` |
| **Interfaz de red** | Ethernet (`enp7s0`) |
| **Acceso remoto** | Tailscale (`melinoe.tail3d13a6.ts.net`) |

---

## 🐳 Servicios

Todos los servicios corren en Docker, organizados en carpetas independientes bajo `~/docker/`, excepto Watchtower que reside en `~/watchtower/`.

| Servicio | Puerto | Carpeta |
|---|---|---|
| Nextcloud | `8080` | `~/docker/nextcloud-docker/` |
| Jellyfin | `8096` | `~/docker/jellyfin/` |
| Calibre-Web | `8083` | `~/docker/calibre-web/` |
| RomM | `8084` | `~/docker/romm/` |
| Uptime Kuma | `3001` | `~/docker/nextcloud-docker/` |
| Flame | `8085` | `~/docker/flame/` |
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

# HomeLab projekt összefoglaló (2025. október)

## Hardver és jelenlegi állapot
- **Eszköz:** Kis laptop (2 GB RAM, Intel Atom N455 CPU)
- **Átlagos terhelés:** CPU 10–16%, RAM használat ~740 MB
- **Futó szolgáltatások:**
  - Pi-hole (natívan)
  - Home Assistant (Dockerben)
  - Netdata (Dockerben)

---

## Javasolt további szolgáltatások

###  Erőforrás-kímélő (ajánlott)
Ezek a szolgáltatások biztonságosan futtathatók a jelenlegi hardveren.

| Szolgáltatás | Funkció | Megjegyzés |
|--------------|----------|-------------|
| **Glance** | Könnyű, YAML-alapú dashboard | Minimális CPU/RAM igény, webes áttekintés |
| **Homarr** | Modern kezdőoldal | Kicsit nehezebb, de még elbírja |
| **File Browser** | Webes fájlkezelő | 50–100 MB RAM |
| **Vaultwarden** | Bitwarden-kompatibilis jelszókezelő | Biztonságos és könnyű |
| **Zigbee2MQTT** | Zigbee integráció | Könnyű MQTT-alapú működés |
| **Portainer** | Docker konténer-kezelő | ~100 MB RAM |
| **NGINX Proxy Manager** | Reverse proxy + SSL | 200–300 MB RAM |
| **Cloudflare DDNS** | Dinamikus IP frissítés | Elhanyagolható erőforrás |

---

##  Közepes erőforrás-igényű (óvatosan)
Ezek futtathatók, de csak korlátozással.

| Szolgáltatás | Funkció | Igény |
|--------------|----------|--------|
| **qBittorrent-nox** | Torrent kliens | Min. 1 GB RAM |
| **Grafana + Prometheus** | Mérőadatok, vizualizáció | 512 MB – 1 GB RAM |

---

## Nem ajánlott a jelenlegi hardveren

| Szolgáltatás | Indok |
|--------------|-------|
| **Nextcloud** | Legalább 2 GB RAM és 2 CPU mag kell |
| **Plex/Jellyfin** | Magas CPU-igény transzkódolásnál |
| ***arr stack** (Radarr, Sonarr, stb.) | Nagy RAM fogyasztás |
| **Immich** | Erős CPU/GPU igény |
| **Frigate** | Kamera + AI feldolgozás, nem fér bele |

---

## Összegzés
A mini HomeLab jelenleg:

- stabil,
- alacsony fogyasztású,
- könnyen kezelhető.

### Ajánlott következő lépések:
1. **Portainer** telepítése a Docker konténerek felügyeletéhez  
2. **Glance vagy Homarr** dashboard beállítása  
3. **Vaultwarden** vagy **File Browser** integrálása  
4. **NGINX Proxy Manager + Cloudflare DDNS** a távoli eléréshez  
5. **Zigbee2MQTT** felvétele, ha később bővíted az okosotthon modult

Ez a környezet ideális egy alacsony fogyasztású, könnyen üzemeltethető mini-HomeLabhoz.


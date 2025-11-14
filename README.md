# HomeLab & Microsoft 365 Lab Dokumentáció

Ez a repó a saját HomeLab környezetem teljes dokumentációját tartalmazza, beleértve a Proxmox alapú szerverrendszert, a Lenovo M910q klasztert, a szolgáltatások felépítését, valamint a Microsoft 365 Developer Programhoz tartozó E5 Sandbox környezet beállításait és integrációit.  
A cél egy jól strukturált, bővíthető, stabil és hosszú távon fenntartható rendszer kialakítása.

---

## Tartalomjegyzék

- [Áttekintés](#áttekintés)
- [Projektcélok](#projektcélok)
- [HomeLab felépítése](#homelab-felépítése)
- [Proxmox klaszter](#proxmox-klaszter)
- [Dokumentumok](#dokumentumok)
- [Microsoft 365 E5 Sandbox](#microsoft-365-e5-sandbox)
- [Integrációk](#integrációk)
- [Fejlesztési irányok](#fejlesztési-irányok)
- [Licenc](#licenc)

---

## Áttekintés

A rendszer alapjai három Lenovo ThinkCentre M910q mini PC-ből felépített Proxmox klaszter, amely konténerek és virtuális gépek futtatására szolgál.  
Emellett a Microsoft 365 Developer Programban létrehozott E5 Sandbox segítségével gyakorolható:

- Microsoft 365 adminisztráció  
- Azure AD / Entra ID  
- Exchange Online  
- Teams integráció  
- Graph API fejlesztés  
- Zero Trust hozzáférési modellek

A projekt célja a gyakorlás, a tanulás és egy saját infrastruktúra folyamatos fejlesztése.

---

## Projektcélok

- Egységes, stabil HomeLab környezet kialakítása
- Dokumentáció fenntartása, verziókövetése GitHubon
- Proxmox klaszter beüzemelése mini PC-ken
- Docker és LXC alapú szolgáltatások elkülönítése
- Média-, hálózati- és biztonsági szolgáltatások integrálása
- Microsoft 365 E5 Sandbox gyakorló-környezet használata
- Automatizálások és API-alapú megoldások fejlesztése

---

## HomeLab felépítése

A mini PC-k szerepköre:

- **Core node** – központi szolgáltatások, DNS, VPN, reverse proxy  
- **Media node** – Plex/Jellyfin, qBittorrent, letöltés és transzkódolás  
- **Utility node** – Home Assistant, Vaultwarden, monitoring, kisebb szolgáltatások  

Tárhelyek:
- NVMe SSD a rendszernek és VM-eknek  
- SATA vagy USB-s HDD-k médialetöltésekhez és megosztásokhoz  

---

## Proxmox klaszter

A három Lenovo M910q-ból épülő klaszter biztosítja:

- LXC konténerek futtatását
- Virtuális gépek kezelését
- Távoli menedzsmentet
- Alacsony fogyasztás mellett magas rendelkezésre állást
- Egységes storage-kezelést (USB, SATA, NFS, SMB)

Részletes beállítások a dokumentumok között találhatók.

---

## Dokumentumok

A repó a következő fő dokumentumokat tartalmazza:

- `docs/homelab_setup.md` – Mini HomeLab alapbeállításai  
- `docs/homelab_setup_lenovo_server.md` – Lenovo M910q klaszter részletes dokumentáció  
- `docs/goals.md` – HomeLab céljai és lépésről lépésre tervezett felépítése  
- `docs/Microsoft_Developer_Program.md` – Microsoft 365 E5 Sandbox leírása és gyakorlati útmutató  

Valamint kiegészítő fájlok:

- Docker Compose fájlok  
- Proxmox script-ek  
- Jegyzetek, konfigurációk  

---

## Microsoft 365 E5 Sandbox

A Microsoft 365 Developer Program keretében ingyenesen létrehozott E5 környezet alkalmas:

- Exchange Online tesztelésre  
- Teams integrációk vizsgálatára  
- Azure AD / Entra ID identitáskezelés gyakorlására  
- Conditional Access szabályok tesztelésére  
- Graph API fejlesztésre  
- Automatizált értesítésekre (pl. Proxmox → Teams)  

A Sandbox nem tartalmaz éles adatokat, oktatási célra jött létre.

---

## Integrációk

A HomeLab és a Microsoft 365 sandbox között több integráció tervezett vagy már működik:

- Proxmox backup értesítések → Microsoft Teams  
- Netdata riasztások → Teams  
- SMTP értesítések Exchange-en keresztül  
- OneDrive szinkron a dokumentációk számára  
- Graph API alapú szkriptek (felhasználók, csoportok, üzenetek kezelése)  

VPN és Zero Trust megoldások:

- Tailscale  
- Twingate  
- WireGuard  

---

## Fejlesztési irányok

A rendszer folyamatosan bővíthető az alábbi technológiákkal:

- Kubernetes / k3s  
- Ansible automatizálások  
- Ceph vagy egyéb megosztott storage  
- Grafana Cloud monitoring  
- Zero Trust hálózat fejlesztése  
- M365 appok és API integrációk  
- Container orchestration tervezése  

---

## Licenc

A dokumentáció szabadon felhasználható és módosítható.  
A konfigurációk és szkriptek éles környezetben csak saját felelősségre alkalmazhatók.


# Linux-järjestelmänhallinta

Tässä osiossa käsitellään keskeisiä järjestelmänhallintaan liittyviä komentoja Linux-järjestelmissä. Ohjeet on laadittu erityisesti WSL-versiolle Ubuntusta. Komennot vaativat usein **sudo**-oikeuksia, joten varmista, että sinulla on tarvittavat oikeudet.

## Peruskomennot

### **sudo**
- **Selitys:** Suorittaa komennon hallintaoikeuksilla.
- **Esimerkki:**
  ```bash
  sudo apt update
  ```
  Päivittää saatavilla olevien pakettien luettelon käyttäen hallintaoikeuksia.

### **apt install**
- **Käyttö:** `sudo apt install <paketti>`
- **Selitys:** Asentaa ohjelmistopaketin järjestelmään.
- **Esimerkki:**
  ```bash
  sudo apt install nginx
  ```
  Asentaa Nginx-verkkopalvelimen.

### **var/www/html**
- **Selitys:** Oletushakemisto, johon verkkosivujen sisältö tallennetaan Apache- tai Nginx-palvelimissa.
- **Huomio:** Käytä `sudo`-komentoa tiedostojen muokkaamiseen tässä hakemistossa, sillä se vaatii hallintaoikeuksia.

---

Nämä komennot auttavat sinua hallitsemaan Linux-järjestelmää tehokkaasti ja turvallisesti. Järjestelmänhallinnan aikana on tärkeää olla varovainen hallintaoikeuksilla tehtävien toimintojen kanssa.

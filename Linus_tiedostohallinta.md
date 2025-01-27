# Linux-tiedostohallinta

Tässä osiossa käydään läpi tärkeimpiä tiedostojen ja hakemistojen hallintaan liittyviä komentoja Linux-järjestelmässä. Ohjeet on laadittu erityisesti WSL-versiolle Ubuntusta.

## Peruskomennot

### **scp**
- **Käyttö:** `scp <tiedostonimi> käyttäjä@osoite:/kohdepolku`
- **Selitys:** Kopioi tiedoston paikalliselta koneelta etäkoneelle turvallisesti SSH-yhteyttä käyttäen.
- **Esimerkki:**
  ```bash
  scp tiedosto.txt student@[opiskelijan ip]:/home/student
  ```
  Tämä komento kopioi `tiedosto.txt`-tiedoston etäkoneelle hakemistoon `/home/student`.

### **cp**
- **Käyttö:** `cp <lähde> <kohde>`
- **Selitys:** Kopioi tiedoston tai hakemiston.
- **Esimerkki:**
  ```bash
  cp tiedosto.txt varmuuskopiot/
  ```
  Tämä kopioi tiedoston `tiedosto.txt` hakemistoon `varmuuskopiot/`.

### **mv**
- **Käyttö:** `mv <lähde> <kohde>`
- **Selitys:** Siirtää tai uudelleennimeää tiedoston tai hakemiston.
- **Esimerkki:**
  ```bash
  mv vanhanimi.txt uusi.txt
  ```
  Tämä uudelleennimeää tiedoston `vanhanimi.txt` nimeksi `uusi.txt`.

### **touch**
- **Käyttö:** `touch <tiedostonimi>`
- **Selitys:** Luo tyhjän tiedoston määritetyllä nimellä.
- **Esimerkki:**
  ```bash
  touch uusi_tiedosto.txt
  ```
  Tämä luo tiedoston `uusi_tiedosto.txt`.

### **mkdir**
- **Käyttö:** `mkdir <hakemistonimi>`
- **Selitys:** Luo uuden hakemiston.
- **Esimerkki:**
  ```bash
  mkdir projektit
  ```
  Tämä luo hakemiston `projektit`.

---

Nämä komennot auttavat sinua hallitsemaan tiedostoja ja hakemistoja tehokkaasti Linux-ympäristössä. Muista aina tarkistaa oikeudet, jos kohtaat ongelmia tiedostojen käsittelyssä.

# Kytkimen peruskonfigurointi

Tässä osiossa käsitellään Cisco-kykimen perusasetuksia ja tärkeimpiä komentoja, jotka auttavat laitteen ensikäyttöä ja hallintaa.

## Komennot

### **enable**
- **Selitys:** Siirtyy EXEC-tilaan, jossa voidaan suorittaa hallintatason komentoja.
- **Käyttö:**
  ```
  S1> enable
  S1#
  ```

### **configure terminal**
- **Selitys:** Siirtyy globaaliin konfigurointitilaan, jossa voidaan muokata kytkimen asetuksia.
- **Käyttö:**
  ```
  S1# configure terminal
  S1(config)#
  ```

### **enable password <salasana>**
- **Selitys:** Asettaa salasanan EXEC-tilaan siirtymiselle.
- **Esimerkki:**
  ```
  S1(config)# enable password vahvaSalasana123
  ```

### **line console 0**
- **Selitys:** Siirtyy konsoliyhteyden asetuksiin.
- **Alikomennot:**
  - `password <salasana>`: Asettaa konsoliyhteyden salasanan.
  - `login`: Ottaa salasanan käyttöön konsoliyhteydessä.
- **Esimerkki:**
  ```
  S1(config)# line console 0
  S1(config-line)# password salasanani
  S1(config-line)# login
  ```

### **banner motd "<viesti>"**
- **Selitys:** Asettaa Message of the Day (MOTD) -viestin, joka näkyy käyttäjälle sisäänkirjautumisen yhteydessä.
- **Esimerkki:**
  ```
  S1(config)# banner motd "Tervetuloa verkkoomme!"
  ```

### **interface vlan 1**
- **Selitys:** Konfiguroi VLAN 1 -rajapinnan hallintaa varten.
- **Esimerkki:**
  ```
  S1(config)# interface vlan 1
  S1(config-if)# ip address 192.168.1.1 255.255.255.0
  S1(config-if)# no shutdown
  ```

### **service password-encryption**
- **Selitys:** Salakirjoittaa kaikki laitteeseen tallennetut salasana-arvot.
- **Esimerkki:**
  ```
  S1(config)# service password-encryption
  ```

### **enable secret <salasana>**
- **Selitys:** Asettaa EXEC-tilaan vahvemman, salatun salasanan.
- **Esimerkki:**
  ```
  S1(config)# enable secret salainenSalasana123
  ```

---

Näillä komennoilla voit konfiguroida kytkimen turvallisesti ja tehokkaasti. Muista tallentaa muutokset suorittamalla **write memory** tai **copy running-config startup-config** kytkimen asetusten pysyväksi tallentamiseksi.

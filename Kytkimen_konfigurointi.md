# Kytkimen peruskonfigurointi

Tässä osiossa käsitellään Cisco-kytkimen perusasetuksia, joita käytetään esimerkiksi Cisco Packet Tracer -tehtävissä. Ohjeet sisältävät yleisimmät komennot ja niiden käyttötavat.

---

## Komennot ja niiden käyttö

### **enable**
- **Selitys:** Siirtyy EXEC-tilaan, jossa voidaan suorittaa hallintatason komentoja.
- **Käyttö:**
  ```
  switch> enable
  switch#
  ```

### **configure terminal**
- **Selitys:** Siirtyy globaaliin konfigurointitilaan, jossa voidaan muokata kytkimen asetuksia.
- **Käyttö:**
  ```
  switch# configure terminal
  switch(config)#
  ```

### **exit**
- **Selitys:** Palauttaa edelliselle komentotasolle. Esimerkiksi globaaliasta konfigurointitilasta EXEC-tilaan.
- **Esimerkki:**
  ```
  switch(config-if)# exit
  switch(config)# exit
  switch#
  ```

### **no ip domain-lookup**
- **Selitys:** Poistaa käytöstä kytkimen oletusarvoisen toiminnon, jossa se yrittää ratkaista virheelliset komennot DNS-palvelimen avulla.
- **Käyttö:**
  ```
  switch(config)# no ip domain-lookup
  ```
- **Hyöty:** Nopeuttaa virheellisten komentojen käsittelyä, koska kytkin ei yritä ratkaista niitä verkkotunnuksiksi.

### **interface vlan 1**
- **Selitys:** Konfiguroi VLAN 1 -rajapinnan hallintaa varten. VLAN 1 on oletusarvoinen hallintarajapinta.
- **Käyttö:**
  ```
  switch(config)# interface vlan 1
  switch(config-if)# ip address 192.168.1.1 255.255.255.0
  switch(config-if)# no shutdown
  ```

### **show ip interface brief**
- **Selitys:** Näyttää yhteenvedon kytkimen rajapinnoista ja niiden tilasta.
- **Esimerkki:**
  ```
  switch# show ip interface brief
  ```

### **line console 0**
- **Selitys:** Määrittää konsoliyhteyden asetuksia.
- **Alikomennot:**
  - `password <salasana>`: Asettaa konsoliyhteyden salasanan.
  - `login`: Ottaa salasanan käyttöön konsoliyhteydessä.
- **Esimerkki:**
  ```
  switch(config)# line console 0
  switch(config-line)# password letmein
  switch(config-line)# login
  ```

### **hostname**
- **Selitys:** Asettaa kytkimelle nimen, joka näkyy komentokehotteessa.
- **Esimerkki:**
  ```
  switch(config)# hostname S1
  S1(config)#
  ```

### **enable password**
- **Selitys:** Määrittää salasanan EXEC-tilaan siirtymiselle.
- **Esimerkki:**
  ```
  switch(config)# enable password c1$c0
  ```

### **enable secret**
- **Selitys:** Määrittää salatun salasanan EXEC-tilaan siirtymiselle. Tämä on turvallisempi vaihtoehto kuin `enable password`.
- **Esimerkki:**
  ```
  switch(config)# enable secret itsasecret
  ```

### **service password-encryption**
- **Selitys:** Salakirjoittaa kaikki tekstimuotoiset salasanat.
- **Esimerkki:**
  ```
  switch(config)# service password-encryption
  ```

### **banner motd**
- **Selitys:** Asettaa Message of the Day (MOTD) -viestin, joka näkyy käyttäjälle sisäänkirjautumisen yhteydessä.
- **Esimerkki:**
  ```
  switch(config)# banner motd "Tämä on suojattu järjestelmä. Luvaton pääsy kielletty!"
  ```

### **show running-config**
- **Selitys:** Näyttää käynnissä olevan konfiguraation (running-config).
- **Esimerkki:**
  ```
  switch# show running-config
  ```

### **copy running-config startup-config**
- **Selitys:** Tallentaa käynnissä olevan konfiguraation (running-config) pysyväksi konfiguraatioksi (startup-config).
- **Esimerkki:**
  ```
  switch# copy running-config startup-config
  ```
### **erase startup-config**
- **Selitys:** Poistaa kytkimen startup-config -asetukset, eli tallennetun konfiguraation NVRAM-muistista.
- **Käyttö:**
  ```
  switch# erase startup-config
  ```
- **Huom:** Käyttämällä tätä komentoa palautat kytkimen alkuperäiseen tilaan ilman aiemmin tallennettuja asetuksia.

### **reload**
- **Selitys:** Käynnistää kytkimen uudelleen.
- **Käyttö:**
  ```
  switch# reload
  ```
- **Vahvistus:** Komento pyytää vahvistusta ennen uudelleenkäynnistystä. Voit perua toiminnon painamalla `n` (no).
- **Huom:** Jos startup-config on poistettu ennen reload-komennon suorittamista, kytkin käynnistyy oletusasetuksilla.

---

Näillä komennoilla voit suorittaa kytkimen peruskonfiguroinnin, tallentaa asetukset ja varmistaa niiden toimivuuden. Muista testata jokaisen vaiheen jälkeen konfiguraatio ja tallentaa muutokset pysyvästi!

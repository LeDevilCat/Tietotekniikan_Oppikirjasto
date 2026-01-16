# Kytkimen peruskonfigurointi

Tässä osiossa käsitellään Cisco-kytkimien perusasetuksia, joita käytetään Ciscon fyysisissä labroissa ja Packet Tracer -tehtävissä. Ohjeet sisältävät peruskonfiguroinnin komennot ja niiden käyttötavat.

Huomaa että osa komennoista ovat samoja reitittimien kanssa.

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

### **end**
- **Selitys:** Palaa suoraan EXEC-tilaan globaalista tai rajapintakonfigurointitilasta ilman useita `exit`-komentoja.
- **Esimerkki:**
  ```
  switch(config-if)# end
  switch#
  ```

### **hostname**
- **Selitys:** Asettaa laitteen nimen, joka näkyy komentokehotteessa ja helpottaa laitteiden tunnistamista verkossa.
- **Esimerkki:**
  ```
  switch(config)# hostname S1
  switch(config)#
  ```

### **no ip domain lookup**
- **Selitys:** Estää laitteen automaattiset DNS-kyselyt, kun komentoriville kirjoitetaan tuntematon nimi. Poistaa viiveen, joka aiheutuu nimen ratkaisemisyrityksestä.
- **Esimerkki:**
  ```
  switch(config)# no ip domain-lookup
  switch(config)#
  ```

### **enable secret**
- **Selitys:** Asettaa salatun (salasanan hashattuna) salasanan privileged EXEC -tilaan; suositeltava tapa asettaa pääsalasana.
- **Esimerkki:**
  ```
  switch(config)# enable secret class
  ```

### **line console 0**
- **Selitys:** Siirtyy konsolirivikonfigurointiin; alla olevilla komennoilla asetetaan konsolisalasana ja otetaan sisäänkirjautuminen käyttöön.
- **Esimerkki:**
  ```
  switch(config)# line console 0
  switch(config-line)# password cisco
  switch(config-line)# login
  switch(config-line)# exit
  ```

### **line vty 0 15**
- **Selitys:** Konfiguroi etäyhteysrajapinnat (VTY) esimerkiksi Telnet/SSH-yhteyksiä varten; asetetaan salasana ja otetaan sisäänkirjautuminen käyttöön. Kytkimissä käytetään tyypillisesti 0-15 (16 samanaikaista yhteyttä).
- **Esimerkki:**
  ```
  switch(config)# line vty 0 15
  switch(config-line)# password cisco
  switch(config-line)# login
  switch(config-line)# exit
  ```
  - **Huom:** VTY-linjojen lukumäärä vaihtelee laitemallin mukaan. Reitittimissä käytetään usein `line vty 0 4` (5 yhteyttä) ja kytkimissä `line vty 0 15` (16 yhteyttä). Labra-/kurssiympäristöissä oletus voi vaihdella IOS-version ja laitemallin mukaan, mutta komennon käyttötapa on sama. Tarvittaessa voit määrittää toisen alueen samalla tavalla.

### **service password-encryption**
- **Selitys:** Salaa konfiguraatiossa näkyvät selväsanaiset salasanat heikolla salauksella (type 7), jotta ne eivät näy paljain silmin.
- **Esimerkki:**
  ```
  switch(config)# service password-encryption
  ```

### **banner motd**
- **Selitys:** Asettaa esittely- tai varoitusviestin (Message of the Day), joka näytetään ennen kirjautumista laitteeseen.
- **Esimerkki:**
  ```
  switch(config)# banner motd # Authorized Users Only! #
  ```

### **copy running-config startup-config**
- **Selitys:** Tallentaa nykyisen juoksevan konfiguraation käynnistyvään konfiguraatiotiedostoon, jotta muutokset säilyvät uudelleenkäynnistyksen jälkeen.
- **Esimerkki:**
  ```
  switch# copy running-config startup-config
  ```

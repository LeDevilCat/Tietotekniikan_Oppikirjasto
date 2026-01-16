# Reitittimen peruskonfigurointi

Tässä osiossa käsitellään Cisco-reitittimien perusasetuksia, joita käytetään Ciscon fyysisissä labroissa ja Packet Tracer -tehtävissä. Ohjeet sisältävät peruskonfiguroinnin komennot ja niiden käyttötavat.

Huomaa että osa komennoista ovat samoja kytkimien kanssa.

---

## Komennot ja niiden käyttö

### **enable**
- **Selitys:** Siirtyy EXEC-tilaan, jossa voidaan suorittaa hallintatason komentoja.
- **Käyttö:**
  ```
  router> enable
  router#
  ```

### **configure terminal**
- **Selitys:** Siirtyy globaaliin konfigurointitilaan, jossa voidaan muokata kytkimen asetuksia.
- **Käyttö:**
  ```
  router# configure terminal
  router(config)#
  ```

### **exit**
- **Selitys:** Palauttaa edelliselle komentotasolle. Esimerkiksi globaaliasta konfigurointitilasta EXEC-tilaan.
- **Esimerkki:**
  ```
  router(config-if)# exit
  router(config)# exit
  router#
  ```

### **end**
- **Selitys:** Palaa suoraan EXEC-tilaan globaalista tai rajapintakonfigurointitilasta ilman useita `exit`-komentoja.
- **Esimerkki:**
  ```
  router(config-if)# end
  router#
  ```

### **hostname**
- **Selitys:** Asettaa laitteen nimen, joka näkyy komentokehotteessa ja helpottaa laitteiden tunnistamista verkossa.
- **Esimerkki:**
  ```
  router(config)# hostname R1
  R1(config)#
  ```

### **no ip domain lookup**
- **Selitys:** Estää laitteen automaattiset DNS-kyselyt, kun komentoriville kirjoitetaan tuntematon nimi. Poistaa viiveen, joka aiheutuu nimen ratkaisemisyrityksestä.
- **Esimerkki:**
  ```
  router(config)# no ip domain-lookup
  router(config)#
  ```

### **interface vlan 1**
- **Selitys:** Konfiguroi VLAN 1 -rajapinnan hallintaa varten. VLAN 1 on oletusarvoinen hallintarajapinta.
- **Käyttö:**
  ```
  switch(config)# interface vlan 1
  switch(config-if)# ip address 192.168.1.1 255.255.255.0
  switch(config-if)# no shutdown
  ```

### **enable secret**
- **Selitys:** Asettaa salatun (salasanan hashattuna) salasanan privileged EXEC -tilaan; suositeltava tapa asettaa pääsalasana.
- **Esimerkki:**
  ```
  R1(config)# enable secret class
  ```

### **line console 0**
- **Selitys:** Siirtyy konsolirivikonfigurointiin; alla olevilla komennoilla asetetaan konsolisalasana ja otetaan sisäänkirjautuminen käyttöön.
- **Esimerkki:**
  ```
  R1(config)# line console 0
  R1(config-line)# password cisco
  R1(config-line)# login
  R1(config-line)# exit
  ```

### **line vty 0 4**
- **Selitys:** Konfiguroi etäyhteysrajapinnat (VTY) esimerkiksi Telnet/SSH-yhteyksiä varten; asetetaan salasana ja otetaan sisäänkirjautuminen käyttöön.
- **Esimerkki:**
  ```
  R1(config)# line vty 0 4
  R1(config-line)# password cisco
  R1(config-line)# login
  R1(config-line)# exit
  ```
- **Huom:** VTY-linjojen lukumäärä vaihtelee laitemallin mukaan. Reitittimissä käytetään usein `line vty 0 4` (5 yhteyttä) ja kytkimissä `line vty 0 15` (16 yhteyttä). Labra-/kurssiympäristöissä oletus voi vaihdella IOS-version ja laitemallin mukaan, mutta komennon käyttötapa on sama. Tarvittaessa voit määrittää toisen alueen samalla tavalla.

### **service password-encryption**
- **Selitys:** Salaa konfiguraatiossa näkyvät selväsanaiset salasanat heikolla salauksella (type 7), jotta ne eivät näy paljain silmin.
- **Esimerkki:**
  ```
  R1(config)# service password-encryption
  ```

### **banner motd**
- **Selitys:** Asettaa esittely- tai varoitusviestin (Message of the Day), joka näytetään ennen kirjautumista laitteeseen.
- **Esimerkki:**
  ```
  R1(config)# banner motd $ Authorized Users Only! $
  ```

### **copy running-config startup-config**
- **Selitys:** Tallentaa nykyisen juoksevan konfiguraation käynnistyvään konfiguraatiotiedostoon, jotta muutokset säilyvät uudelleenkäynnistyksen jälkeen.
- **Esimerkki:**
  ```
  R1# copy running-config startup-config
  ```

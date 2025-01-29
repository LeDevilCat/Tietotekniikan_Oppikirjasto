# Kytkimen MAC-osoitteiden tarkastelu

Tässä ohjeessa käsitellään, kuinka voit tarkastella ja hallita MAC-osoitteita Cisco-kytkimessä.

## **show mac address-table**
- **Selitys:** Näyttää kytkimen MAC-osoitetaulukon, joka sisältää kytkimen oppimat MAC-osoitteet ja niiden vastaavat portit.
- **Käyttö:**
  ```
  switch# show mac address-table
  ```
- **Esimerkki:**
  ```
  switch# show mac address-table
  ```
  Tämä näyttää kaikki MAC-osoitteet, jotka kytkin on oppinut.

## **clear mac address-table dynamic**
- **Selitys:** Tyhjentää kaikki dynaamisesti opitut MAC-osoitteet MAC-osoitetaulukosta.
- **Käyttö:**
  ```
  switch# clear mac address-table dynamic
  ```
- **Huom:** Kun MAC-osoitetaulukko on tyhjennetty, se alkaa täyttyä uudelleen, kun verkkoliikennettä vastaanotetaan.

## **show arp**
- **Selitys:** Näyttää ARP-taulukon, joka yhdistää MAC-osoitteet ja IP-osoitteet.
- **Käyttö:**
  ```
  switch# show arp
  ```

## **show interfaces f0/1**
- **Selitys:** Näyttää tietoa tietystä kytkimen portista, mukaan lukien sen MAC-osoite.
- **Käyttö:**
  ```
  switch# show interfaces f0/1
  ```

Näillä komennoilla voit tarkastella ja analysoida MAC-osoitteiden liikennettä verkossasi.


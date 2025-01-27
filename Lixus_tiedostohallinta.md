# Linux-tiedostohallinta

Tässä osiossa käydään läpi tärkeimpiä tiedostojen ja hakemistojen hallintaan liittyviä komentoja Linux-järjestelmässä. Ohjeet on laadittu erityisesti WSL-versiolle Ubuntusta.

## Peruskomennot

### **cd**
- **Käyttö:** `cd <hakemisto>`
- **Selitys:** Siirtyy toiseen hakemistoon.
- **Esimerkki:**
  ```bash
  cd projektit
  ```
  Siirtyy `projektit`-hakemistoon. Käytä `cd ..` siirtyäksesi ylöspäin hierarkiassa.

### **pwd**
- **Käyttö:** `pwd`
- **Selitys:** Näyttää nykyisen hakemiston polun.
- **Esimerkki:**
  ```bash
  pwd
  ```
  Komento voi palauttaa esimerkiksi `/home/user/projektit`, mikä kertoo, että olet `projektit`-hakemistossa.

### **ls**
- **Käyttö:** `ls [vaihtoehdot]`
- **Selitys:** Listaa hakemiston sisällön.
- **Esimerkkejä:**
  ```bash
  ls
  ls -l
  ls -a
  ```
  - `ls`: Näyttää hakemiston sisällön.
  - `ls -l`: Näyttää sisällön yksityiskohtaisesti.
  - `ls -a`: Sisältää myös piilotetut tiedostot.

### **tree**
- **Käyttö:** `tree`
- **Selitys:** Näyttää hakemiston rakenteen puumaisessa muodossa. Tämä komento ei välttämättä ole oletuksena asennettu, joten sen voi asentaa komennolla:
  ```bash
  sudo apt install tree
  ```
- **Esimerkki:**
  ```bash
  tree
  ```
  Tämä komento näyttää nykyisen hakemistorakenteen visuaalisesti.
### **mkdir**
- **Käyttö:** `mkdir <hakemistonimi>`
- **Selitys:** Luo uuden hakemiston.
- **Esimerkki:**
  ```bash
  mkdir projektit
  ```
  Tämä luo hakemiston `projektit`.

### **touch**
- **Käyttö:** `touch <tiedostonimi>`
- **Selitys:** Luo tyhjän tiedoston määritetyllä nimellä.
- **Esimerkki:**
  ```bash
  touch uusi_tiedosto.txt
  ```
  Tämä luo tiedoston `uusi_tiedosto.txt`.

### **mv**
- **Käyttö:** `mv <lähde> <kohde>`
- **Selitys:** Siirtää tai uudelleennimeää tiedoston tai hakemiston.
- **Esimerkki:**
  ```bash
  mv vanhanimi.txt uusi.txt
  ```
  Tämä uudelleennimeää tiedoston `vanhanimi.txt` nimeksi `uusi.txt`.
  Tiedoston siirtäminen toimii samalla tavalla kuin alla oleva **cp**

### **cp**
- **Käyttö:** `cp <lähde> <kohde>`
- **Selitys:** Kopioi tiedoston tai hakemiston.
- **Esimerkki:**
  ```bash
  cp tiedosto.txt varmuuskopiot/
  ```
  Tämä kopioi tiedoston `tiedosto.txt` hakemistoon `varmuuskopiot/`.

### **scp**
- **Käyttö:** `scp <tiedostonimi> käyttäjä@osoite:/kohdepolku`
- **Selitys:** Kopioi tiedoston paikalliselta koneelta etäkoneelle turvallisesti SSH-yhteyttä käyttäen.
- **Esimerkki:**
  ```bash
  scp tiedosto.txt student@[opiskelijan ip]:/home/student
  ```
  Tämä komento kopioi `tiedosto.txt`-tiedoston etäkoneelle hakemistoon `/home/student`.

### Tiedostojen valitseminen mv- ja cp-komennoilla

#### **Jokerimerkit (Wildcards)**
Jokerimerkit ovat hyödyllisiä, kun haluat valita useita tiedostoja tietyn kuvion perusteella.

- **`*`**: Vastaa mitä tahansa merkkijonoa.
  - **Esimerkki:** 
    ```bash
    cp *.txt varmuuskopiot/
    ```
    Tämä kopioi kaikki `.txt`-päätteiset tiedostot nykyisestä hakemistosta `varmuuskopiot/`-hakemistoon.

- **`?`**: Vastaa yhtä merkkiä.
  - **Esimerkki:**
    ```bash
    mv tiedosto?.txt kohdehakemisto/
    ```
    Tämä siirtää tiedostot, joiden nimet alkavat `tiedosto` ja päättyvät yhteen merkkiin, kuten `tiedosto1.txt` ja `tiedosto2.txt`.

#### **Hakemistorakenne (Recursive)**
- Lisää **`-r`**-vaihtoehto kopiointiin hakemistojen siirtämiseksi:
  ```bash
  cp -r hakemisto kohde/
  ```
  Tämä kopioi koko hakemiston ja sen sisällön.

#### **Valikoiva valinta tiedostonimien perusteella**
- Valitse vain tiettyjä tiedostoja:
  ```bash
  mv tiedosto1.txt tiedosto2.txt kohdehakemisto/
  ```
  Tämä siirtää `tiedosto1.txt` ja `tiedosto2.txt` määriteltyyn hakemistoon.

---

  ### explorer.exe -komennon käyttö WSL:ssä

**explorer.exe**-komennolla voit avata WSL-hakemiston Windowsin Resurssienhallinnassa.

#### **Käyttö**
- **Komento:** 
  ```bash
  explorer.exe .
  ```
  Tämä avaa nykyisen hakemiston Windowsin Resurssienhallinnassa. 

#### **Esimerkki**
1. Siirry haluttuun hakemistoon:
   ```bash
   cd /mnt/c/users/oma_hakemisto
   ```
2. Avaa hakemisto Windowsin Resurssienhallinnassa:
   ```bash
   explorer.exe .
   ```

Windows Resurssienhallinta avautuu ja näyttää valitun hakemiston sisällön. Tämä komento on erityisen hyödyllinen, kun haluat käyttää WSL-hakemistoja Windowsin puolella.

Nämä komennot auttavat sinua hallitsemaan tiedostoja ja hakemistoja tehokkaasti Linux-ympäristössä. Muista aina tarkistaa oikeudet, jos kohtaat ongelmia tiedostojen käsittelyssä.


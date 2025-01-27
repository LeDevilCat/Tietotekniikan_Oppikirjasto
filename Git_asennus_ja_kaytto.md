# Git ja GitHub - Asennus ja Komentojen Käyttö

## **Gitin asentaminen**

### Windows
1. **Lataa Git-asennuspaketti** [Git for Windows](https://git-scm.com/).
2. **Suorita asennusohjelma** ja valitse seuraavat asetukset:
   - Valitse oletuseditoriksi esimerkiksi "Nano" tai "Vim".
   - Ota "Git from the command line" -vaihtoehto käyttöön.
   - Hyväksy muut oletusasetukset ja suorita asennus loppuun.

### Linux
1. **Avaa terminaali** ja suorita seuraava komento:
   ```bash
   sudo apt update && sudo apt install git
   ```
2. Varmista asennus tarkistamalla Gitin versio:
   ```bash
   git --version
   ```

### macOS
1. **Asenna Homebrew (jos sitä ei ole jo asennettu):**
   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```
2. **Asenna Git Homebrewin avulla:**
   ```bash
   brew install git
   ```
3. Tarkista asennus:
   ```bash
   git --version
   ```

---

## **Gitin perusasetukset**
Ennen kuin alat käyttää Gitiä, sinun tulee määrittää käyttäjätiedot.

### Aseta käyttäjänimi ja sähköposti
```bash
git config --global user.name "Oma Nimi"
git config --global user.email "sahkoposti@esimerkki.com"
```

### Varmista asetukset
```bash
git config --list
```

---

## **Git-komennot**
Alla on yleisimmin käytetyt Git-komennot ja niiden selitykset.

### **Git-repositorion luominen**

1. **Alusta uusi repositorio:**
   ```bash
   git init
   ```
2. **Kloonaa olemassa oleva repositorio GitHubista:**
   ```bash
   git clone [URL]
   ```

### **Tiedostojen hallinta**

1. **Lisää tiedostoja seurattavaksi:**
   ```bash
   git add [tiedosto]
   ```
   - Lisää kaikki tiedostot:
     ```bash
     git add .
     ```

2. **Tallenna muutokset (commit):**
   ```bash
   git commit -m "Viesti muutoksista"
   ```

3. **Poista tiedosto:**
   ```bash
   git rm [tiedosto]
   ```

### **Muutosten tarkastelu**

1. **Tarkastele tiedostojen tilaa:**
   ```bash
   git status
   ```

2. **Näytä erot nykyisen ja viimeisen commitin välillä:**
   ```bash
   git diff
   ```

3. **Näytä commit-historia:**
   ```bash
   git log
   ```

### **Muutosten julkaiseminen**

1. **Yhdistä paikallinen repositorio etärepoon:**
   ```bash
   git remote add origin [URL]
   ```

2. **Lähetä muutokset etärepositorioon:**
   ```bash
   git push origin main
   ```

3. **Hae muutokset etäreposta paikallisesti:**
   ```bash
   git pull origin main
   ```

---

## **Lisää resursseja**
Seuraavassa Git-komentojen täydellinen luettelo: [Joshnh Git Commands](https://github.com/joshnh/Git-Commands)

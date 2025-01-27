# Git-palvelimen linkittäminen ja SSH-avaimen luominen

## **Git-palvelimen linkittäminen**

Git-projektit voidaan yhdistää etäpalvelimiin, kuten GitHubiin tai GitLabiin, julkaisemista ja versionhallintaa varten.

### Vaihe 1: Etäpalvelimen lisääminen

1. **Luo uusi repositorio palvelimelle (esim. GitHub/GitLab):**
   - Siirry palveluun ja valitse "New Repository".
   - Anna projektille nimi ja määrittele näkyvyysasetukset (public/private).

2. **Linkitä paikallinen repositorio etäpalvelimeen:**
   ```bash
   git remote add origin [URL]
   ```
   - Korvaa `[URL]` etärepositorion HTTPS- tai SSH-linkillä, joka näkyy palvelimen käyttöliittymässä.
   
3. **Varmista etäpalvelimen linkitys:**
   ```bash
   git remote -v
   ```
   Tuloste näyttää etäpalvelimen osoitteet, esim.:
   ```
   origin  git@github.com:kayttaja/projekti.git (fetch)
   origin  git@github.com:kayttaja/projekti.git (push)
   ```

### Vaihe 2: Muutosten lähettäminen etäpalvelimeen

1. **Tallenna muutokset paikalliseen repositorioon:**
   ```bash
   git add .
   git commit -m "Ensimmäinen commit"
   ```

2. **Lähetä muutokset etäpalvelimeen:**
   ```bash
   git push -u origin main
   ```
   - `-u`: Asettaa oletushaaraksi `origin/main`, jolloin jatkossa voit käyttää yksinkertaista `git push` -komentoa.

---

## **SSH-avaimen luominen ja käyttöönotto**

SSH-avaimet tarjoavat turvallisen ja salasanattoman tavan yhdistää Git-palvelimiin.

### Vaihe 1: Tarkista olemassa olevat avaimet

1. **Avaa terminaali ja tarkista, onko järjestelmässä jo SSH-avain:**
   ```bash
   ls -al ~/.ssh
   ```
   - Jos kansiossa näkyy tiedostot kuten `id_rsa` ja `id_rsa.pub`, sinulla on jo olemassa SSH-avain.

### Vaihe 2: Luo uusi SSH-avain

1. **Suorita seuraava komento:**
   ```bash
   ssh-keygen -t ed25519 -C "sahkoposti@esimerkki.com"
   ```
   - Korvaa "sahkoposti@esimerkki.com" omalla sähköpostiosoitteellasi.
   - Jos ed25519 ei ole tuettu, käytä RSA-algoritmia:
     ```bash
     ssh-keygen -t rsa -b 4096 -C "sahkoposti@esimerkki.com"
     ```

2. **Tallenna avain oletuspaikkaan:**
   - Kun komento kysyy tiedostonimeä, paina vain `Enter` tallentaaksesi avaimen polkuun `~/.ssh/id_ed25519`.

3. **Aseta salasanavaihtoehto (valinnainen):**
   - Voit syöttää salasanan, tai jättää sen tyhjäksi (painamalla `Enter`).

### Vaihe 3: Ota avain käyttöön

1. **Käynnistä SSH-agentti:**
   ```bash
   eval "$(ssh-agent -s)"
   ```

2. **Lisää avain SSH-agenttiin:**
   ```bash
   ssh-add ~/.ssh/id_ed25519
   ```

### Vaihe 4: Lisää julkinen avain Git-palveluun

1. **Näytä julkinen avain:**
   ```bash
   cat ~/.ssh/id_ed25519.pub
   ```

2. **Kopioi avaimen sisältö.**

3. **Lisää avain GitHubiin tai GitLabiin:**
   - **GitHub:**
     - Siirry kohtaan **Settings > SSH and GPG keys > New SSH key**.
     - Liitä avaimen sisältö ja tallenna.
   - **GitLab:**
     - Siirry kohtaan **Preferences > SSH Keys**.
     - Liitä avaimen sisältö ja tallenna.

### Vaihe 5: Testaa yhteys

1. **Testaa yhteys Git-palvelimeen:**
   ```bash
   ssh -T git@github.com
   ```
   - Vaihda `github.com` palvelun mukaan (esim. `gitlab.com`).

2. **Jos yhteys toimii, näet viestin kuten:**
   ```
   Hi [username]! You've successfully authenticated, but GitHub does not provide shell access.
   ```

---

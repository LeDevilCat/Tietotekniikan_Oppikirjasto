# Nettisivujen vieminen palvelimeen (IoT ja Web-ohjelmointi):

## Tämä ohje olettaa seuraavat asiat:
- Olet tehnyt erillisen kansion (esim. week_05) tehtävänannon mukaisesti
- Kansio sisältää ainakin yhden .html-tiedoston
- Olet asentanut OpenVPN:n

## VAIHE 1: Avaa terminaalit:

**Avaa terminaali** (TER 1) ja navigoi hakemistoon (käyttämällä 'cd'-komentoja), jossa luomasi "week_XX"-kansio sijaitsee. Jos olet luonut kansion paikallisesti, voit käyttää Windowsin päätettä.
```
C:\Users\user\iot-ja-web\nettisivu>  // Esimerkkisijainti
```
**Jos olet tehnyt kansion Ubuntuun**, tee tämä vaihe Ubuntu-terminaalissa.
```
user@UserPC:~/iot-ja-web/nettisivu$  // Esimerkkisijainti
```
## VAIHE 2: Kirjaudu palvelimeen
**Avaa toinen terminaali** (TER 2), jota käytät palvelinta varten. Esim. **Git Bash** tai **Windowsin pääte**.

> [!IMPORTANT]
> Varmista, että olet yhdistänyt OpenVPN:ään tai SOURCE-verkkoon!

Kirjaudu palvelimeen sinulle osoitetulla IP-osoitteella:
```
ssh student@IP_OSOITTEESI
```
*Jos et tiedä IP-osoitettasi, etkä löydä sitä kurssin Moodle-sivulta, pyydä opettajaltasi apua.*  

---
Kun olet kirjautunut palvelimelle onnistuneesti, siirry seuraavaan vaiheeseen.

## VAIHE 3: Vie tehtävät palvelimelle
Palaa ensimmäiseen terminaaliin (TER 1) ja kopioi kansio palvelimeen käyttämällä komentoa...  
...Windows päätteessä:
```
scp -r week_XX student@IP_OSOITE:/home/student
```
...Ubuntu-terminaalissa:
```
rsync -av week_XX student@IP_OSOITE:/home/student
```
> [!IMPORTANT]
> Muista vaihtaa week_XX haluamaksesi kansioksi ja IP_OSOITE omaasi!
---
**Jos kaikki onnistui**, voit siirtyä [**vaiheeseen 4.**](#VAIHE-4:-siirrä-kansio-nettisivullesi)

---
Mikäli komento ei suoriutunut oikein, tarkista ensin komennon oikeinkirjoitus. Jos et vieläkään saanut kansiota vietyä palvelimeen, jatka tämän vaiheen ohjeiden seuraamista.

---
### Vaihtoehtoinen tapa
Avaa terminaali, jolla kirjauduit palvelimeen (TER 2).
> [!IMPORTANT]
> Varmista, että olet "student" -hakemistossa! (Aloitushakemisto)

Luo uusi kansio komennolla:
```
mkdir week_XX
```
---
Avaa ensimmäinen terminaali (TER 1) ja siirry week_XX kansioon:
```
cd week_XX 
```
Kopioi kansion sisältö palvelimeen komennolla:
```
scp * student@IP_OSOITE:/home/student/week_XX
```
---
Nyt tiedostojen pitäisi olla palvelimen puolella. Jos jostain syystä tämäkään ei toiminut, varmista komentojen oikeinkirjoitus tai kysy apua opettajalta/Googlelta/tekoälyltä.

## VAIHE 4: Siirrä kansio nettisivullesi

Avaa palvelimen terminaali (TER 2) ja kirjoita seuraava komento:
```
sudo mv week_XX ../../var/www/html
```
Edellä mainittu komento siirtää "week_XX"-kansion hakemistoon, jossa verkkosivusi sijaitsee.

---
Tarkista toimivuus kirjoittamalla selaimeen: IP_OSOITTEESI/week_XX  
Jos "week_XX"-kansion index.html ei toimi selaimessa:
- Tarkista osoitteen oikeinkirjoitus
- Varmista, että "week_XX"-kansion rakenne on tehty tehtävänannon mukaisesti
- Varmista, että seurasit tämän oppaan vaiheita oikein

## That's all folks!

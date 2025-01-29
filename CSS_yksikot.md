# CSS-yksiköt ja niiden selitykset

CSS:ssä käytetään erilaisia yksiköitä määrittämään elementtien mittoja, kuten leveyttä, korkeutta, reunuksia ja fonttikokoja. Nämä yksiköt jaetaan kahteen pääryhmään: absoluuttisiin ja suhteellisiin yksiköihin.

## **Absoluuttiset yksiköt**
Absoluuttiset yksiköt edustavat kiinteitä mittoja, jotka eivät muutu suhteessa muihin elementteihin tai ympäristöön.

- **tuuma (in)**: 1 in = 25,4 mm
- **senttimetri (cm)**: 1 cm = 10 mm
- **millimetri (mm)**: 1 mm = 1 mm
- **piste (pt)**: 1 pt = 1/72 tuumaa ≈ 0,3528 mm
- **pica (pc)**: 1 pc = 12 pt ≈ 4,233 mm

Huom: Näiden yksiköiden tarkka fyysinen koko voi vaihdella näytön tarkkuuden ja laitteiston mukaan.

## **Suhteelliset yksiköt**
Suhteelliset yksiköt määrittyvät suhteessa muihin arvoihin, kuten vanhemman elementin kokoon tai näkymän kokoon.

- **prosentti (%)**: Suhteessa vanhemman elementin vastaavaan arvoon.
- **em**: 1em = nykyisen elementin fonttikoko.
- **rem**: 1rem = juurielementin (`<html>`) fonttikoko.
- **vw**: 1vw = 1% näkymän leveydestä.
- **vh**: 1vh = 1% näkymän korkeudesta.
- **vmin**: 1vmin = 1% näkymän pienemmästä dimensiosta (leveys tai korkeus).
- **vmax**: 1vmax = 1% näkymän suuremmasta dimensiosta (leveys tai korkeus).

Suhteelliset yksiköt mahdollistavat responsiivisen suunnittelun, koska ne mukautuvat eri näyttökokoihin ja laitteisiin.

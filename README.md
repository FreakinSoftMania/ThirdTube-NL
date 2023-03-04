# ThirdTube-NL

Een in werk voortgang homebrew YouTube client voor de 3DS in het Nederlands vertaald  
[GBAtemp-thread](https://gbatemp.net/threads/release-thirdtube-a-homebrew-youtube-client-for-the-new-3ds.591696/)  
[Discord-server (alleen Engels)](https://discord.gg/CVcThBCQJM)

## Instabiliteitswaarschuwing

Omdat deze app zich nog in de alfafase bevindt, kunt en zult u crashes en andere bugs tegenkomen.
Als je er een vindt, zou het handig zijn om een probleem te openen in deze GitHub-repository.

## Beschrijving
Het maakt gebruik van een aantal niet-gedocumenteerde YouTube-API's om de onbewerkte video-URL te krijgen en speelt de stream af met behulp van de decoder uit [Video player for 3DS by Core-2-Extreme](https://github.com/Core-2-Extreme/Video_player_for_3DS) .
Het voert geen javascripts uit en geeft geen html/css weer, dus het is aanzienlijk sneller dan YouTube in de browser.
De naam is afgeleid van het feit dat het de derde YouTube-client op 3DS is, na de officiële YouTube-app (stopgezet) en de nieuwe 3DS-browser.

## QR code
U kunt de onderstaande qr-code gebruiken om .cia van 3ds te downloaden en te installeren (Dank aan @Minionguyjpro)
<img src="./images/qr_code.png" width="200" height="200">

## Schermafbeeldingen
<img src="./images/0.jpg" width="400" height="480"> ![](./images/1.bmp)  
![](./images/3.bmp) ![](./images/4.bmp)  

## Functies

  - Videoweergave tot 360p
    480p zou mogelijk kunnen zijn en zou kunnen worden overwogen in de toekomstige ontwikkeling
  - Ondersteuning voor livestreams en premièrevideo's
  - Zoeken
  - Video-suggestie
  - Opmerkingen
  - Onderschriften
  - Lokale kijkgeschiedenis en kanaalabonnement
  - Geen advertenties
    Het is meer zoiets als "Advertenties zijn niet geïmplementeerd" in plaats van "We hebben functionaliteit voor het blokkeren van advertenties".
    Natuurlijk zal ik het nooit "implementeren" :) 

## Bediening

  - B-knop: ga terug naar de vorige scène
  - C-pad omhoog/omlaag: scrollen
  - L/R: schakelen tussen tabbladen
  - Select + Start: maak het onderste scherm zwart
  - In videospeler
     - Pijl links/rechts: 10 s zoeken

Hieronder staan voor foutopsporingsdoeleinden

  - Select + X: debug log in-/uitschakelen
  - Select + Y: schakel geheugengebruiksmonitor in
  - Select + R + A: schakel FPS-monitor in

## Vereisten
Een 3DS (inclusief 2DS) met [Luma3DS](https://github.com/LumaTeam/Luma3DS) geïnstalleerd en [DSP1](https://github.com/zoogie/DSP1) uitgevoerd.
Ik heb de minimale systeemversie niet getest, maar er is minimaal 8.1.0-0 nodig.

## Veelgestelde vragen

  - Is het logisch?
    De **slechtste** vraag in de homebrew-scène van de console. Is het niet gewoon spannend om je favoriete video's te zien spelen op een 3DS?

## Bouwen
U heeft nodig:

  - devkitPro met devkitARM r58
  - ```3ds-zlib``` en ```3ds-mbedtls``` geïnstalleerd in portlibs van devkitPro
    U kunt het installeren door devkitPro msys2 te openen en ```pacman -S [pakketnaam]``` te typen.

Type ```make``` (als je Linux gebruikt) of ```make all_win``` (als je Windows gebruikt) om het te bouwen.

  - Bouwen van afhankelijkheidsbibliotheken (optioneel)
    Voor ffmpeg, libbrotli en libcurl volgt u built.txt in elke map
    Typ voor libctru ```make``` in library\libctru\source\libctru

## Licentie
U kunt de code gebruiken onder de voorwaarden van de GNU General Public License GPL v3 of onder de voorwaarden van eventuele latere herzieningen van de GPL. Raadpleeg het meegeleverde LICENSE-bestand voor meer informatie.

## Licenties van derden

### [FFmpeg](https://ffmpeg.org/)
door de FFmpeg-ontwikkelaars onder GNU Lesser General Public License (LGPL) versie 2.1
De gewijzigde broncode is te vinden op https://github.com/windows-server-2003/FFmpeg/tree/3ds.
### [rapidjson](https://github.com/Tencent/rapidjson)
door Tencent en Milo Yip onder MIT-licentie
### [libctru](https://github.com/devkitPro/libctru)
door devkitPro onder zlib-licentie
### [libcurl](https://curl.se/)
door Daniel Stenberg en vele medewerkers onder de curl-licentie
### [libbrotli](https://github.com/google/brotli)
door de Brotli-auteurs onder MIT-licentie
### [stb](https://github.com/nothings/stb/)
door Sean Barrett onder MIT-licentie en publiek domein

## Credits
* Core 2 Extreme
   Voor [Videospeler voor 3DS](https://github.com/Core-2-Extreme/Video_player_for_3DS) waarop deze app is gebaseerd.
   Het behoeft geen betoog dat de functionaliteit voor het afspelen van video's essentieel is voor deze app, en het zou niet mogelijk zijn geweest om deze software te ontwikkelen zonder dat hij zijn tijd besteedde aan het optimaliseren van de code, soms zelfs met montage en het onderzoeken van HW-decodering op de nieuwe 3DS.
* dixy52-peep
   Voor in-app-texturen
* [PokeTube](https://github.com/Poketubepoggu)
   Voor het pictogram en de banner
* De bijdragers van [youtube-dl](https://github.com/ytdl-org/youtube-dl)
   Als referentie over het parseren van YouTube-webpagina's. Het was vooral handig voor het deobfusceren van gecodeerde handtekeningen.
* De bijdragers van [pytube](https://github.com/pytube/pytube)
   Als referentie over het parseren van YouTube-webpagina's. Dankzij het strikte afhankelijkheidsvrije beleid kon ik zonder problemen een deel van de code porteren.

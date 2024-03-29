spatialsuite-matomo
=============================

Modul til tracking af SpatialSuite i [matomo](https://matomo.org/)  

[Septima](http://www.septima.dk) v/ Klavs Pihlkjær. klavsATseptima.dk    

Der registreres et enkelt pageview per session, herudover registreres
* tryk på knapper og menuer,  
* kort-opløsning, samt  
* tænd/sluk af temaer  

som handlinger (events) i matomo
  
  
__Før installation__

I matomo oprettes og konfigureres en konto. Informationer fra opsætningen af denne konto skal bruges i konfigurationen af modulet. Se nedenfor

INSTALLATION
--------------------

1:    Download og udpak https://github.com/Septima/spatialsuite-matomo/archive/0.5.0.zip  
1.a:  Kopiér og omdøb folderen "spatialsuite-matomo-0.5.0" til [cbinfo.config.dir]/modules/thirdparty/septima/matomo.  
1.b:  Skriv følgende i modules.xml:
```xml
<module name="matomo" dir="thirdparty/septima/matomo"/>.
```

2  :  Inkludér toolet i profile.xml. (Evt i include-fil så det automatisk kommer med i alle profiler)
```xml
<tool module="matomo" name="matomo-plugin"/>
```

3  :  Inkludér cbinfo-parametre

3.a:  Obligatoriske parametre:
```xml
<!-- =================================== -->
<!-- Matomo                              -->
<!-- =================================== -->
  <!--siteurl: Din piwik-installation. Eksempelvis piwik.nyby.dk -->
  <param name="module.matomo.siteurl">xxxxx.xxx.xxx/</param>
    
  <!--siteid: Det id som sitet har i matomo. Eksempelvis 1 (Kan ses som 'idSite' når man er inde i matomo)-->
  <param name="module.matomo.siteid">XX</param>
```
3.b:  Skal oplysninger om brugeren gemmes? (Valgfri parameter)  
Brugerens id gemmes som attribut på pageviewet og efterfølgende events i matomo  
```xml
<param name="module.matomo.storeprincipal">true</param>
```

3.b:  Undlad at bruge cookies (Valgfri parameter)  
Brugeren trackes ikke, dvs der vil blive registreret ny bruger hvergang sitet reloades. Alle handlinger (events) registreres korrekt, men de vil ikke kunne henføres til en brugers opførsel på sitet  
```xml
<param name="module.matomo.no-cookie">true</param>
```


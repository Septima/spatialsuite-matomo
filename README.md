spatialsuite-matomo
=============================

Matomo modul

Septima v/ Klavs P. Christensen. klavsATseptima.dk  
www.septima.dk

Før installation

I Matomo oprettes og konfigureres en konto. Informationer fra opsætningen af denne konto skal bruges i konfigurationen af modulet. Se nedenfor

--------------------
INSTALLATION
--------------------

1:    Download modulet https://github.com/Septima/spatialsuite-matomo/archive/0.1.0.zip  
1.a:  Kopiér modulet "matomo" til [cbinfo.config.dir]/modules/thirdparty/septima/matomo.  
1.b:  Skriv følgende i modules.xml:
```xml
<module name="matomo" dir="thirdparty/septima/matomo"/>.
```

2  :  Inkludér toolet i profile.xml. (Evt i include-fil så det automatisk kommer med i alle profiler)
```xml
<tool module="matomo" name="matomo-plugin"/>
```

3  :  Inkludér cbinfo-parametre

3.a:  Matomo parametre:
```xml
<!-- =================================== -->
<!-- Matomo                              -->
<!-- =================================== -->
  <!siteurl: Det navn som sitet har i matomo. Eksempelvis webkort.nyby.dk -->
  <param name="module.matomo.siteurl">xxxxx.xxx.xxx/</param>
    
  <!siteid: Det id som sitet har i matomo. Eksempelvis 1 (Kan ses som 'idSite' når man er inde i matomo)-->
  <param name="module.matomo.siteid">XX</param>
```
3.b:  Skal oplysninger om brugeren gemmes?:
```xml
<param name="module.matomo.storeprincipal">true</param>
```

3.b:  Undlad at bruge cookies: (Brugeren trackes ikke, dvs der vil blive registreret ny bruger hvergang sitet reloades. Alle events er korrekte, men de vil ikke kunne henføres til en brugers opførsel på sitet)  
```xml
<param name="module.matomo.no-cookie">true</param>
```


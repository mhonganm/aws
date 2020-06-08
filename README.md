# aws
Tämä Koodi luo Linux instanssin ja lisää siihen Apachen webserverin ja siihen uuden aloitus-sivun. 

- VPC ja subnet pitää olla jo aikaisemmin luotuna (testattu default VPC:llä)
- KeyPair pitää olla jo aikaisemin luotuna
- Instanssille sallitaan SSH määriteltävästä avaruudesta x.x.x.x/x
- Sallitut instanssi muodot, jos tarvitset listan ulkopuolelta jotain, lisää se koodiin mukaan
      - t2.micro
      - t2.medium
      - t3.micro
      - t3.medium
      - t3.large
- Oletuksena käytetään viimeisintä Amazon linux distron imagea, muuta koodia jos haluat jotain muuta
- SecurityGroup joka sallii liikenteen julki internettiin sekä hallinnan ja pingin aikaisemmin määritetystä osoitteesta
- Metadatassa asennetaan Yumin avulla httpd paketti (apache) ja lisätään sinne erillinen index.html tiedosto
- Apache käynnistetään ja asetetaan käynnistymään automaattisesti   
- Roolit
  - InstancePatchingRole (Rooli joka sallii Systems Manager yhteyden päivityksiä varten)  
  - PatchingInstanceProfile (Rooli joka sallii Kriittisten päivitysten automaattisen asennuksen)
  - MaintenanceWindowRole (Rooli päivitysten aikaikkunalle)
- Päivitykset ajastettu tapatuvaksi joka päivä kello 17 
- Output tietoina tulee palvelimen URL ja IP tiedot

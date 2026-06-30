# IoT Hardware – Composants du Gilet Haptique (Phase 2)

## 1. Objectif

Concevoir un gilet haptique DIY avec :
- 4 zones de vibration
- communication BLE avec Unity (Meta Quest 3)
- retour haptique (impacts, météo, interactions)

---

## 2. Architecture globale

Unity (Quest 3)
→ BLE
→ ESP32
→ Drivers
→ Moteurs vibrants

---

## 3. Liste des composants

---

## 3.1 Microcontrôleur

### ESP32 DevKit (ESP32-WROOM-32)

- Référence : ESP32 DevKit V1 / ESP32-WROOM-32
- Connectivité : WiFi + Bluetooth (BLE)
- Tension : 3.3V
- Interfaces : GPIO, PWM, I2C, SPI

Exemple :
[ESP32 DevKit (ESP32-WROOM-32)] Coût 5,79€ TTC

https://fr.aliexpress.com/item/1005006023774611.html?isdl=y&aff_fsk=_om02Uef&src=RedbrainFR&aff_platform=aff_feeds&aff_short_key=_om02Uef&pdp_npi=4%40dis%21EUR%213.19%213.19%21%21%21%21%21%40%2112000035367991718%21afff%21%21%21&dp=CjwKCAjw-8vPBhBbEiwAoA39WqukZUPlZRrS6YwDsX2rLK33GdAQl5p-4MdAw7DwgGgzdyCHrmhpiBoCFZQQAvD_BwE 


Justification :
- BLE natif → communication directe avec Unity
- faible coût
- standard IoT
- très grande communauté  [oai_citation:0‡Random Nerd Tutorials](https://randomnerdtutorials.com/getting-started-with-esp32/?utm_source=chatgpt.com)

---

## 3.2 Drivers haptiques

### DRV2605L – Haptic Driver

- Référence : DRV2605L Breakout
- Communication : I2C
- Support : moteurs ERM et LRA
- Effets intégrés : oui (patterns)

Exemple :
[DRV2605L Breakout Board] Coût 4,99€

https://fr.aliexpress.com/item/1005012030053554.html?src=google&src=google&albch=shopping&acnt=248-630-5778&isdl=y&slnk=&plac=&mtctp=&albbt=Google_7_shopping&aff_platform=google&aff_short_key=UneMJZVf&gclsrc=aw.ds&albagn=888888&ds_e_adid=&ds_e_matchtype=&ds_e_device=c&ds_e_network=x&ds_e_product_group_id=&ds_e_product_id=fr1005012030053554&ds_e_product_merchant_id=5069261870&ds_e_product_country=FR&ds_e_product_language=fr&ds_e_product_channel=online&ds_e_product_store_id=&ds_url_v=2&albcp=19000710609&albag=&isSmbAutoCall=false&needSmbHouyi=false&gad_source=1&gad_campaignid=17725339642&gclid=Cj0KCQjwh-HPBhCIARIsAC0p3cfZn7lZE0stBu14WkwEqW1ZwnKlj1iykqL3d-5m-nqLq89YKJ83OosaAtfyEALw_wcB

Justification :
- génération d’effets haptiques avancés
- gestion fine des vibrations
- proche des systèmes utilisés en VR

---

## 3.3 Actionneurs (moteurs vibrants)

### ERM Coin Vibration Motor

- Type : ERM (Eccentric Rotating Mass)
- Tension : 3V
- Diamètre : 8mm ou 10mm

Exemples :
[ERM Coin Vibration Motor 8mm] 1€ les 10 pièces

https://fr.aliexpress.com/item/1005006866794218.html?src=google&src=google&albch=shopping&acnt=248-630-5778&isdl=y&slnk=&plac=&mtctp=&albbt=Google_7_shopping&aff_platform=google&aff_short_key=UneMJZVf&gclsrc=aw.ds&albagn=888888&ds_e_adid=&ds_e_matchtype=&ds_e_device=c&ds_e_network=x&ds_e_product_group_id=&ds_e_product_id=fr1005006866794218&ds_e_product_merchant_id=107882406&ds_e_product_country=FR&ds_e_product_language=fr&ds_e_product_channel=online&ds_e_product_store_id=&ds_url_v=2&albcp=19000710609&albag=&isSmbAutoCall=false&needSmbHouyi=false&gad_source=1&gad_campaignid=17725339642&gclid=Cj0KCQjwh-HPBhCIARIsAC0p3cdtwHVH8rvbdmsjj0EUFczg1VMQQn76gd3iHWvcRHn8GFnNmG6XAJYaAt8KEALw_wcB
z

Justification :
- simple à intégrer
- robuste
- bon compromis coût/performance
- suffisant pour prototype VR

---

## 3.4 Alimentation

### Batterie LiPo 3.7V

- Capacité recommandée : 2000 mAh
- Tension : 3.7V

Exemples :
[Batterie LiPo 3.7V 2000mAh] Coût 2,61€

https://fr.aliexpress.com/item/1005009606905538.html?aff_fsk=_oD4bq9e&aff_platform=aff_feeds&aff_short_key=_oD4bq9e&cn=318473&cv=a5930b23d6663d1663e90cd684112080&dp=17775379596350755847619531197008005&isdl=y&src=Connexity&pdp_npi=4%40dis%21EUR%214.74%212.61%21%21%21%21%21%40%2112000049612685284%21afff%21%21%21


---

### Module de charge

### TP4056

- Entrée : USB 5V
- Sortie : 3.7V LiPo
- Protection intégrée

Exemples :
[TP4056 Charge Module] Coût 4,69€

https://www.aliexpress.com/p/tesla-landing/index.html?src=google&exp_tag=pcgcp&key=ggEu&src=google&albch=shopping&acnt=364-871-7393&slnk=&plac=&mtctp=&albbt=Google_7_shopping&gclsrc=aw.ds&albagn=888888&ds_e_adid=795091124544&ds_e_matchtype=search&ds_e_device=c&ds_e_network=g&ds_e_product_group_id=2519523722327&ds_e_product_id=fr1005009818913119&ds_e_product_merchant_id=5716905007&ds_e_product_country=FR&ds_e_product_language=fr&ds_e_product_channel=online&ds_e_product_store_id=&ds_url_v=2&albcp=23509535010&albag=194069405964&isSmbAutoCall=false&needSmbHouyi=false&gad_source=1&gad_campaignid=23509535010&gclid=CjwKCAjw-8vPBhBbEiwAoA39WmwaZR-tPkLQyKVr9RgQGCgSPShy17ZrWZZ8LLSIB9s9oQ4TR76JXBoC8ZMQAvD_BwE&aff_fcid=e3b0eb2448534ed7b87f68f6e85d25bf-1777538400435-02569-irey5Th&aff_fsk=irey5Th&aff_platform=promotion&sk=irey5Th&aff_trace_key=e3b0eb2448534ed7b87f68f6e85d25bf-1777538400435-02569-irey5Th&terminal_id=32209723d9f24e2d903f4285c7e1e3a3&scenario=c_ppc_item_bridge&productId=1005009818913119&_immersiveMode=true&withMainCard=true&OLP=1128500808_f&o_s_id=1128500808&afSmartRedirect=n

---

## 3.5 Support physique

### Gilet tactique MOLLE

- Type : porte-plaques / gilet tactique
- Fixation : velcro / sangles MOLLE

Exemples :
[Gilet tactique MOLLE] Coût 16,88€

https://fr.shein.com/goods-p-393020893.html?goods_id=393020893&test=5051&url_from=adhub2017142732124123136&scene=1&pf=google&ad_type=DPA&language=fr&siteuid=fr&version_bid=102311026,102310816,102353676,102310681,102310801&version_eid=100902896&landing_page_id=1510&ad_test_id=49155&requestId=olw-5okl8soebc4t&cid=23509367742&gad_source=1&network=g&gad_campaignid=23509367742&adid=795194251676&tv_b=2&activity_id=5051&currency=EUR&lang=fr&skucode=I5mkzeek0ty9ty&product_set_id=25917&onelink=0/googlefeed_fr&gclid=Cj0KCQjwh-HPBhCIARIsAC0p3ceLZAGGmOonCA7UmVXGvUB4Zi84KoLKWtqWHtuN8P6hIccLlRcCH8waAkKXEALw_wcB&ismg=9e836a1919e7eb4a6bdef89dc3750bcd3bba949f0e79706d03931c9fad2477cd_01_1777890654&geoid=9213519&setid=195543855994&kwd=pla-2464276837328

Justification :
- structure stable
- modulable
- idéal pour prototypage

---

## 3.6 Connectique & accessoires

### Câblage
- câbles Dupont (M/F)
- fils électriques souples

### Fixation
- velcro industriel
- supports imprimés 3D (optionnel)

### Sécurité
- interrupteur ON/OFF
- fusible (optionnel)

---

## 4. Répartition des capteurs

Configuration Phase 2 (4 zones) :

- Épaule gauche
- Épaule droite
- Poitrine gauche
- Poitrine droite

Objectif :
- localisation des impacts
- immersion VR
- feedback directionnel

---

## 5. Communication

### BLE (Bluetooth Low Energy)

ESP32 ↔ Unity (Meta Quest 3)

Avantages :
- faible latence
- connexion directe
- pas besoin de backend

---

## 6. Coût Devis

- Via AliExpress : 5,79 + 4,69

---

## 7. Fonctionnalités attendues

- vibration lors d’un choc
- feedback lors interaction PNJ
- simulation météo (pluie, vent)
- retour directionnel (gauche/droite)

---

## 8. Évolutions futures

Phase 3 :
- 8 à 12 capteurs

Phase 4 :
- 16 à 40 capteurs (type bHaptics)

---

## 8. Conclusion

Cette architecture permet :

- un prototype fonctionnel
- une forte valeur pédagogique
- une intégration complète VR + IoT
- une évolutivité vers des systèmes avancés
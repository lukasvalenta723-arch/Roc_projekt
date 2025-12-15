# Roc_projekt

Cíl mého ročníkového projektu:

  - Cílem mého ročníkového projektu je motorizace a kompletní el. osvětlení plastikového modelu bombardéru B-17 od značky Eduard v měřítku 1/48. Jako hlavní zdroj inspirace mi posloužilo jedno YouTube video, které
    jsem viděl před 5-6 lety, a bylo jedním z hlavních důvodů, proč mě tento můj koníček tehdy tak moc zaujal. Proto jsem si na něj vzpomněl po letech u příležitosti tohoto Ročníkového projektu. Každopádně, ve
    zkratce se ve videu detailně ukazuje postup kompletní stavby a úpravy modelu letounu Douglas DC-3 v měřítku 1/48, přičemž je  kladen důraz na zahrnutí kompletního přistávacího, interiérového a ocasního
    osvětlení a motorizaci vrtulí s použitím mikroelektroniky. V případě zájmu je originální video, ze kterého jsem se inspiroval uvedeno v sekci Citace a odkazy.

Hlavní cíle projektu:

  - Nainstalovat a zapojit čtyři bezjádrové motory napájené pomocí (3.7 V) do motorových gondol, přičemž je nutné zajistit realistické a plynule regulovatelné otáčky pomocí DC/DC měniče a PWM regulátoru, aby
    nedocházelo k příliš rychlému otáčení vrtulí.
  
  - Implementovat kompletní sadu navigačních, přistávacích a antikolizních světel (LED napájené pomocí 12 V).

  - Vytvořit systém napájení s využitím 3S LiPo baterie (11.1 V / 12.6 V), který zvládne napájet obě větve obvodu (První větev bude pro motory, a druhá pro osvětlení).
    
  - Posledním úkolem tohoto projektu je ukrýt všechnu elektroniku zahrnující PWM modulátor, DC/DC měnič, spínače a baterie. Zde přichází bod, ve kterém se musím rozhodnout, jak udělám regulaci otáček motoru. V        prvním případě se dá provést pomocí DC-DC Step-Down měniče v trupu modelu, přičemž bude zároveň potřeba použít co nejtenčí a nejlehčí vodiče, aby nedošlo k narušení měřítka a integrity modelu. Popřípadě je
    druhá, praktičtější možnost ukrytí baterie, spínačů a PWM do případného diorama (miniatura scény, která vytváří iluzi skutečnosti pomocí plastických modelů). Avšak toto řešení vede k problému s tím, kudy
    povede kabeláž z modelu do dioramatu. Také je možnost tyto 2. možnosti zkombinovat, což je dále rozvedeno v Schématech zapojení větví.

Současná podoba projektu:

  - Aktuálně se můj projekt nachází ve fázi, když už mám vybranou většinu součástek, co pro svoje plánované modifikace potřebuji. Na druhou stranu mi ještě zbývá dodělat spousta věcí. Jednou z těchto věcí je
    dodělat samotná schémata zapojení, která už mám sice vymyšlená, ale zbývá mi jejich samotná vizualizace (nákres). Dále mi např. zbývá objednat všechny el. součástky, potřebuji dodělat modifikace samotného
    modelu pro akomodaci el. součástek a na závěr se ještě musím rozhodnout, jakým způsobem nakonec provedu limitaci otáček motorů (tato problematika je dále rozvedena ve schématech zapojení motorů). Nejvíce času
    trávím stavbou samotného modelu.

Součástky:
- Baterie:
     - LiPol Gens Ace Soaring G-Tech 3S 11.1V 1300mAh 30C (1ks)
     
- DC-DC Step-Down měnič:
     - LM2596 Modul (1ks)
     
- PWM regulátor: 
     - Regulátor otáček motoru 1.8-5V DC 2A 30W (1x)
     
- Motory:
     - 6x12 mm bezjádrový mikromotor 3.7 V (4ks)
     
- Osvětlení LED: 
     - Studená bílá LED světla 1 mm (6-8ks)
     - Zelená LED dioda – 1 mm (1ks)
     - Červená LED dioda – 1 mm (1ks)
     - Studená bílá LED dioda blikající - 2mm (1ks)
     - Červená LED dioda blikající - 2mm (1ks)
     
- Vodiče:
     - Hlavní přívod (od XT60 k DC/DC měniči a vypínačům)
       - 20 - 22 AWG
     - Od DC/DC měniče/PWM k motorům
       - 26 AWG
       
- Spínače:
     - Pro celkové napájení 
       - Kolébkový nebo posuvný spínač
    
     - Navigační, přistávací a antikolizní světla
       - Posuvný spínač

Schémata zapojení větví:

  I. Větev motorů:
   - Tato větev zajišťuje realistické otáčky pro čtyři motory, protože mají motory uvedené 21800 ot. /min. Z tohoto důvodu je potřeba do tohoto obvodu zakomponovat určitý způsob jejich limitace. Proto jsem zvolil
     DC/DC měnič LM2596: Připojen k napětí (12.6 V). Výstupní napětí je pevně nastaveno na 3.7V (jmenovité napětí motorů). Dále se v obvodu nachází miniaturní spínač (min. 2A), který zapíná napájení regulátoru.
     PWM regulátor, který nastavuje plynulé otáčky od nuly. Na vstupu je (3.7 V). Všechny čtyři motory jsou zapojeny paralelně k výstupu PWM regulátoru. Jako vodič použiji silikonové lanko 26 AWG (průřez 0.129
     mm²).

  II. Větev osvětlení:
   - Všechny 1mm LED napájené pomocí (12 V) s vestavěným rezistorem jsou zapojeny paralelně k (12.6 V) obvodu, každá skupina má svůj vlastní spínač.
     
  A. Trvalý svit (Navigační a Přistávací světla)
   - Veškeré osvětlení v tomto obvodu je zapojeno paralelně k (12.6 V) napájecí větvi a je rozděleno do dvou spínaných podskupin: Navigační a přistávací světla.

  B. Blikající svit (Antikolizní/Stroboskopická světla)
   - Obě blikající LED diody (Bílá a Červená) jsou zapojeny paralelně k napájecímu obvodu (12.6 V). Ke každé LED je v sérii připojen její vlastní omezovací rezistor 470 Ω.

Speciální poděkování:

  - V tomto odstavci mi dovolte  vyjádřit upřímné poděkování mým přátelům Hlibu Tryhubovi a Tomáši Dobešovi. Jejich pomoc a cenné rady byly klíčové nejen při výběru vhodných elektronických součástek pro motorové      a osvětlovací obvody, ale i při konzultacích ohledně správného schématu zapojení celého modelu. Jejich podpora významně přispěla k prozatimní úspěšné realizaci projektu.

Citace a odkazy:

Komponenty a inspirace
 - "5 kusů 6x12 mm bezjádrový mikromotor 3.7 V." Allegro.cz. Získáno 15. prosince 2025, z: https://allegro.cz/nabidka/5-kusu-6x12-mm-bezjadrovy-mikromotor-3-7-v-13926269146
 - "Studená bílá LED světla 1mm." Allegro.cz. Získáno 15. prosince 2025, z: https://allegro.cz/produkt/studena-bila-led-svetla-1mm-8247449e-5cd2-4b9d-a3f6-4dd796fc245d?offerId=17533497608
 - "Regulátor otáček motoru 1.8-5V DC 2A 30W." Allegro.cz. Získáno 15. prosince 2025, z: https://allegro.cz/nabidka/regulator-otacek-motoru-1-8-5v-dc-2a-30w-13487321048
 - "Akumulátor Gens Ace G-Tech Soaring 1300mAh 11.1V 30C 3S1P LiPo." Allegro.cz. Získáno 15. prosince 2025, z: https://allegro.cz/produkt/akumulator-gens-ace-g-tech-soaring-1300mah-11-1v-30c-3s1p-lipo-baterie-c167e944-1c47-4499-a924-c4064617a085?offerId=17791318479
 - "GSW Green LED Lights 1mm (10 ks)." Peckamodel.cz. Získáno 15. prosince 2025, z: https://www.peckamodel.cz/gsw8436554364121es-green-led-lights-1mm-10x
 - "GSW Red LED Lights 1mm (10 ks)." Peckamodel.cz. Získáno 15. prosince 2025, z: https://www.peckamodel.cz/gsw8436554363841es-red-led-lights-1mm-10x
 - "GSW Blinking LEDs Cool White 2mm (10 ks)." Peckamodel.cz. Získáno 15. prosince 2025, z: https://www.peckamodel.cz/gsw8435646510125es-blinking-leds-cool-white-2mm-10x
 - "GSW Blinking LEDs Red 2mm (10 ks)." Peckamodel.cz. Získáno 15. prosince 2025, z: https://www.youtube.com/watch?v=HO_0f8tcBuI&t=6s
 - "Step-Down nastavitelný měnič s LM2596 DC-DC." Dratek.cz. Získáno 15. prosince 2025, z: https://dratek.cz/arduino-platforma/1303-stepdown-nastavitelny-menic-s-lm2596-dc-dc.html
 - "Silikonový kabel 22 AWG (0,644mm) Red." Bighobby.cz. Získáno 15. prosince 2025, z: https://www.bighobby.cz/silikonovy-kabel-22-awg--0-644mm--red/?srsltid=AfmBOooiepvVAEAUK8DXntnDI0RidhvZAwn4YS9TvYzEyDEUSVAR-      YZi
 - "Silikonový kabel 26 AWG červený (1 metr)." Bighobby.cz. Získáno 15. prosince 2025, z: https://www.bighobby.cz/silikonovy-kabel-26-awg-cerveny--1-metr-/?srsltid=AfmBOoq5EMeBpE8AjzrSURZQ-24Xnpb_6xY6fCU-             mn5QcT0Bfz3N8IpH

Video, které bylo mojí ispirací.

 - Douglas DC-3 trumpeter 1/48 Alaska Airlines - Aircraft Model. (2018, 3. prosince). [Videozáznam]. YouTube. Získáno 15. prosince 2025, z: https://www.youtube.com/watch?v=HO_0f8tcBuI&t=6s

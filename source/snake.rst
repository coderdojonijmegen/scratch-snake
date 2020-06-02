Snake
=====

Inleiding
---------

In deze opdracht ga je het klassieke spelletje *Snake*, dus *Slang*,
programmeren. Je bestuurt in dit spelletje een slang en je doel is door zo veel
mogelijk te eten zo lang mogelijk te worden. Maar pas op, als je in je eigen
staart bijt dan ben je af!

Dit zijn de stappen die je gaat programmeren:

1. Maak de slang
2. Zorg dat de slang kan bewegen
3. Laat het eten van de slang verschijnen
4. Maak de slang langer door het eten
5. Laat het spel eindigen als de slang in de eigen staart bijt

Als je dan nog zin (en tijd) hebt dan zijn er nog allerlei uitbreidingen mogelijk.

Als startpunt voor de opdracht kun je `dit project
<https://scratch.mit.edu/projects/400374714>`_ gebruiken (je kunt dan stap 1
van de opdraht overslaan). Je kunt het project
zelf gaan bewerken door op de *Remix* knop boven in Scratch te klikken:

.. image:: imgs/remix.png

De opdracht is afgeleid van `deze instructies
<https://bournetocode.com/projects/7-CS-ScratchArcade/pages/2_Lesson.html>`_
(`Github bron <https://github.com/digixc/7-CS-ScratchArcade>`_).

Maak de slang
-------------

Als je gekozen hebt het project helemaal vanaf het begin te doen, ontwerp dan
je eigen slang of download deze plaatjes om de twee *uiterlijken* van de slang
mee te maken:

.. image:: imgs/slang_hoofd.png
.. image:: imgs/slang_lijf.png

Volg deze stappen om een sprite van de slang te maken:

1. Klik op het icoon voor een nieuwe sprite (rechtsonder, plaatje van de kat)
   en kies voor *Upload sprite*.
2. Upload het hoofd van de slang.
3. Ga naar het tabblad *Uiterlijken* (linksboven, rechts naast het *Code*
   tabblad).
4. Klik op het icoon voor een nieuw uiterlijk (linksonder, plaatje van de kat)
   en kies voor *Upload uiterlijk*.
5. Upload het lijf van de slang.
6. Klik nu op het hoofd van de slang.

Zorg dat de slang kan bewegen
-----------------------------

Het is de bedoeling om de slang met de pijltjestoetsen te laten bewegen. Er
zijn verschillende manieren om dit te doen, bijvoorbeeld zo:

.. raw:: html

  <div class = "scratch">
    wanneer [pijltje omhoog v] is ingedrukt
    richt naar (0) graden
    neem (5) stappen
  </div>

Met *richt naar 0 graden* draai je het hoofd van de slang naar boven, met *neem
5 stappen* beweegt de slang 5 stappen in die richting. Maar... als je de toets
loslaat, dan houdt de slang op met bewegen.

**Opdracht** Zorg dat de slang doorgaat met bewegen totdat je een andere kant
op gaat. *Tip 1*: hiervoor heb je het *herhaal* blok uit het menu *Besturen*
nodig. *Tip 2*: begin het programma met het *wanneer op de vlag wordt geklikt*
blok uit het menu *Gebeurtenissen*.

.. container:: toggle

  .. container:: header

    Klik om de voorbeeldcode te laten zien om de slang omhoog te laten bewegen

  .. raw:: html

    <div class = "scratch">
      wanneer groene vlag wordt aangeklikt
      herhaal
      als &lt;toets [pijltje omhoog v] ingedrukt?&gt; dan
      richt naar (0) graden
      end
      neem (10) stappen
      wacht (0.1) sec.
    </div>

In de voorbeeldcode wordt het blok *wacht 0.1 sec.* gebruikt. Dit is niet nodig
om de slang te laten bewegen, maar wordt verderop in het spel belangrijk. 
Door de wachttijd en/of het aantal stappen dat de slang zet te veranderen kun
je de snelheid van de slang bepalen.

Laat de appels verschijnen
--------------------------

Nu is het tijd om de slang eten te geven. Dit voorbeeld gaat uit van
appels, je kunt natuurlijk ook iets heel anders verzinnen. Om het lekker
onvoorspelbaar te maken waar de appel verschijnt is het blok *ga naar
willekeurige positie* uit het menu *Beweging* heel geschikt.

**Opdracht** Maak een nieuwe *sprite* voor de appel, en zorg dat er bij het begin
van het spel een appel verschijnt. *Tip*: zorg dat je de appel-sprite hebt
gekozen zodat de code die je maakt ook echt bepaalt wat de appel moet doen.

.. container:: toggle

  .. container:: header

    Klik om de voorbeeldcode te laten zien

  .. raw:: html

    <div class = "scratch">
      wanneer groene vlag wordt aangeklikt
      ga naar (willekeurige positie)
    </div>

De volgende stap is om een "nieuwe" appel op een andere plek te laten
verschijnen wanneer de slang er een heeft opgegeten. Hiervoor maak je niet echt
een *nieuwe* appel, maar je laat de appel-sprite gewoon op een andere plek
verschijnen.

**Opdracht** Laat de appel op een andere plek verschijnen als de slang er een
heeft opgegeten. *Tip*: hiervoor kun je het blok *raak ik ...* uit het menu
*Waarnemen* gebruiken.

.. container:: toggle

  .. container:: header

    Klik om de voorbeeldcode te laten zien

  .. raw:: html

    <div class = "scratch">
      wanneer groene vlag wordt aangeklikt
      ga naar (willekeurige positie)
      herhaal
      als &lt;raak ik (slang hoofd v)?&gt; dan
      ga naar (willekeurige positie)
      end
    </div>

Maak de slang langer
--------------------

Van al die appels groeit de slang natuurlijk wel! Het is nu tijd om de slang
langer te maken als je een appel eet. Hiervoor is het eerst nodig dat je
bijhoudt hoeveel appels de slang al heeft gegeten, dat kun je ook meteen als
je *score* in het spel gebruiken!

**Opdracht** Hou het aantal gegeten appels bij. *Tip 1*: hiervoor heb je een
*variabele* nodig, deze maak je in het menu *Variabelen*. *Tip 2*: zet aan het
begin van het spel de waarde van de variabele op 0.

.. container:: toggle

  .. container:: header

    Klik om de voorbeeldcode voor de slang te laten zien

  .. raw:: html

    <div class = "scratch">
      wanneer groene vlag wordt aangeklikt
      maak [score v] (0)
      enzovoort
    </div>

.. container:: toggle

  .. container:: header

    Klik om de voorbeeldcode voor de appel te laten zien

  .. raw:: html

    <div class = "scratch">
      wanneer groene vlag wordt aangeklikt
      ga naar (willekeurige positie)
      herhaal
      als &lt;raak ik (slang hoofd v)?&gt; dan
      ga naar (willekeurige positie)
      verander [score v] met (1)
      end
    </div>

Nu komt het moeilijkste stukje van het spel: het lijf van de slang! Hiervoor
ga je werken met *klonen* van de slang, deze functies vind je in het menu
*Besturen*. Dit werkt zo:

* het lijf van de slang maak je door op de plek van het hoofd een kloon te
  maken.
* het lijf van de slang is het tweede *uiterlijk* van de slang *sprite*, om
  de kop in een lijf te laten veranderen heb je het *verander uiterlijk naar*
  blok in het menu *Uiterlijken* nodig.
* als je nog geen of weinig appels hebt gegeten, dan wil je zo'n kloon meteen
  - of in ieder geval heel snel - weer *laten verdwijnen*.
* hoe meer appels je hebt gegeten dus hoe hoger je score, hoe langer je wilt
  wachten met het laten verdwijnen van de kloon.

**Opdracht** Kloon de kop van de slang (bij iedere stap), en laat de kloons
na een tijdje weer verdwijnen. *Tip*: je kunt uitrekenen hoe lang je moet
wachten door je score te vermenigvuldigen met hoe lang 1 stap van de slang
duurt.

.. container:: toggle

  .. container:: header

    Klik om de voorbeeldcode van de slang te laten zien

  .. raw:: html

    <div class = "scratch">
      wanneer groene vlag wordt aangeklikt
      herhaal
      als &lt;toets [pijltje omhoog v] ingedrukt?&gt; dan
      richt naar (0) graden
      end
      neem (10) stappen
      wacht (0.1) sec.
      maak een kloon van (mijzelf v)
    </div>

.. container:: toggle

  .. container:: header

    Klik om de voorbeeldcode van kloons van de slang te laten zien

  .. raw:: html

    <div class = "scratch">
      wanneer ik als kloon start
      verander uiterlijk naar (slang_lijf v)
      wacht ((score) * (0.1)) sec.
      verwijder deze kloon
    </div>

Verliezen als je in jezelf hapt
-------------------------------

Je hebt nu een slang die steeds langer wordt als ie meer appels eet. Wat nog
mist is dat het spel is afgelopen als je slang in zichzelf bijt. Dit gebeurt
wanneer een deel van het lijf een ander deel van het lijf raakt.

**Opdracht** Zorg ervoor dat het spel stopt als de slang in zichzelf bijt.
*Tip*: hiervoor kun je weer het *raak ik* blok gebruiken.

.. container:: toggle

  .. container:: header

    Klik om de voorbeeldcode te laten zien

  .. raw:: html

    <div class = "scratch">
      wanneer ik als kloon start
      als &lt;raak ik kleur [#9afeb6]?&gt; dan
      stop [alle v]
    </div>

Uitbreidingen
-------------
Je kunt het spel natuurlijk nog veel mooier, spannender en moeilijker maken.
Hier heb je alvast een lijstje met ideeën als je nog verder wil programmeren
aan *Snake*:

* laat de appels na een tijdje weer verdwijnen
* maak een start- of eindscherm voor het spel
* laat de slang sneller gaan als je meer appels hebt gegeten
* laat het spel ook afgelopen zijn als je de rand raakt
* kies een mooie achtergrond voor je spel
* laat ook voorwerpen verschijnen die je juist moet ontwijken
* programmeer het spel voor twee spelers

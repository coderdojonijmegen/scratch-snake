Snake
=====

In deze opdracht ga je het klassieke spelletje *Snake*, dus *Slang*,
programmeren. Je bestuurt in dit spelletje een slang en je doel is door zo veel
mogelijk te eten zo lang mogelijk te worden. Maar pas op, als je in je eigen
staart bijt dan ben je af!

Je gaat het spel zo bouwen:

1. Maak de slang
2. Zorg dat de slang kan bewegen
3. Maak eten voor de slang
4. Laat het eten op allerlei plekken verschijnen
5. Maak de slang langer door het eten
6. Laat het spel eindigen als de slang in de eigen staart bijt
7. Hou de score bij


Maak de slang
-------------

Als je gekozen hebt het project helemaal vanaf het begin te doen, download dan
deze plaatjes om de twee *uiterlijken* van de slang mee te maken:

.. image:: imgs/slang_hoofd.png
.. image:: imgs/slang_lijf.png

Volg deze stappen om een sprite van de slang te maken:

1. Klik op het icoon voor een nieuwe sprite (rechtsonder, plaatje van de kat)
   en kies voor *Upload sprite*.
2. Upload het hoofd van de slang.
3. Ga naar het tabblad *Uiterlijken* (linksboven, rechts naast het *Code* tabblad).
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
loslaat, dan houdt de slang op met bewegen. In dit geval moet de slang doorgaan
tot je een andere kant op gaat. *Tip*: hiervoor heb je het *herhaal* blok nodig.
Begin het programma met het *wanneer op de vlag wordt geklikt* blok.



.. raw:: html

  <div class = "scratch">
    wanneer groene vlag wordt aangeklikt
    herhaal
    als <key [pijltje omhoog v] ingedrukt?> then
    end


.. raw:: html

  <div class = "scratch">
    wanneer groene vlag wordt aangeklikt
    toets [pijltje omhoog v] ingedrukt?
    key [arrow down v] pressed?
    if <> then
    if <key [arrow down v] pressed?> then
    end
    <span>if <key [pijltje omhoog v] pressed?> then</span>
    end
  </div>


.. container:: toggle

   .. container:: header

      klik om voorbeeld te laten zien

   .. raw:: html

    <div class = "scratch">
        wanneer op vlag geklikt
        richt naar (0) graden
        neem (5) stappen
    </div>



Je kunt in de instructies gebruik maken van Scratch blokken. Gebruik daarvoor de volgende code:

.. code::

   .. raw:: html

      <div class = "scratch">
          when flag clicked
          clear
      </div>

En dat resulteert dan in:

.. raw:: html

   <div class = "scratch">
       when flag clicked
       clear
   </div>

mit AWTRIXER kannst du 8x8 Icons (statisch oder animiert) und 32x8 Animationen erstellen.
AWTRIXER basiert auf [Piskel](https://www.piskelapp.com/) und arbeitet direkt mit dem AWTRIX Backend zusammen.
AWTRIXER behinhaltet massig funktionen die fast schon an Photoshop erinnern.

!> Piskel und damit auch AWTRIXER sind nicht für mobile Geräte optimiert!

  <div align=center>
  <img width="1000" src="..\assets\creator.gif"/>
  </div>

  - Auf der linken Seite findest du alle Werkzeuge die du zum zeichnen benötigst. Fahre mit der Maus über die einzelnen Symbole um mehr informationen zu erhalten.
  - Bei der Farbauswahl ist zu beachten, das transparente Farben nicht im fertig gespeicherten Icon übernommen werden.
  - Eine Animation erstellst du, in dem du mehrere Frames hinzufügst. Du kannst diese neu erstellen oder ein vorhandenen Frame duplizieren.
  - Auf der Rechten Seite findest du die Icon Vorschau sowie den Slider um die Geschwindikeit der Animation zu ändern.
  - Die Sektion **Live View** ermöglicht es dir, deine Arbeit Live auf deiner AWTRIX zu sehen. Nutze dies bevor du ein Icon hochlädst, denn auf der Matrix sieht es meist etwas anders aus, als auf deinem Montior.
  - über die Menüpunkte ganz rechts gelangst du zu den allgemeinen Eigenschaften von AWTRIXER
    - Resize lässt dich deine Leinwand von 8x8 auf 32x8 ändern. Andere Größen sind hier nicht möglich.
    - Mit Save kannst du dein Werk umbennenen, für spätere sessions abseichern oder in die Cloud hochladen.
    - Export, exportiert dein Icon als Bilddatei auf den PC. Diese können von AWTRIX aber nicht verwendet werden.
    - Mit Import kannst du vorhandene Grafiken oder Animationen importieren. Bitte beachte auch hier das AWTRIX nur 8x8 oder 32x8 arbeiten kann. Nutze ggf. die Resize Funktion während des importiertvorgangs.


**Du hast auch die Möglichkeit, um Icons für den privaten Gebrauch lokal zu speichern**  
Um sie zu verwenden, schreibst du einfach den Icon-Namen als ID (String statt Integer) in deine API-Anforderung
Alle Icons werden in einer lesbaren Textdatei gespeichert (config->privatIcons), so dass du Icons manuell bearbeiten/ hinzufügen/entfernen kannst.
AWTRIX erkennt keine Änderungen an dieser Datei. Um deine privaten Icons neu zu laden, führe einfach Reload-Icons vom Terminal auf der Hauptseite aus. Wenn du deine Icons über AWTRIXER speicherst, werden sie automatisch neu geladen.
Wie die Community Icons können auch deine privaten Icons nicht zur Bearbeitung in AWTRIXER geladen werden. Benutze  "Speichern als .awtrixer-Datei", um dein Icon zu sichern.
Deine privaten Icons werden nicht in der Icondatabase angezeigt.
Trotz dieser Funktion ist es natürlich immer noch schön, Icons mit der Gemeinschaft zu teilen.

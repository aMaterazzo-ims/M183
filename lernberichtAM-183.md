# Lern-Bericht
✍️ By Andrea Materazzo

## Einleitung

✍️ In diesem Modul ging es um Applikationssicherheit. Ich habe mich für ein Projekt mit XSS (Cross-Site-Scripting) entschieden. Um die Gefahr zu erläutern die
XSS mit sich birgt.

## Was habe ich gelernt?

✍️ Ich habe gelernt das XSS eine ernstnzunehmende Sicherheitslücke ist, und immer behoben werden muss. Zusätzlich weiss ich jetzt wie man diese Sicherheitslücke behebt.

## Beschreibung

✍️ Um XSS weiter zu erläutern, habe ich hier eine Beschreibung geschrieben.

Wenn der Angreifer in einem Textfeld Code eingibt und so eine JavaScript-Datei ladet, kann er eine Menge schaden anrichten. Deshalb müssen wir sorgen das
Sonderzeichen umgewandelt werden, sodass der Browser diese Eingabe nicht mehr als auszuführenden JavaScript-Datei interpretiert.

Es gibt ein bekanntes Beispiel von XSS, undzwar der "Self-retweeting Tweet".
Ein User auf Twitter hat im Jahre 2014 auf Twitter einen Kommentar gepostet, welcher eine JavaScript-Datei ladete, welche den Tweet automatisch wieder retweetete.
Der Tweet wurde 81'500 mal retweetet.

So sah der Tweet aus.

![image](https://user-images.githubusercontent.com/111268969/207706914-63163d60-305c-427c-8284-9cc47e9c63c5.png)

Um dies zuvermeiden müssen wir die Sonderzeichen umwandeln, und dies wird wie folgt gemacht.

```Java
//Methode um die Sonderzeichnen umzuwandeln
public String convertUserInput(String userInput) {

//Sonderzeichen werden unschädlich gemacht indem Sie nicht wie Code aussehen.
  String converteddInput = userInput.replaceAll("<script>", "")
                                   .replaceAll("</script>", "")
                                   .replaceAll("<style>", "")
                                   .replaceAll("</style>", "")
                                   .replaceAll("<", "&lt;")
                                   .replaceAll(">", "&gt;");
  
  //Encoder Methode wird aufgerufen, um sicherzustellen, dass alle Sonderzeichen, die für URL's verwendet werden, richtig codiert werden.
  convertedInput = URLEncoder.encode(convertedInput, "UTF-8");
  //Gibt den Umgewandelten Input heraus.
  return convertedInput;
}
```

## Verifikation

✍️ Die von mir benutzten Medien, zeigen die Gefahr von XSS und wie die Lösung, um Missbrrauch zu verhindern, umgesetzt wird.

# Reflektion zum Arbeitsprozess

👍 Als wir den Input zu XSS erhalten haben, dachte ich mir das es sehr schwierig werden würde diese Sicherheitslücke zu schliessen, jedoch braucht man dafür nur 
wenig und einfachen Code. Obwohl wir die meiste Zeit von Zuhause aus gearbeitet haben, konnte ich trotzdem sehr Prdouktiv arbeiten und meine Ziele erreichen.

👎 Dadurch das wir von Zuhause gearbeitet haben, habe ich mehr gezögert fragen zustellen, da dies nicht wie in der Schule ist wo man den Lehrer kurz zu sich ruft
oder an den Tisch des Lehrers geht, sondern man muss den Lehrer anschreiben und dan mit ihm einen Call machen und den Bildschirm teilen etc. Dadurch das ich aber
nicht nachgefragt habe, konnte ich meine selbständigkeit erhöhen und lernen besser selber klar zukommen. Wie es im Berufsleben der Fall sein wird.

✍️ **VBV**:  Ich habe Zuhause zwar Produktiv gearbeitet, jedoch Pausen gemacht die länger gingen als vorgegeben. Deshalb möchte ich für das nächste Modul probieren
die Pausenzeiten einzuhalten damit ich noch mehr erreichen kann.

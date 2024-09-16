# Haspel-SSD
Mockup für eine Webapp zur Absprache zwischen Lehrern und Sanitätern am BK Haspel

# Anforderungen
Nutzer sollen sich mit vorgeneriertem User anmelden. <br>
Es sollen Meldungen von Lehrern erstellt werden. <br>
Meldungen sollen als Push Notification bei Sanitätern erscheinen. <br>
Sanitäter sollen sich zum Dienst melden können. <br>
Sanitäter sollen sich einer Meldung zuordenen können ("Wir sind unterwegs"). <br>
Lehrer sollen Meldungen bearbeiten und abschließen können. <br>
Es sollen keine personenbezogenen Daten gespeichert/angezeigt werden. <br>
Gegen doppeltes Versenden und Unfug absichern. <br>
Es soll eine Admin-Page zum Verwalten von Accounts geben. <br>

# Elemente / Pages

### Login
Username eingeben <br>
Passwort eingeben <br>

### Dashboard (Übersicht aller Anfragen + Teams)
Liste aller Meldungen (rot = aktiv, grün = unterwegs, grau = inaktiv)
<table style="width:100%">
  <tr>
    <th>Zeit</th>
    <th>Standort</th>
    <th>Beschreibung</th>
    <th>Name Ersteller</th>
    <th>Benötigte Teams</th>
    <th>Funktionsbuttons</th>
  </tr>
</table>
Funktionsbuttons Lehrer: "Wir sind unterwegs" <br>
Funktionsbutton Lehrer: "Meldung bearbeiten", "Meldung abschließen" <br>

Lehrer Button -> Meldung erstellen
Standort (Dropdown)	Raumnummer (Dropdown)	Teams benötigt (Dropdown)	Beschreibung

### Push Notification an Sanitäter
Benachrichtigung "Sanitäter benötigt"
-Standort anzeigen


# Beschreibung

Im Login können sich Lehrer und Sanitäter mit einem vom Admin generierten Account anmelden. Nach erfolgreicher Anmeldung wird man auf das Dashboard weitergeleitet.

Das Dashboard sieht ja nach Account-Typ unterschiedlich aus, es beinhaltet eine Liste der aktuellen Meldungen. Eine Meldung beinhaltet folgendes:
-Zeit der Erstellung
-Standort
-Beschreibung
-Name des Erstellers
-Anzahl benötigter Teams
-Button: "Wir sind unterwegs" (SANITÄTER)
-Button: "Meldung bearbeiten" (LEHRER)
-Button: "Meldung abschließen" (LEHRER)

Eine erstellte Meldung wird vorerst als rot angezeigt.

Wenn Sanitäter den Button "Wir sind unterwegs" klicken, ändert sich der Status der Meldung auf grün.

Wenn Lehrer auf den Button "Meldung bearbeiten" klicken, können sie die Daten der Meldung abändern, diese werden in der Liste aktualisiert.

Wenn Lehrer auf den Button "Meldung abschließen" klicken, wird die Meldung ausgegraut.

Wenn Lehrer auf den Button "Meldung erstellen" klicken, öffnet sich eine Eingabemaske, in der die Meldung erstellt werden kann, folgende Dinge werden eingegeben:
-Standort (Dropdown)
-Raumnummer (Dropdown)
-Beschreibung (Textbox)
-Anzahl benötigter Teams (Dropdown)

Beim Erstellen einer neuen Meldung wird automatisch eine Push-Notification mit dem Standort an alle verfügbaren Sanitäter gesendet.

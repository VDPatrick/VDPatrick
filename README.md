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
Button Lehrer: "Meldung erstellen" <br>
Zeitpunkt der letzten Aktualisierung wird unter der Liste angezeigt <br><br>
Liste aller Meldungen (rot = aktiv, gelb = keine Beschreibung, grün = unterwegs, grau = inaktiv)
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
Funktionsbutton Sanitäter: "Wir sind unterwegs" <br>
Funktionsbutton Lehrer: "Meldung bearbeiten", "Meldung abschließen" <br>

### Meldung erstellen
<table style="width:100%">
  <tr>
    <th>Standort (Dropdown)</th>
    <th>Raumnummer (Dropdown)</th>
    <th>Teams benötigt (Dropdown)</th>
    <th>Alle Sanitäter rufen (Button)</th>
  </tr>
</table>

### User Control Pop-Up
Kleines Fenster oben rechts, öffnet sich durch Klicken <br>
Kleines "Profilbild" anzeigen <br>
Nutzernamen anzeigen <br>
Logout Button <br>
Slider Sanitäter: Status steuern (aktiv / inaktiv) <br>

### Push Notification an Sanitäter
Benachrichtigung "Sanitäter benötigt" <br>
-Standort anzeigen <br>

### Admin Dashboard
Liste aller Nutzer (Name + Rolle + Status) <br>
Neue Nutzer anlegen <br>
Nutzer verwalten (Änderungen von Name + Rolle) <br>
Passwort von Nutzer zurücksetzen <br>
Historie aller Meldungen + Statusänderungen <br>
Exportieren der Historie als PDF <br>

# Beschreibung

Im Login können sich Lehrer und Sanitäter mit einem vom Admin generierten Account anmelden. Nach erfolgreicher Anmeldung wird man auf das Dashboard weitergeleitet.
<br>
Das Dashboard sieht ja nach Account-Typ unterschiedlich aus. Es beinhaltet eine Liste der aktuellen Meldungen, den Zeitpunkt der letzten Aktualisierung, ein User Control Pop-Up und für Lehrer einen Button zum Erstellen neuer Meldungen. <br>
<br>
Eine Meldung in der Liste beinhaltet folgendes: <br>
-Zeit der Erstellung <br>
-Standort <br>
-Beschreibung <br>
-Name des Erstellers <br>
-Anzahl benötigter Teams <br>
-Button: "Wir sind unterwegs" (SANITÄTER) <br>
-Button: "Meldung bearbeiten" (LEHRER) <br>
-Button: "Meldung abschließen" (LEHRER) <br>
<br>
Eine erstellte Meldung wird vorerst als rot angezeigt. <br>
Wenn Sanitäter den Button "Wir sind unterwegs" klicken, ändert sich der Status der Meldung auf grün. <br>
Wenn Lehrer auf den Button "Meldung bearbeiten" klicken, können sie die Daten der Meldung abändern, diese werden in der Liste aktualisiert. <br>
Wenn Lehrer auf den Button "Meldung abschließen" klicken, wird die Meldung ausgegraut. <br>
<br>
Wenn Lehrer auf den Button "Meldung erstellen" klicken, öffnet sich eine Eingabemaske, in der die Meldung erstellt werden kann, folgende Dinge werden eingegeben:<br>
-Standort (Dropdown)<br>
-Raumnummer (Dropdown)<br>
-Anzahl benötigter Teams (Dropdown) <br>
<br>
Nach dem Erstellen wird die (unfertige) Meldung zwar schon abgeschickt aber auch farblich vorgehoben, bis der Lehrer eine Beschreibung eingegeben hat. <br>
<br>
Beim Erstellen einer neuen Meldung wird automatisch eine Push-Notification mit dem Standort an alle verfügbaren Sanitäter gesendet. <br>
<br>
Für Admins gibt es ein extra Dashboard zum Verwalten und Erstellen von User-Accounts. <br>

# Klassendiagramm

![Klassendiagramm](images/Webapp-Klassendiagramm.jpg)
---
title: "S4R: Chrome, Safari, Firefox - Aber bitte mit ...!"
date: 2024-10-26T18:00:00+02:00
description: Gastbeitrag zur IT-Sicherheits Serie Security 4 Runaways von Tim Kern
hero: images/hero.svg
menu:
  sidebar:
    name: S4R - Browser
    parent: itsecde
    identifier: 0001_2024-10-26-browser
    weight: 1
tags: ["Basics", "Security", "Browser"]
categories: ["IT-Sicherheit"]
---

Hinweis: Es wurde keine KI zur Erstellung oder Recherche dieses Beitrags verwendet. Das Training einer KI mit diesem Beitrag ist nicht gestattet.

# Sicherheitsbasics für den (PC) Browser

In der modernen Welt reicht es leider oft nicht mehr aus, nur noch einen Browser herunterzuladen, als "Standardbrowser" zu setzen und los zu surfen.

Was zusätzlich noch notwendig ist, möchte ich in diesem Beitrag kurz beleuchten. Sicherheit und relative Anonymität muss nicht kompliziert sein.

Dieser Beitrag gehört zu einer Beitragsreihe namens "Security for Runaways" von Tim Kern. Veröffentlicht wurde der Beitrag ursprünglich in meinem Blog, auf steffen-barnau.systems.

## 1 - Die Browserauswahl

Für Einige Nutzer der entsprechenden Windows 10+ Versionen, ergibt sich bereits beim ersten Systemstart die Frage, welcher Browser als "Standard" installiert werden soll. Früher wurde oft der Umstand belächelt, dass Microsoft jedem Nutzer den Internet Explorer "Aufzwang". Dieser sei dann der beste Browser, um andere Browser herunterzuladen.

Der Klassiker war bis zu Zeiten von Windows XP defintiv Firefox. Das kennt sicherlich jeder.

Im Jahre 2008 kam Google Chrome dazu. Der Browser zeichnete sich damals durch einige Features aus, die ihn schneller und stabiler als die Alternativen machten, und so grub er nach und nach Marktanteile von Firefox ab.

Neben Chrome und Firefox, gibt es heutzutage noch folgende Optionen:

* Apple Safari
* Microsoft Edge (basierend auf Chrome bzw. Chromium)
* Brave (basierend auf Chrome bzw. Chromium)
* Opera GX (basierend auf Chrome bzw. Chromium)
* Einige neuere Browser, wie zum Beispiel Arc

Besonders letztere könnten durch kluge Integration von KI in Zukunft interessant sein, wir konzentrieren uns hier aber auf die großen:

* Edge
* Chrome
* Firefox
* Safari

Da ich keinen Mac besitze und daher keine Erfahrung mit Safari habe, muss ich diesen leider außen vor lassen.

Für die allermeisten User ergibt sich also die Wahl zwischen Edge (dem vorinstallierten Browser auf Windows), Chrome und Firefox.

Glücklicherweise bieten alle 3 Browser aktuell ein Erweiterungs-System, was uns im Folgenden entgegenkommen wird.

Um den Post möglichst einfach und kurz zu halten, werde ich pauschal eine Auswahl für einen Browser treffen. Zum aktuellen Zeitpunkt ist dies aus Gründen der Privatsphäre und einiger nützlicher Features der Chromium-basierte Browser **Brave**.

Der Browser kann auf Windows, Linux und MacOS (sowie Smartphones) installiert werden und ist auf der Herstellerseite https://brave.com verfügbar.

### 1.1 - Wieso Brave?
Brave bietet bereits ohne zusätzliche Addons enorm starken Schutz gegen schädliche Scripts, Werbung und Tracking. Da Google in der Upstream-Version von Chrome AdBlocker stark beschnitten hat (Manifest V3), scheidet Chrome selbst praktisch aus. Brave hat wiederum versprochen, weiterhin die AdBlocker Funktion zu pflegen ([s. Blogpost](https://brave.com/blog/brave-shields-manifest-v3/)).

## 2 - Grundkonfiguration
Out of the Box ist Brave prinzipiell schon sehr gut vorkonfiguriert. Der Browser finanziert sich durch Werbung, bzw. "Brave Rewards" - Das ist ein Cryptowährungs-Token, das durch das Zulassen von nicht-intrusiver Werbung verdient werden kann. Außerdem gibt es Werbeanzeigen im Browser.

Ob dieses Finanzierungsmodell bestand haben kann, wird sich zeigen. Persönlich finde ich jedoch Werbung für Crypto-Börsen ablehnenswert, daher habe ich einige der "Features" abgeschaltet. Jede(r) muss für sich selbst entscheiden, ob für die Unterstützung des Projektes die Werbeeinblendungen gerechtfertigt sind.

### 2.1 - Werbefunktionen in Brave deaktivieren
Auf der "neuer Tab" Seite wird in der Regel Vollbildwerbung angezeigt. Diese kann durch das Deaktivieren der Karten, sowie der Werbehintergründe umgangen werden. Die Konfiguration kann unten rechts auf der Seite "Anpassen" aufgerufen werden. Auf der Seite "Hintergrundbilder" können Sponsor-Bilder deaktiviert werden.

Zudem können Karten im zugehörigen Menüpunkt deaktiviert werden.

In den Browsereinstellungen können weitere Features deaktiviert werden. Hierzu via "Burgermenü" (Die 3 Streifen neben der Adressleiste), via "Einstellungen" folgende Anpassungen vorgenommen werden:

* Erscheinungsbild: Buttons und Suchvorschläge aktivieren/deaktivieren
* Shields/Schilde: Hier sind die interessanten zusätzlichen Features gelistet für Sicherheit und Privatsphäre
* Privatsphäre und Sicherheit: Die Standardeinstellungen sind ausreichend. Relevant ist hier noch "Sicheres DNS", dazu später mehr
* Web3: Hier alles deaktivieren (auf "Erweiterungen" (ohne Fallback) stellen)
* Leo: Da integrierte LLM/KI Modell. Ich deaktiviere hier alles
* Erweiterungen: Sicherstellen, dass "Wedevine" aktiviert ist, damit Streaming in hoher Qualität (bsp. Netflix) möglich ist

### 2.2 - Zusätzliche Addons
Über den Schutz von Brave hinaus, bleibt eigentlich nur die Installation des Addons [uBlock Origin](https://github.com/gorhill/uBlock/).

{{< alert type="warning" >}}
Für weitere Addons gilt es stets zu beachten, welche Rechte diese Anfragen und wer diese Bereitstellt. Ein Addon kann den kompletten Schutz von Brave und uBlock aushebeln!
{{< /alert >}}

## 3 - Weitere Aspekte
### 3.1 - VPN/Proxy
Viele VPN Anbieter werben damit, die Sicherheit beim Surfen durch Anonymisierung zu erhöhen. Beachtet werden sollte dabei, einen vertrauenswürdigen VPN Anbieter zu nutzen, denn durch die Nutzung eines solchen, wird sämtlicher Datenverkehr durch ein anderes Netzwerk geleitet und kann prinzipiell dort inspiziert werden. Die (zusätzlich) verschlüsselte VPN Verbindung endet beim VPN Anbieter selbst.

Trotzdem kann es durchaus wertvoll sein, einen VPN und/oder Proxyserver zu verwenden. Wenn viele Menschen durch einen Endpunkt (in diesem Falle der VPN Anbieter) auf eine Website zugreifen, so ist die Verbindung deutlich schwieriger auf einen einzelnen zurückzuführen.

### 3.2 - Secure DNS/DOH/DOT
Das Thema ist sehr technisch, und daher halte ich mich hier kurz. Normalerweise ist DNS Verkehr unverschlüsselt, und kann daher mitgelesen werden. DOH löst mehrere Probleme, die DNS hat und stellt meines Erachtens nach einen Netto gewinn dar.

Daher sollte im Browser die Secure DNS Option mit dem DNS Anbieter des Vertrauens verwendet werden. Ähnlich wie bei VPN sollte beachtet werden, dass der Anbieter selbst weiterhin alle Anfragen sehen und auswerten kann.

### 3.3 - Firewall und Adblocking DNS
Zusätzliche Sicherheit können private Firewalls (angeboten durch manche Router Hersteller), und private DNS Server wie PiHole oder AdGuard bieten. Auch diese sind für diesen Blog jedoch zu technisch.

## 4 - Setup testen
Die EFF bietet ein Tool zur Prüfung der Browser-Anonymisierung an. Dieses findet sich unter https://coveryourtracks.eff.org/

Die allgemeinen Sicherheitseinstellungen eines Browsers können auf https://browseraudit.com/ geprüft werden.

{{< alert type="warning" >}}
Grundsätzlich gilt: Der Browser ist ein mächtiges Tool mit potenziell sehr weitreichenden Systemrechten. Daher **muss** dieser stets aktuell gehalten werden.
{{< /alert >}}

## 5 - Wieso das Ganze?
Man kann sich sicherlich Fragen, wozu der Ganze aufwand betrieben werden muss. Wer allerdings ohne AdBlocker im Internet unterwegs war, weiß sehr genau, wo die Probleme liegen.
Im Prinzip sind viele (werbefinanzierte) Websites ohne AdBlocker nicht mehr nutzbar. Da sie sich aber durch Werbung finanzieren, muss für diejenigen, die keine AdBlocker verwenden noch mehr Werbung geschaltet werden.

Leider prüft nicht jedes Werbenetzwerk die Sicherheit der eingeblendeten Banner und nachgeladenen Scripte. Das kann dafür sorgen, dass man sich wenige Minuten später am Telefon mit einem angeblichen Support-Mitarbeiter von Microsoft wieder findet, oder in ein "Crypto Token der Zukunft" investiert.

Das sind jedoch noch die vergleichsweise harmlosen Fälle. Sollte der Browser oder das Betriebssystem (oder sogar der Heimrouter) Sicherheitslücken haben, die noch nicht gepatcht wurden, kann entsprechende Werbung gar ein Einfallstor für Angreifer sein.

Es gilt sowohl für IT-Abteilungen, als auch für Nutzer: Kein Internet ohne AdBlocker. Soll eine Website unterstützt werden, und es ist sichergestellt, dass sämtliche Werbung vertrauenswürdig ist, so bietet sich immer die Möglichkeit, diese Website zu "Whitelisten", also entsprechende Addons für die Website zu deaktivieren, damit Werbung gesehen werden kann.

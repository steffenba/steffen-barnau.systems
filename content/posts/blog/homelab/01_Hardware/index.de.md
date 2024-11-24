---
title: "01 - Die Hardware"
date: 2024-11-24T00:00:00+02:00
description: Übersicht zur eingesetzten Hardware
hero: images/lenovo-thinkCentre-M910-M710-tiny-hero.png
menu:
  sidebar:
    name: 01 - Hardware
    parent: homelabde
    identifier: 01_hardware_de
    weight: 1
tags: ["Basics", "Hardware", "Homelab"]
categories: ["Homelab"]
---

# Die Hardware

Je nach Anwendungsfall, kann und muss die jeweilige Hardware im Homelab angepasst werden.
Das wird vermutlich auch hier der Fall sein, dieser Artikel beschreibt stets den aktuellen Zustand meiner eingesetzten Hardware.

Ziel ist es, angesichts der Energiekosten und Umweltbedenken, möglichst sparsame Hardware für den Anwendungsfall einzusetzen, während Aspekte wie Datensicherheit und Performance weiterhin im Fokus stehen.

## USV

Fangen wir beim Grundsätzlichen an: Die Stromversorgung.

Während in Deutschland eigentlich selten Probleme bei der Energieversorgung, geschweigedenn Stromausfälle zu befürchten sind, können kleine Unfälle im Haushalt durchaus dafür sorgen, dass eine Sicherung fliegt.
Daher habe ich es für sinnvoll gehalten, eine USV zu besorgen. 

Da der Gesamtverbrauch meines Homelabs eher überschaubau sein sollte, habe ich mich für eine 850VA USV von Eaton entschieden, welche reguläre SchuKo-Kontakte verwendet.
Dabei handelt es sich um die **Eaton 3S 850VA**. Das Gerät kann nur über USB an einen Host angeschlossen werden, um bspw. via `nuts` einen automatischen Shutdown angeschlossener Hardware zu ermöglichen.

Das reicht für meine Zwecke jedoch aus. Die Anbindung via NUTS wird in einem späteren Artikel ausführlich behandelt.

## Netzwerk

Für ein Homelab sicherlich *etwas* overkill, habe ich mich dazu entschieden, als zentralen Switch einen SFP+-Only, Managed 10 Gigabit Switch zu verwenden.
Meine Wahl ist auf den **Sodola 8-Port 10G SFP+ Managed Switch** gefallen. Dieser wird mittels Glasfaser direkt mit Mokerlink Switches an den Arbeitsplätzen verbunden. Diese haben 4 2,5GbE-RJ45 Ports und 2 SFP+ 10G Ports.

So habe ich grundsätzlich die Möglichkeit, sofern ich die Hardware entsprechend anpasse, sowohl auf mein NAS, als auch auf meinen Server via 10G-Anbindung zuzugreifen.

Als Router-Kombigerät kommt ein **ASUS GT-BE98** zum Einsatz, dieser besitzt auch 2 10GbE Ports, also selbst ins WLAN (der Router unterstützt zudem WiFi-7 MLO) habe ich weit jenseits von 1 Gigabit Bandbreite (je nach Distanz, versteht sich).

Mein NAS hat eine 10G-PCIe Karte von **10GTek mit Intel x520-DA1** Chipsatz. Hierzu gibt es einiges zu beachten, dazu mehr im entsprechenden Artikel zu meinem NAS.

Der Server selbst ist aktuell mit einem USB3.0 2,5GbE Adapter von ASUS angebunden. So auch die PCs.

Das Netzwerksetup ist vor allem auf Zukunftssicherheit ausgelegt, 10G ist mittlerweile erstaunlich bezahlbar, daher nutze ich dieses bereits als Backbone, obwohl weder meine Client-PCs, noch der Server diese Bandbreite aktuell nutzen können.

## Speicher

Da der Heimserver an sich in Zukunft als Cluster betrieben können werden soll und ich den Speicher grundsätzlich von dessen Hardware trennen können möchte, habe ich mich für ein **QNAP TS-464** entschieden.

Dieses exportiert problemlos SMB-Shares und iSCSI-Volumes für die Nutzung unter Proxmox, respektive VMs und LXC Containern.

In dem NAS befinden sich zwei **Seagate Ironwolf 16TB (refurbished)** Festplatten im RAID-1, sowie 2 **Samsung 990 PRO 1TB** NVMe SSDs im RAID-1.

2 Slots sind noch frei, diese werde ich ggf. in Zukunft mit 2 weiteren Ironwolf Platten ausstatten und den RAID-1 auf RAID-10 migrieren.

## Der Server

Als Server-Host wird aktuell ein **Lenovo M910q** verwendet. Die Maschine ist sehr günstig gebraucht zu haben, und hat genügend Rechenkapazität, um einen kleinen Homeserver zu betreiben. Primär ist der limitierende Faktor für mich der Arbeitsspeicher, da dieser maximal 32GB umfassen kann.



So viel zur Hardware, die aktuell im Einsatz ist. Im nächsten Artikel werde ich das Proxmox, QNAP und USV (NUTS) Setup beleuchten, welches die Basis für den unterbrechungsfreien Betrieb darstellt.

Vielen Dank für's Lesen!
# Nexus Edge (Light Version) v6.1

**Ein Cyberpunk-styled OSINT Datenerfassungs-Tool für mobile Browser.**

Entwickelt für den schnellen Feldeinsatz ("Edge"), um Verbindungen und Entitäten zu erfassen und später in Neo4j zu analysieren. Dies ist die "Light Version", die komplett client-seitig im Browser läuft und Daten persistent speichert.

![Version](https://img.shields.io/badge/version-6.1-neon.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![Author](https://img.shields.io/badge/author-m0h1nd4-blue.svg)

## 🎯 Über das Projekt

**Nexus Edge** wurde entwickelt, um OSINT-Daten (Open Source Intelligence) direkt während der Recherche – auch vom Handy aus – strukturiert zu erfassen. Das Tool verzichtet auf komplexe Backend-Infrastruktur und nutzt moderne Browser-Technologien zur Datenspeicherung und zum Teilen von Ergebnissen.

Das Zielformat ist optimiert für den Import in Graph-Datenbanken wie **Neo4j**.

## ✨ Features

*   **📱 Mobile-First Design:** Optimierte Touch-Oberfläche mit nativem Sharing-Support.
*   **💾 Persistenz (Local Storage):** Deine Daten werden automatisch im Browser gespeichert. Auch nach einem Refresh oder Neustart des Browsers bleibt die Datenbank erhalten.
*   **🛡️ Daten-Integrität:** 
    *   **Duplikat-Warnung:** Verhindert das versehentliche doppelte Anlegen identischer Einträge.
    *   **Dedupe-Tool:** Eingebaute Funktion zum nachträglichen Bereinigen der Datenbank von Duplikaten.
*   **🎨 Cyberpunk UI:** Dunkles Theme mit Neon-Akzenten (V6 Design) für diskretes Arbeiten.
*   **🕸️ Graph-Ready Data:** Erfassung von Knoten (Nodes) und Kanten (Relationships).
*   **🔄 Advanced CSV Management:**
    *   **Import/Export:** Volle Unterstützung für CSV-Datensätze.
    *   **Sync & Merge:** Intelligente Logik beim Export – wähle zwischen Überschreiben, Synchronisieren (Zusammenführen von Import und aktuellen Daten) oder Umbenennen.
    *   **Custom Filename:** Der Standard-Dateiname für Exporte ist in den Einstellungen konfigurierbar.
*   **📤 Native Sharing:** Nutze die Share-Funktion deines Handys, um CSV-Daten direkt per Signal, WhatsApp, E-Mail oder Cloud zu senden (erfordert HTTPS).

## 🚀 Nutzung

### Installation
Es ist keine Installation notwendig! Das Tool besteht aus einer einzigen HTML-Datei.

1. Lade die Datei `nexus-edge.html` auf dein Endgerät (Laptop oder Smartphone).
2. Öffne die Datei in einem modernen Browser (Chrome, Firefox, Safari).

### Workflow
1. **INPUT:** Gib Daten in die Maske ein. Die Liste der Relationen wurde für professionelle OSINT-Analysen erweitert (z.B. `DIRECTOR_OF`, `SUBSIDIARY_OF`, `ALIAS_OF`).
2. **SAVE:** Klicke auf `>> SAVE TO MEMORY <<`. Das Tool warnt dich, falls der Eintrag schon existiert.
3. **DATABASE:** Überprüfe deine Einträge.
    *   Bearbeite oder lösche einzelne Zeilen.
    *   Nutze `[ DUPLIKATE ENTFERNEN ]` am Ende der Seite, um deine Liste sauber zu halten.
4. **EXPORT:** 
    *   Nutze `[ SAVE CSV ]` für den klassischen Download.
    *   Nutze `[ SHARE CSV ]` auf dem Handy für den schnellen Versand.
    *   Konfiguriere im EXPORT-Tab deinen bevorzugten Dateinamen.

## 🛠️ Technologien
*   HTML5 / CSS3 (Responsive Flexbox/Grid)
*   Vanilla JavaScript (Keine Frameworks, läuft offline)
*   Web Storage API & Web Share API

## 📄 Lizenz
Dieses Projekt ist unter der **MIT Lizenz** veröffentlicht.

---
*Created by m0h1nd4*

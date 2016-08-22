# icinga-sync
icinga-sync lädt eine nodes.json von einem Webserver und baut aus den darin enthaltenen Informationen eine Icinga1 Konfiguration für alle in der json-Daten gelisteten Knoten.
Außerdem legt es für jede E-Mailadresse, die im Kontaktfeld hinterlegt ist, einen Kontakt an. Jeder Knoten wird einer Kontaktgruppe entsprechend seiner Domänenzugehörigkeit zugewiesen. Die entsprechenden Kontaktgruppen werden dabei ebenfalls angelegt.

Beschreibung:
icinga-sync legt drei Verzeichnisse an:

    $WORKDIR - Das Arbeitsverzeichnis
    $ICCFGDIR - Das Zielverzeichnis für die Icinga-Konfigdateien
        hostgroups - Das Zielverzeichnis für die Icinga Hostgruppen / Domänen
        hosts - Das Zielverzeichnis für die Gluon-Router Konfigurationsdateien
        contacts - Das Zielverzeichnis für die Kontakte der Gluon-Router

Installation:
Das Script wir sinnvollerweise in /opt/icinga-sync/icinga-sync.sh abgelegt.
Anschließend wird es ausführbar gemacht mit:
chmod +x /opt/icinga-sync/icinga-sync.sh

Im Script müssen folgende Variablen angepasst werden:

    JSONURL Die Adresse der nodes.json Datei (diese sollte die Emailadressen noch enthalten!)
    WORKDIR Das Arbeitsverzeichnis (default ist /opt/icinga-sync/data/)
    ICCFGDIR Zielpfad zum Icinga Konfigurations-Verzeichnis

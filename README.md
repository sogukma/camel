Grundsätzliches
===============

Mit diesem Projekt, welches im Rahmen einer Arbeit im Modul «Enterprise
Application Integration» erfolgt ist, wurde das Backend eines Online-Shops für
Bretzel realisiert. Der Kunde bestellt ein Bretzel, wonach das Lager bearbeitet,
eine Zahlung durchgeführt und die Bestellung geliefert wird.

Der Auftragnehmer ist die Gruppe «Pretzel».

Grober Ablauf des Programms
===========================

Wenn im Browser der Link <https://eshop3.herokuapp.com/order/> eingegeben wird,
wird eine Bestellung abgegeben, welcher dann mithilfe Camels automatisch eine
Zahlung, Lieferung und Kommissionierung auslöst.

Auf der folgenden Seite ist die gesamte Camel-Route aufgeführt.

![](media/e65fce0146867a3e208c83cec132dc60.tmp)

Abbildung 1 gesamte Camel-Route

Ablageort
=========

Zugriff auf das System
----------------------

Die Microservices befinden sich auf Heroku auf folgenden Links:

-   E-Shop (https://eshop3.herokuapp.com/)

    -   Bestellung abgeben: https://eshop3.herokuapp.com/order/

    -   PostgreSQL-Datenbank: <https://eshop3.herokuapp.com/console>
        -   Datenbanktyp unter "Saved Setting" auf "Generic PostgreSQL" stellen
            
        -   Link:
            jdbc:postgresql://ec2-54-75-231-156.eu-west-1.compute.amazonaws.com:5432/dp8lnq31r5456

        -   Username: upxclwfoomsnri

        -   Password:
            4b5f12f5f55f8bfdc76a76502f10d3767734cdaa8c8ae437a83191e8310df3bb

-   Payment (https://payment4.herokuapp.com/)

    -   PostgreSQL-Datenbank: <https://payment4.herokuapp.com/console>
        -   Datenbanktyp unter "Saved Setting" auf "Generic PostgreSQL" stellen
            
        -   Link:
            jdbc:postgresql://ec2-54-247-119-167.eu-west-1.compute.amazonaws.com:5432/ddfoorq2e76vh4

        -   Username: rcugvcoqqxvdye

        -   Password:
            a84ce234dd40f631ddf91085c6489943fb249848316ed985c799b4584148ce22

-   Shipping (https://shipping3.herokuapp.com/)

    -   PostgreSQL-Datenbank: <https://shipping3.herokuapp.com/console/>
        -   Datenbanktyp unter "Saved Setting" auf "Generic PostgreSQL" stellen
            
        -   Link:
            jdbc:postgresql://ec2-54-246-117-62.eu-west-1.compute.amazonaws.com:5432/db6aou0e8v6lf5

        -   Username: cpxmtiwvfpmood

        -   Password:
            781179129de5c9404ec6144e67eacbb706ec876af919e56d8beca1490ded7ffd

-   Inventory(https://inventory4.herokuapp.com/)

    -   PostgreSQL-Datenbank <https://inventory4.herokuapp.com/console/>
        -   Datenbanktyp unter "Saved Setting" auf "Generic PostgreSQL" stellen
            
        -   Link:
            jdbc:postgresql://ec2-54-247-119-167.eu-west-1.compute.amazonaws.com:5432/ddj0eaokfv76fu

        -   Username: svultcwpzswkiq

        -   Password:
            0bb99d1c62cf0d9b11e6e533d82ab968890660bcf583412eccdd6e37b6272aec

-   Camel-Route (https://camel.herokuapp.com/)

-   **Notiz: Ausführung des Programms**
Das Programm sollte ausschliesslich auf Heroku ausgeführt werden. Wenn es lokal ausgeführt wird, werden nämlich trotzdem Services auf Heroku angesprochen, wobei kann es zu Problemen wegen "zu vielen" Zugriffen auf die Datenbank kommen kann.

GitHub-Repositories
-------------------

Die Source-Codes aller Microservices befinden sich auf folgenden Links:

-   E-Shop: https://github.com/sogukma/eshop

-   Payment: https://github.com/sogukma/payment2

-   Shipping: https://github.com/sogukma/shipping

-   Inventory: <https://github.com/sogukma/inventory>

-   Camel: https://github.com/sogukma/camel

Projektordner
-------------

Der Projektorder ist vermischt Andreas Martins Werken und die des Projektteams.
Nachfolgend sind nur die vom Projektteam erstellten oder bearbeiteten Dateien
aufgeführt:

-   **E-Shop**

    -   Folder: rocks.process.integration.eshop/

        -   EShopApplicaton.java: Hier wird Fake Brezel und Customer erstellt

    -   Folder: rocks.process.integration.eshop.api.impl/

        -   CustomerAPIImpl.java

    -   Folder: rocks.process.intergration.eshop.business.client

        -   CheckoutAdapter.java

    -   Folder: rocks.process.integration.eshop.controller /

        -   CheckoutController.java

    -   Folder: rocks.process.integration.eshop.domain /

        -   Customer.java

        -   Pretezl.java

        -   Orders.java

    -   Folder: rocks.process.integration.eshop.service /

        -   OrdersService.java

    -   Folder: src/main/resources

        -   application.yml

-   **Payment**

    -   Folder: rocks.process.integration.payment.api.endpoint/

        -   PaymentEndpoint.java

    -   Folder: rocks.process.integration.payment.business.client/

        -   CustomerServiceClient.java

    -   Folder: rocks.process.intergration.payment.business.service/

        -   PaymentService.java

    -   Folder: rocks.process.integration.payment.data.domain /

        -   Transaction.java:

    -   Folder: src/main/resources

        -   application.yml

-   **Shipping**

    -   Folder: rocks.process.integration.shipping.api /

        -   ShippingEndpoint.java

    -   Folder: rocks.process.integration.shipping.business.client/

        -   CustomerServiceClient.java

    -   Folder: rocks.process.intergration.shipping.business.service/

        -   ShippingService.java

    -   Folder: rocks.process.integration.shipping.domain /

        -   ShippingBill.java:

    -   Folder: src/main/resources

        -   application.yml

-   **Inventory**

    -   Folder: rocks.process.integration.inventory.api /

        -   InventoryEndpoint.java

    -   Folder: rocks.process.integration.inventory.business.client/

        -   CustomerServiceClient.java

    -   Folder: rocks.process.intergration.inventory.business.service/

        -   InventoryService.java

    -   Folder: rocks.process.integration.inventory.domain /

        -   PickingList.java:

    -   Folder: src/main/resources

        -   application.yml

-   **Camel**

    -   Folder: rocks.process.integration.camel.route/

        -   CamelRoutes.java

    -   Folder: src/main/resources

        -   application.yml

Detailliere Dokumentation zu den Klassen sind dem SourceCode zu entnehmen.


Use-Cases
=========

Die Funktionalität über alle Microservices hinweg ist sehr simpel gehalten.

-   E-Shop: «bestellt Brezel»

-   Payment: «stellt Rechnung aus» + «bezahlt Rechnung»

-   Inventory: «kommissioniert Bestellung»

-   Shipping: «schickt Bestestellung ab»

Abbildung 2 UseCase Diagramm

Domain-Objekte
==============

OrderMessage
------------

![](media/d56e8c21a532aa27ad5c395be456f10d.tmp)

Die OrderMessage ist eine Klasse, das in allen fünf Microservices implementiert
ist. Deren Objekte werden hin und wieder in JSON umgewandelt und über REST-APIs
an andere Microservices gesendet. Die OrderMessage beinhaltet alle Attribute,
welche bis zum Ende des Programmdurchlaufs gebraucht werden.

Domain-Objekte im E-Shop
------------------------

Die Domain-Objekte im E-Shop besteht aus den Tabellen «Customer», «Orders» und
«Pretzel». Diese sind im E-Shop entsprechend in der Datenbank abgebildet.

Abbildung 5 Domain-Objekte des E-Shops

Es sind u.a. folgende erklärungsbedürftige Attribute vorhanden:

Customer

-   loyalityPoints: Wenn eine Bestellung eingeht, wird ein Zehntel der
    Totalkosten als Punkte auf die LoyalityPoints addiert. Danach werden die
    gesamten LoyalityPoints in der Zahlung eingesetzt, indem sie die Totalkosten
    vermindern. Nach jeder Bestellung werden von den LoyalityPoints 10 Punkte
    abgezogen.

Orders:

-   status: Status der Bestellung. Wenn eine Bestellung erfolgreich durchgeht,
    wird der Status auf «ordered» gesetzt.

Domain Objekte im Payment
-------------------------

Die Domain-Objekte im Payment besteht u.a. aus der Tabellen «Transaction» und
wird in der Datenbank entsprechend abgebildet. Weitere Domain Objekte im Payment
dienen der Transformation von JSON-Nachrichten.

Es sind u.a. folgende erklärungsbedürftige Attribute vorhanden:

-   chargingAmount: Geldmenge, die abgehoben wurde (exkl. Loyality Points)

-   cardTransactionId: Fake TransaktionsId für die Zahlung

Abbildung 6 Domain-Objekt Transaction

Domain Objekte im Shipping
--------------------------

Die Domain-Objekte im Shipping besteht u.a. aus der Tabellen «ShippingBill» und
wird in der Datenbank entsprechend abgebildet. Weitere Domain Objekte im
Shipping dienen der Transformation von JSON-Nachrichten.

Es sind u.a. folgende erklärungsbedürftige Attribute vorhanden:

-   trackingId: Fake Sendung-Verfolgungsnummer

-   status: Status der Lieferung. Wenn Bestellung geliefert wird, Status auf
    «shipped» gesetzt; wenn nicht genügend Menge auf Lager vorhanden ist auf «in
    queue».

Abbildung 7 Domain-Objekt ShippingBill

Domain Objekte im Inventory
---------------------------

Die Domain-Objekte im Inventory besteht u.a. aus der Tabellen «PickingList» und
wird in der Datenbank entsprechend abgebildet. Weitere Domain Objekte im
Shipping dienen der Transformation von JSON-Nachrichten.

Es sind u.a. folgende Attribute vorhanden:

-   trackingId: Fake Sendung-Verfolgungsnummer

-   status: Status der Kommissionierung. Wenn fertig Kommissioniert wurde, wird
    Status auf «picked» gesetzt; wenn nicht genügend Menge auf Lager vorhanden
    ist auf «in queue».

Abbildung 8 Domain-Objekt PickingList

Verwendung von Libraries/Frameworks
===================================

Das Programm wurde mit dem Maven Framework Spring Boot erstellt.

Datenbank
=========

Bei allen Microservices wird PostgreSQL verwendet, da dieser von Heroku gut
unterstützt wird. Bei jedem der Programme werden die Datenbanken jeweils
gelöscht und neu erstellt. Die Daten dienen nur der Veranschaulichung der
Funktionalität und nicht der Aufbewahrung von Daten.

Kommunikation über Microservices
================================

Die Kommunikation zwischen den Services läuft über REST-APIs, wobei JSON-Files
verwendet werden. Der Prozess und der Nachrichtenaustausch wird über
Camel-Routes gesteuert.

Screenshots
===========

Nachfolgend sind Screenshots von Datenbankeinträgen aufgeführt, die nach zwei
Bestellungseingängen entstanden sind.

![](media/68a62cb3a37933675e9fef8557bccfdf.tmp)

Abbildung 9 Datenbankeinträge E-Shop

![](media/0cf8ea4cb42cb4c8f2592e6b9ec31b58.tmp)

Abbildung 10 Datenbankeinträge Payment

![](media/0955305acf726e964efcae93b64c0bf2.tmp)

Abbildung 11 Datenbankeinträge Shipping

![](media/5609efa7bf6171e20233555f248e8349.tmp)

Abbildung 12 Datenbankeinträge Inventory

Testfälle
=========

Nachfolgend sind alle von uns durchgedachten kritischen Fälle aufgeführt, die
die Funktionalität des Programms nachvollziehbar machen sollen.

| Testfallbeschreibung                                   | Erwartetes Verhalten                                                                 | Eingetretenes Verhalten | Unterschrift Tester                                        |
|--------------------------------------------------------|--------------------------------------------------------------------------------------|-------------------------|------------------------------------------------------------|
| Bestellung im E-Shop funktioniert                      | Nach Eingabe des URL für die Bestellung, wird eine Bestellung abgeschickt            | ok                      | [./media/image14.png](./media/image14.png) Malik Sogukoglu |
| Zahlung funktioniert                                   | Nach Eingabe des URL für die Bestellung, wird eine Zahlung durchgeführt              | ok                      | Malik Sogukoglu                                            |
| Shipping funktioniert                                  | Nach Eingabe des URL für die Bestellung, wird ein Shipping abgeschickt               | ok                      | Malik Sogukoglu                                            |
| Inventory funktioniert                                 | Nach Eingabe des URL für Bestellung, wird eine Kommissionierung durchgeführt         | ok                      | Malik Sogukoglu                                            |
| Loyality Points werden bei Zahlung berücksichtigt      | Bei Bestellung werden Loyality Points von Gesamtkosten abgezogen                     | ok                      | Malik Sogukoglu                                            |
| Loyality Pointy werden korrekt vermehrt                | Bei Bestellung werden Loyality Points um 1/10 der Gesamtkosten vermehrt              | ok                      | Malik Sogukoglu                                            |
| Loyality Points werden nach Zahlung korrekt vermindert | Loyality Points werden nach Zah-lung um 10 Punkte vermindert                         | ok                      | Malik Sogukoglu                                            |
| Lagerbestand wird berücksichtigt beim Shipping         | Wenn zu wenig Lager, wird Bestellung nicht ausgeliefert, sondern in Queue gesetzt    | ok                      | Malik Sogukoglu                                            |
| Lagerbestand wird berücksichtigt beim Inventory        | Wenn zu wenig Lager, wird Bestellung nicht kommissioniert, sondern in Queue gesetzt. | ok                      | Malik Sogukoglu                                            |

Abbildungs- und Tabellenverzeichnis
===================================

Abbildungen
-----------

[Abbildung 1 gesamte Camel-Route 7](#_Toc532072859)

[Abbildung 2 UseCase Diagramm 8](#_Toc532072860)

[Abbildung 3 Inhalt des OrderMessage
9](../../Necati/Dropbox/Pretzel/Pretzel%20Doku.docx#_Toc532072861)

[Abbildung 5 Domain-Objekte des E-Shops 10](#_Toc532072862)

[Abbildung 6 Domain-Objekt Transaction 11](#_Toc532072863)

[Abbildung 7 Domain-Objekt ShippingBill 11](#_Toc532072864)

[Abbildung 8 Domain-Objekt PickingList 12](#_Toc532072865)

[Abbildung 9 Datenbankeinträge E-Shop 13](#_Toc532072866)

[Abbildung 10 Datenbankeinträge Payment 13](#_Toc532072867)

[Abbildung 11 Datenbankeinträge Shipping 14](#_Toc532072868)

[Abbildung 12 Datenbankeinträge Inventory 14](#_Toc532072869)

Selbständigkeitserklärung 
==========================

Wir bestätigen hiermit, die vorliegende Arbeit selbständig verfasst zu haben.
Sämtliche Textstellen, die nicht von uns stammen, sind als Zitate gekennzeichnet
und mit genauem Hinweis auf ihre Herkunft versehen. Die verwendeten Quellen
(auch Abbildungen, Tabellen, Grafiken u.ä.) sind im Literaturverzeichnis
aufgeführt.

![](media/abb9b37a562477cbaff6b02cd7e28580.png)

Malik Sogukoglu

![](media/5150e2c18df2c8819246bfb008050062.png)

Halil Cenik

![](media/596ea89346715bdd7f5a59f875c00c5a.png)

Necati Van

![](media/9bf04c818f546499c74320a65b4def48.jpg)

Petar Mandir

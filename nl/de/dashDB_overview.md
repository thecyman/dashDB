---

copyright:
  years: 2014, 2017
lastupdated: "2017-05-16"

---

<!-- Attribute definitions --> 
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:pre: .pre}

#Informationen zu dashDB
{: #dashDB_overview}

{{site.data.keyword.IBM}} {{site.data.keyword.dashdbshort}} stellt zwei verschiedene Datenbanklösungen bereit: eine Data-Warehousing- und Analyselösung ({{site.data.keyword.dashdbshort_notm}} for Analytics-Pläne) und eine Onlinetransaktionsverarbeitungslösung ({{site.data.keyword.dashdbshort_notm}} for Transactions-Pläne).
{: shortdesc}

##Verwalteter dashDB-Service
{: #managed_service}

Der vollständig verwaltete Service von {{site.data.keyword.dashdbshort_notm}} verarbeitet alle Software-Upgrades, Betriebssystemaktualisierungen und Hardwarewartungstasks. Der Service umfasst die 24x7-Statusüberwachung der Datenbank und der Infrastruktur. Beim Auftreten eines Hardware- oder Softwarefehlers wird der Service automatisch neu gestartet.
{: shortdesc}

Weitere Informationen zu den Aspekten eines verwalteten Service von {{site.data.keyword.dashdbshort_notm}} finden Sie in [Verwalteter {{site.data.keyword.dashdbshort_notm}}-Service ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/managed_service.html).

##Pläne und Konfigurationen
{: #plans_cfgs}

Sie können einen {{site.data.keyword.dashdbshort_notm}}-Plan auswählen, der für die jeweiligen Aufgaben konfiguriert und optimiert ist:
{: shortdesc}

   * Einstiegsplan zum Testen der Funktionen
   * Kleine, mittlere und große Pläne für die Produktion
   * MPP-Konfigurationen für die parallele Verarbeitung
   * Für die Hochverfügbarkeit oder für die Oracle-Kompatibilität konfigurierte Pläne
   * Und mehr...

Sie können die verfügbaren Pläne im {{site.data.keyword.Bluemix}}-Katalog anzeigen: 
   * Für Data-Warehouse- und Analyse-Workloads (OLAP) konfigurierte Pläne: [{{site.data.keyword.dashdbshort_notm}} for Analytics](https://console.ng.bluemix.net/catalog/services/dashdb-for-analytics){:new_window}
   * Für transaktionsorientierte Hochgeschwindigkeitsverarbeitung (OLTP) konfigurierte Pläne: [{{site.data.keyword.dashdbshort_notm}} for Transactions](https://console.ng.bluemix.net/catalog/services/dashdb-for-transactions-sql-database){:new_window}

Wenn die benötigte Konfiguration im Katalog nicht angezeigt wird, [wenden Sie sich an {{site.data.keyword.IBM_notm}} Sales ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://www.ibm.com/connect/ibm/us/en/?lnk=fcw){:new_window}, um sich über weitere Optionen zu informieren.


##dashDB for Analytics
{: #dashDB_an}

Verwenden Sie in den {{site.data.keyword.dashdbshort_notm}} for Analytics-Data-Warehouse-Plänen das {{site.data.keyword.dashdbshort_notm}}-Data-Warehouse zum Speichern relationaler Daten, einschließlich spezieller Datentypen wie Geodaten. Analysieren Sie eigene oder von anderen Cloud-Services geladene Daten unter Verwendung der integrierten Analysefunktionen oder durch Verbinden Ihrer eigenen Apps. Sie können die leistungsfähige, speicherinterne Datenbanktechnologie mit Spaltentabellen für analytische Workloads nutzen. Die {{site.data.keyword.dashdbshort_notm}}-Webkonsole verarbeitet allgemeine Datenverwaltungstasks wie das Laden von Daten und Analysetasks wie das Ausführen von Abfragen und R-Scripts.
{: shortdesc}

Sie können auch externe Anwendungen und Tools mit {{site.data.keyword.dashdbshort_notm}} verbinden und diese zur weiteren Verwaltung und Analyse der Daten verwenden. Beispiele:
   * Verbindung mit {{site.data.keyword.IBM_notm}} InfoSphere® Data Architect für den Entwurf und die Bereitstellung des Datenbankschemas.
   * Verbindung mit Esri ArcGIS für die Durchführung von Geodatenanalysen und das Veröffentlichen von Karten mit Ihren Daten.
   * Verbindung mit einem {{site.data.keyword.IBM_notm}} Cognos®-Server zur Ausführung von Cognos-Berichten für Ihre Daten.
   * Verbindung mit SQL-basierten Tools wie Tableau, Microstrategy oder Microsoft Excel für die Datenbearbeitung oder -analyse.
   * Verbindung Ihrer {{site.data.keyword.Bluemix_short}}-Anwendungen, die eine Analysedatenbank benötigen.
   * Verbindung mit Aginity Workbench für die Migration von Netezza®-Datenmodellen und -Daten in {{site.data.keyword.dashdbshort_notm}}.

##Bereitstellen von dashDB for Analytics
{: #whse_provision}

Das {{site.data.keyword.IBM_notm}} {{site.data.keyword.dashdbshort_notm}} for Analytics-Data-Warehouse kann in {{site.data.keyword.BluSoftlayer_full}} und für AWS bereitgestellt werden.
{: shortdesc}

Wenn das {{site.data.keyword.dashdbshort_notm}} for Analytics-Data-Warehouse für AWS bereitgestellt werden soll, wählen Sie den Plan **{{site.data.keyword.IBM_notm}} {{site.data.keyword.dashdbshort_notm}} for Analytics MPP Small for AWS** aus.

##dashDB for Transactions
{: #dashDB_tr}

Verwenden Sie in den {{site.data.keyword.dashdbshort_notm}} for Transactions-Plänen die relationale {{site.data.keyword.dashdbshort_notm}}-Datenbank für die Onlinetransaktionsverarbeitung. Sie können neue oder vorhandene Anwendungen verbinden und mit dem Verarbeiten von Transaktionen und dem Speichern Ihrer Daten beginnen. Die Kompatibilität mit DB2® und Oracle ermöglicht das Verbinden kleiner oder großer Anwendungen sowie die Nutzung eines verwalteten Datenbanksystems, das auf Großunternehmen abgestimmt ist. Sie können die Vorteile der {{site.data.keyword.dashdbshort_notm}} for Transactions-Webkonsole zum Verwalten von Benutzern, Laden von Daten und Abrufen von Verbindungsinformationen nutzen.
{: shortdesc}

<!-- ##dashDB web console overview
{: #console_overview}

You can manage your {{site.data.keyword.dashdbshort_notm}} database, analyze your data, and monitor sensitive data with the {{site.data.keyword.dashdbshort_notm}} web console accessible from {{site.data.keyword.Bluemix_notm}}.
{: shortdesc}

Open the web console by clicking the service tile on your application overview page, and then click **Open**.

Single sign-on authentication connects you directly to the web console. You can access connection information from the web console, and the **Downloads** page includes links to client drivers for accessing {{site.data.keyword.dashdbshort_notm}} from remote applications. You can also access sample data and reports.

###Sensitive data reporting

The {{site.data.keyword.dashdbshort_notm}} web console includes a sensitive data reporting feature that detects and monitors sensitive objects in the {{site.data.keyword.dashdbshort_notm}} data warehouse, such as credit card numbers and US Social Security numbers.

To run and view reports that identify columns that contain sensitive data and provide information about connections and activities that access the sensitive data, select **Monitor &gt; Sensitive Data** in the web console. -->


<!-- ##IBM Analytics Services
{: #analytics_services}

For more information about {{site.data.keyword.IBM_notm}} analytics services and finding your local services representative, see: [{{site.data.keyword.IBM_notm}} Analytics Services ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://www.ibm.com/software/data/services/).
{: shortdesc} -->















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

#Informazioni su dashDB
{: #dashDB_overview}

Sono disponibili due differenti soluzioni database fornite da {{site.data.keyword.IBM}} {{site.data.keyword.dashdbshort}}: una soluzione di immagazzinamento (warehouse) e di analisi dei dati (piani {{site.data.keyword.dashdbshort_notm}} for Analytics) e una soluzione di elaborazione delle transazioni online (piani {{site.data.keyword.dashdbshort_notm}} for Transactions).
{: shortdesc}

##Servizio gestito da dashDB
{: #managed_service}

Il servizio pienamente gestito di {{site.data.keyword.dashdbshort_notm}} gestisce tutti
gli aggiornamenti software, gli aggiornamenti del sistema operativo e la manutenzione hardware. Il servizio include un monitoraggio dell'integrità sette giorni alla settimana, 24 ore su 24. In caso di malfunzionamento hardware o software, il servizio viene riavviato automaticamente.
{: shortdesc}

Per ulteriori informazioni sugli aspetti del servizio gestito di {{site.data.keyword.dashdbshort_notm}}, vedi: [Servizio gestito da {{site.data.keyword.dashdbshort_notm}} ![Icona di link esterno](../../icons/launch-glyph.svg "Icona di link esterno")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/managed_service.html).

##Piani e configurazioni
{: #plans_cfgs}

Puoi scegliere un piano {{site.data.keyword.dashdbshort_notm}} configurato e ottimizzato per il lavoro che devi eseguire:
{: shortdesc}

   * Un piano d'ingresso per provare le funzionalità offerte
   * Piani piccoli, medi e grandi per la produzione
   * Configurazioni MPP per l'elaborazione parallela
   * Piani configurati per l'alta disponibilità o per la compatibilità Oracle
   * E altro ...

Visualizza i piani disponibili nel catalogo {{site.data.keyword.Bluemix}}:
   * Piani configurati per i carichi di lavoro di immagazzinamento (warehouse) e analisi dei dati (OLAP): [{{site.data.keyword.dashdbshort_notm}} for Analytics](https://console.ng.bluemix.net/catalog/services/dashdb-for-analytics){:new_window}
   * Piani configurati per l'elaborazione transazionale ad alta velocità (OLTP): [{{site.data.keyword.dashdbshort_notm}} for Transactions](https://console.ng.bluemix.net/catalog/services/dashdb-for-transactions-sql-database){:new_window}

Se nel catalogo non vedi una configurazione che risponda alle tue esigenze, [contatta il reparto vendite {{site.data.keyword.IBM_notm}} ![Icona di link esterno](../../icons/launch-glyph.svg "Icona di link esterno")](https://www.ibm.com/connect/ibm/us/en/?lnk=fcw){:new_window} per discutere delle altre opzioni.

##dashDB for Analytics
{: #dashDB_an}

Nei piani di data warehouse {{site.data.keyword.dashdbshort_notm}} for Analytics, usa il data warehouse {{site.data.keyword.dashdbshort_notm}} per archiviare i dati relazionali, compresi i tipi speciali quali i dati geospaziali. Analizza i tuoi dati, o i dati caricati da altri servizi cloud,
utilizzando la nostra analisi integrata oppure connettendo delle tue applicazioni. Puoi avvalerti della tecnologia di database in memoria ad elevate
prestazioni con tabelle a colonne per i carichi di lavoro di analisi. La console web {{site.data.keyword.dashdbshort_notm}} gestisce
le comuni attività di gestione dei dati, ad esempio il caricamento di dati, e le attività di analisi come l'esecuzione di query e di script
R.
{: shortdesc}

Puoi anche
connettere applicazioni e strumenti esterni a {{site.data.keyword.dashdbshort_notm}} e
utilizzarli per un'ulteriore gestione o analisi dei dati. Ad esempio:
   * Connetti {{site.data.keyword.IBM_notm}} InfoSphere® Data Architect per progettare e distribuire il tuo schema di database.
   * Connetti Esri ArcGIS per eseguire l'analisi geospaziale e associare la pubblicazione
ai dati.
   * Connetti un server {{site.data.keyword.IBM_notm}} Cognos® per eseguire i report Cognos sui tuoi dati.
   * Connetti gli strumenti basati su SQL quali Tableau, Microstrategy o Microsoft Excel per manipolare o analizzare i tuoi dati.
   * Connetti le tue applicazioni {{site.data.keyword.Bluemix_short}} che necessitano di
un database di analisi.
   * Connetti Aginity Workbench per migrare i modelli di dati e i dati Netezza® a {{site.data.keyword.dashdbshort_notm}}.

##Esecuzione del provisioning di dashDB for Analytics
{: #whse_provision}

È possibile eseguire il provisioning del data warehouse {{site.data.keyword.IBM_notm}} {{site.data.keyword.dashdbshort_notm}} for Analytics su {{site.data.keyword.BluSoftlayer_full}} e per AWS.
{: shortdesc}

Se vuoi che venga eseguito il provisioning del data warehouse {{site.data.keyword.dashdbshort_notm}} for Analytics per AWS, seleziona il piano **{{site.data.keyword.IBM_notm}} {{site.data.keyword.dashdbshort_notm}} for Analytics MPP Small for AWS**.

##dashDB for Transactions
{: #dashDB_tr}

Nei piani {{site.data.keyword.dashdbshort_notm}} for Transactions,
utilizza il database relazionale {{site.data.keyword.dashdbshort_notm}} per l'elaborazione
delle transazioni online. Puoi connettere le applicazioni nuove o esistenti e puoi avviare l'elaborazione delle transazioni e la
memorizzazione dei tuoi dati. Con la compatibilità DB2® e Oracle, puoi connettere applicazioni grandi o piccole e avvalerti di un sistema di database di classe aziendale gestito. Puoi sfruttare la
console web {{site.data.keyword.dashdbshort_notm}} for Transactions per gestire utenti, caricare dati
e ottenere informazioni di connessione.
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















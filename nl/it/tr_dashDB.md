---

copyright:
  years: 2014, 2017
lastupdated: "2017-05-16"

---

<!-- Attribute definitions --> 
{:tsSymptoms: .tsSymptoms} 
{:tsCauses: .tsCauses} 
{:tsResolve: .tsResolve} 
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:pre: .pre}

#Risoluzione dei problemi di dashDB 
{: #tr_dashDB}

Di seguito sono riportate le risposte alle domande più frequenti relative all'utilizzo di {{site.data.keyword.dashdbshort}} in {{site.data.keyword.Bluemix_short}}.
{: shortdesc}

##Impossibile accedere a RStudio
{: #r_studio}

SSO (single sign-on) per RStudio non è disponibile per {{site.data.keyword.dashdblong}}.
{: shortdesc}

Vuoi accedere a RStudio da {{site.data.keyword.dashdbshort_notm}} utilizzando SSO, ma ti viene richiesta una password.
{: tsSymptoms}

SSO per RStudio non è disponibile in {{site.data.keyword.dashdbshort_notm}}.
{: tsCauses}

Per ottenere le tue credenziali per RStudio, consulta la tua variabile di ambiente `VCAP_SERVICES`. Ulteriori informazioni sono disponibili n [Introduzione a {{site.data.keyword.dashdbshort_notm}}](/docs/services/dashDB/dashDB.html#dashDB){:new_window}.
{: tsResolve}


##Impossibile trovare il file `diag.log` per la risoluzione dei problemi
{: #diag_log}

Il file `diag.log` non è disponibile
{: shortdesc}

Vuoi risolvere il problema ma non riesci a trovare il file `diag.log`
per {{site.data.keyword.dashdbshort_notm}}.
{: tsSymptoms}

Il file `diag.log` non è disponibile su {{site.data.keyword.dashdbshort_notm}} né lo è qualsiasi altro log specifico per DB2®.
{: tsCauses}

I log specifici dell'applicazione sono accessibili tramite la CLI
(command line interface) di Cloud Foundry. Dalla CLI, immetti **cf
logs --recent**. I log sono accessibili anche dal sito {{site.data.keyword.Bluemix_notm}}
selezionando la tua applicazione e passando a **File e log**.
{: tsResolve}

##Impossibile trovare l'organizzazione o lo spazio: ID Bluemix non corrispondente
{: #org_space_id}

Impossibile trovare un'organizzazione o uno spazio per una nuova istanza {{site.data.keyword.dashdbshort_notm}}.
{: shortdesc}

Vuoi creare una nuova istanza del servizio {{site.data.keyword.dashdbshort_notm}} in {{site.data.keyword.Bluemix_notm}} utilizzando la funzione di immagazzinamento (warehouse) nel dashboard Cloudant® ma ricevi il seguente messaggio di errore: `Impossibile trovare l'organizzazione o lo spazio.`
{: tsSymptoms}

Per eseguire il provisioning di una nuova istanza del servizio {{site.data.keyword.dashdbshort_notm}} in {{site.data.keyword.Bluemix_notm}}, la funzione di immagazzinamento (warehouse) Cloudant
tenta di trovare l'organizzazione di destinazione {{site.data.keyword.Bluemix_notm}} "più adatta" per l'utente {{site.data.keyword.Bluemix_notm}} autenticato. Di norma, la funzione di immagazzinamento (warehouse) cerca un'organizzazione corrispondente all'ID
{{site.data.keyword.Bluemix_notm}}, ossia
un ID che in genere è l'indirizzo e-mail dell'utente. Se non viene trovata
un'organizzazione corrispondente e l'utente ha accesso a una sola organizzazione,
la funzione di immagazzinamento (warehouse) seleziona tale organizzazione. Potrebbero esserci dei casi
in cui l'utente non abbia accesso ad alcuna organizzazione o
disponga dell'accesso a più organizzazioni. In queste situazioni, Cloudant non
può determinare dove eseguire il provisioning dell'istanza {{site.data.keyword.dashdbshort_notm}} e viene visualizzato il messaggio di errore.
{: tsCauses}

Per risolvere il problema, scegli
una delle seguenti opzioni:
{: tsResolve}

* Dall'elenco a discesa del dashboard Cloudant, seleziona l'organizzazione {{site.data.keyword.Bluemix_notm}} in cui desideri che venga creata l'istanza {{site.data.keyword.dashdbshort_notm}}. Dopo aver selezionato l'organizzazione, seleziona lo
spazio appropriato dall'elenco a discesa secondario.
* Esegui manualmente il provisioning di un'istanza {{site.data.keyword.dashdbshort_notm}} direttamente in {{site.data.keyword.Bluemix_notm}} e seleziona l'istanza del servizio {{site.data.keyword.dashdbshort_notm}} creata dall'elenco a discesa presente nel dashboard Cloudant.


##Impossibile trovare l'organizzazione o lo spazio: regione non corrispondente
{: #org_space_region}

Impossibile trovare un'organizzazione o uno spazio per una nuova istanza {{site.data.keyword.dashdbshort_notm}}.
{: shortdesc}

Vuoi creare una nuova istanza del servizio {{site.data.keyword.dashdbshort_notm}},
ma gli elenchi a discesa delle istanza del servizio {{site.data.keyword.dashdbshort_notm}}
o delle organizzazioni {{site.data.keyword.Bluemix_notm}} esistenti
sono vuoti. Non è possibile eseguire il provisioning di una nuova istanza del servizio {{site.data.keyword.dashdbshort_notm}} e ricevi il seguente messaggio di errore: `Impossibile trovare l'organizzazione o lo spazio.`
{: tsSymptoms}

Se l'account {{site.data.keyword.Bluemix_notm}} dell'utente si trova in una regione diversa da quella del cluster Cloudant, la richiesta di provisioning non riesce. Ad esempio, l'account {{site.data.keyword.Bluemix_notm}} è stato caricato nella regione Europa Regno Unito, ma il cluster Cloudant funziona con la regione Stati Uniti Sud. Di conseguenza, gli elenchi a discesa delle organizzazioni e istanze del servizio esistenti nel dashboard Cloudant potrebbero essere vuoti o mostrare organizzazioni e spazi appartenenti a
regioni differenti.
{: tsCauses}

1. Accedi al dashboard {{site.data.keyword.Bluemix_notm}}
e passa alla regione prevista. Attieniti alle richieste che ti vengono presentate per completare
il caricamento in tale regione. In alternativa, crea un account {{site.data.keyword.Bluemix_notm}}
nella regione appropriata.
2. Accedi al dashboard Cloudant per ripetere la selezione dell'istanza del servizio {{site.data.keyword.dashdbshort_notm}}.
{: tsResolve}

##Limite dei servizi superato
{: #service_limit}

Il servizio {{site.data.keyword.dashdbshort_notm}}
in {{site.data.keyword.Bluemix_notm}} ha superato
il suo limite.
{: shortdesc}

Durante l'utilizzo del servizio {{site.data.keyword.dashdbshort_notm}} in {{site.data.keyword.Bluemix_notm}}, viene visualizzato il seguente messaggio di errore: `È stato superato il limite dei servizi dell'organizzazione.`
{: tsSymptoms}

Stai ancora utilizzando la versione di prova gratuita di {{site.data.keyword.Bluemix_notm}},
che prevede dei limiti di servizio.
{: tsCauses}

Per risolvere il problema, scegli
una delle seguenti opzioni:
{: tsResolve}

* Per liberare delle risorse, dal dashboard {{site.data.keyword.Bluemix_notm}} elimina i servizi
che non utilizzi più. Ritenta la richiesta di provisioning per una nuova istanza {{site.data.keyword.dashdbshort_notm}}.
* Utilizza il dashboard {{site.data.keyword.Bluemix_notm}}
per eseguire manualmente il provisioning di un'istanza {{site.data.keyword.dashdbshort_notm}}
in un'organizzazione o spazio appropriato che non abbia limiti di
servizio. Seleziona tale istanza dal dashboard Cloudant.


##Il servizio dashDB non è disponibile
{: #outages}

Il servizio {{site.data.keyword.dashdbshort_notm}}
in {{site.data.keyword.Bluemix_notm}} potrebbe
non essere disponibile.
{: shortdesc}

Il tentativo di creare un data warehouse non riesce con un errore 500
o un caricamento SDP segnala un errore SQL.
{: tsSymptoms}

Il servizio {{site.data.keyword.dashdbshort_notm}}
in {{site.data.keyword.Bluemix_notm}} è
sottoposto a una procedura di manutenzione pianificata o si è verificata un'interruzione
nota.
{: tsCauses}

È possibile determinare lo stato del servizio {{site.data.keyword.dashdbshort_notm}}
in {{site.data.keyword.Bluemix_notm}}
controllando le seguenti pagine sullo stato:
{: tsResolve}

* [Supporto {{site.data.keyword.Bluemix_notm}} ![Icona di link esterno](../../icons/launch-glyph.svg "Icona di link esterno")](https://developer.ibm.com/bluemix/support/#status){:new_window}
* Monitoraggio dello stato:
  * [Tutte le regioni ![Icona di link esterno](../../icons/launch-glyph.svg "Icona di link esterno")](https://console.eu-gb.bluemix.net/status?tags=platform,runtimes,services,ibm:yp:eu-gb,ibm:yp:eu-de,ibm:yp:us-south,ibm:yp:au-syd){:new_window}
  <!--[US - South region ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://estado.ng.bluemix.net/internalstatus){:new_window}
  [Europe - United Kingdom region ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://estado.eu-gb.bluemix.net/internalstatus){:new_window}
  [Europe - Germany region ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://estado.eu-de.bluemix.net/internalstatus){:new_window}
  [Australia - Sydney region ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://estado.au-syd.bluemix.net/internalstatus){:new_window}-->


##Come ottenere aiuto e supporto per dashDB
{: #gettinghelp}

Se hai dei problemi o delle domande quando utilizzi {{site.data.keyword.dashdbshort_notm}},
puoi ottenere aiuto ricercando le informazioni o facendo delle domande in un forum. Puoi inoltre aprire un ticket di supporto.
{: shortdesc}

Quando utilizzi i forum per fare una domanda, contrassegna con una tag la tua domanda in modo che sia visualizzabile dai team di sviluppo {{site.data.keyword.Bluemix}}.

* Se hai domande tecniche sullo sviluppo o la distribuzione di un'applicazione con {{site.data.keyword.dashdbshort_notm}}, pubblica la tua domanda in [Stack Overflow ![Icona di link esterno](../../icons/launch-glyph.svg "Icona di link esterno")](http://stackoverflow.com/search?q=dashdb+bluemix){:new_window} e contrassegnala con le tag "bluemix" e "dashdb".
* Per domande sul servizio e per le istruzioni introduttive, usa il forum [IBM developerWorks® dW Answers ![Icona di link esterno](../../icons/launch-glyph.svg "Icona di link esterno")](https://developer.ibm.com/answers/topics/dashdb/?smartspace=bluemix){:new_window}. Includi le tag "bluemix" e "dashdb".

Consulta [Come ottenere supporto](/docs/support/index.html#getting-help){:new_window} per ulteriori dettagli sull'utilizzo dei forum.

Per informazioni su come aprire un ticket di supporto IBM o sui livelli di supporto e sulla gravità dei ticket, consulta: [Come contattare il supporto](/docs/support/index.html#contacting-support){:new_window}.




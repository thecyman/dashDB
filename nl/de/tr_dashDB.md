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

#dashDB - Fehlerbehebung 
{: #tr_dashDB}

Hier finden Sie Antworten auf einige häufig gestellte Fragen zur Verwendung von {{site.data.keyword.dashdbshort}} in {{site.data.keyword.Bluemix_short}}.
{: shortdesc}

##Anmeldung bei RStudio nicht möglich
{: #r_studio}

Single Sign-on (SSO) für RStudio ist für {{site.data.keyword.dashdblong}} nicht verfügbar.
{: shortdesc}

Sie möchten sich in {{site.data.keyword.dashdbshort_notm}} mit SSO bei RStudio anmelden, werden aber zur Eingabe eines Kennworts aufgefordert.
{: tsSymptoms}

SSO für RStudio ist in {{site.data.keyword.dashdbshort_notm}} nicht verfügbar.
{: tsCauses}

Die Berechtigungsnachweise für RStudio sind in der Umgebungsvariablen `VCAP_SERVICES` enthalten. Weitere Informationen finden Sie in [Einführung in {{site.data.keyword.dashdbshort_notm}}](/docs/services/dashDB/dashDB.html#dashDB){:new_window}.
{: tsResolve}


##Datei `diag.log` zur Fehlerbehebung kann nicht gefunden werden.
{: #diag_log}

Die Datei `diag.log` ist nicht verfügbar.
{: shortdesc}

Sie möchten eine Fehlerbehebung durchführen und können die Datei `diag.log` für {{site.data.keyword.dashdbshort_notm}} nicht finden.
{: tsSymptoms}

Die Datei `diag.log` ist in {{site.data.keyword.dashdbshort_notm}} nicht verfügbar. Dasselbe gilt für alle anderen für DB2® spezifischen Protokolle.
{: tsCauses}

Der Zugriff auf die anwendungsspezifischen Protokolle ist über die Cloud Foundry-Befehlszeilenschnittstelle möglich. Geben Sie in der Befehlszeilenschnittstelle **cf logs --recent** ein. Der Zugriff auf die Protokolle ist auch über die {{site.data.keyword.Bluemix_notm}}-Site möglich. Wählen Sie hierfür Ihre App aus und rufen Sie **Dateien und Protokolle** auf.
{: tsResolve}

##Organisation oder Bereich kann nicht gefunden werden: Abweichung bei Bluemix-ID
{: #org_space_id}

Für eine neue {{site.data.keyword.dashdbshort_notm}}-Instanz kann keine Organisation bzw. kein Bereich gefunden werden.
{: shortdesc}

Sie möchten eine neue {{site.data.keyword.dashdbshort_notm}}-Serviceinstanz in {{site.data.keyword.Bluemix_notm}} erstellen, indem Sie das Warehousing-Feature im Cloudant®-Dashboard verwenden, es wird jedoch die folgende Fehlernachricht ausgegeben: `Organisation oder Bereich kann nicht gefunden werden.`
{: tsSymptoms}

Für die Bereitstellung einer neuen {{site.data.keyword.dashdbshort_notm}}-Serviceinstanz in {{site.data.keyword.Bluemix_notm}} versucht das Cloudant-Warehousing-Feature, die am besten geeignete {{site.data.keyword.Bluemix_notm}}-Zielorganisation für den authentifizierten {{site.data.keyword.Bluemix_notm}}-Benutzer zu finden. Das Warehousing-Feature sucht in der Regel nach einer Organisation, die der {{site.data.keyword.Bluemix_notm}}-ID entspricht; bei dieser ID handelt es sich gewöhnlich um die E-Mail-Adresse des Benutzers. Wird keine passende Organisation gefunden und hat der Benutzer lediglich auf eine einzige Organisation Zugriff, wählt das Warehousing-Feature diese Organisation aus. Es kann Situationen geben, in denen der Benutzer keine Organisation hat, auf die ein Zugriff möglich ist, oder in denen der Benutzer Zugriff auf mehrere Organisationen hat. In diesen Situationen kann Cloudant nicht feststellen, wo die {{site.data.keyword.dashdbshort_notm}}-Instanz bereitgestellt werden soll, und die Fehlernachricht wird ausgegeben.
{: tsCauses}

Wählen Sie eine der folgenden Optionen, um das Problem zu beheben:
{: tsResolve}

* Wählen Sie in der Dropdown-Liste im Cloudant-Dashboard die {{site.data.keyword.Bluemix_notm}}-Organisation aus, in der die {{site.data.keyword.dashdbshort_notm}}-Instanz erstellt werden soll. Nach der Auswahl der Organisation wählen Sie in der sekundären Dropdown-Liste den entsprechenden Bereich aus.
* Stellen Sie eine {{site.data.keyword.dashdbshort_notm}}-Instanz direkt in {{site.data.keyword.Bluemix_notm}} manuell bereit und wählen Sie die erstellte {{site.data.keyword.dashdbshort_notm}}-Serviceinstanz in der Dropdown-Liste im Cloudant-Dashboard aus. 


##Organisation oder Bereich kann nicht gefunden werden: Abweichung bei Region
{: #org_space_region}

Für eine neue {{site.data.keyword.dashdbshort_notm}}-Instanz kann keine Organisation bzw. kein Bereich gefunden werden.
{: shortdesc}

Sie möchten eine neue Instanz des Service {{site.data.keyword.dashdbshort_notm}} erstellen, doch die Dropdown-Listen der vorhandenen Instanzen des Service {{site.data.keyword.dashdbshort_notm}} bzw. der {{site.data.keyword.Bluemix_notm}}-Organisationen sind leer. Eine neue {{site.data.keyword.dashdbshort_notm}}-Serviceinstanz kann nicht bereitgestellt werden und die folgende Fehlernachricht wird ausgegeben: `Organisation oder Bereich kann nicht gefunden werden.`
{: tsSymptoms}

Wenn sich das {{site.data.keyword.Bluemix_notm}}-Konto des Benutzers in einer anderen Region befindet als der Cloudant-Cluster, schlägt die Bereitstellungsanforderung fehl. Beispiel: Für das {{site.data.keyword.Bluemix_notm}}-Konto wurde in der Region 'Europa - Vereinigtes Königreich' ein Onboarding durchgeführt, der Cloudant-Cluster verwendet jedoch die Region 'Vereinigte Staaten - Süd'. Dies führt dazu, dass die Dropdown-Listen für die vorhandenen Serviceinstanzen und Organisationen im Cloudant-Dashboard leer sein können oder dass Organisationen und Bereiche angezeigt werden, die einer völlig anderen Region zugeordnet sind.
{: tsCauses}

1. Melden Sie sich beim {{site.data.keyword.Bluemix_notm}}-Dashboard an und wechseln Sie zu der erwarteten Region. Folgen Sie allen Eingabeaufforderungen und führen Sie das Onboarding in dieser Region durch. Alternativ dazu können Sie in der entsprechenden Region ein {{site.data.keyword.Bluemix_notm}}-Konto erstellen. 
2. Melden Sie sich beim Cloudant-Dashboard an und wiederholen Sie die Auswahl für die {{site.data.keyword.dashdbshort_notm}}-Serviceinstanz.
{: tsResolve}

##Überschrittener Servicegrenzwert
{: #service_limit}

Für den Service {{site.data.keyword.dashdbshort_notm}} in {{site.data.keyword.Bluemix_notm}} wurde der Grenzwert überschritten.
{: shortdesc}

Bei der Verwendung des {{site.data.keyword.dashdbshort_notm}}-Service in {{site.data.keyword.Bluemix_notm}} wird die folgende Fehlernachricht angezeigt: `Sie haben die Speicherbegrenzung für Ihre Organisation überschritten.`
{: tsSymptoms}

Sie verwenden immer noch die gebührenfreie {{site.data.keyword.Bluemix_notm}}-Testversion, für die es Einschränkungen beim Service gibt.
{: tsCauses}

Wählen Sie eine der folgenden Optionen, um das Problem zu beheben:
{: tsResolve}

* Um Ressourcen freizugeben, löschen Sie ungenutzte Services in Ihrem {{site.data.keyword.Bluemix_notm}}-Dashboard. Wiederholen Sie die Bereitstellungsanforderung für eine neue Instanz von {{site.data.keyword.dashdbshort_notm}}.
* Mit dem {{site.data.keyword.Bluemix_notm}}-Dashboard können Sie eine {{site.data.keyword.dashdbshort_notm}}-Instanz in einer entsprechenden Organisation bzw. einem entsprechenden Bereich manuell bereitstellen, die/der keine Serviceeinschränkungen hat. Wählen Sie diese Instanz im Cloudant-Dashboard aus.


##Service 'dashDB' ist nicht verfügbar
{: #outages}

Der Service {{site.data.keyword.dashdbshort_notm}} in {{site.data.keyword.Bluemix_notm}} ist möglicherweise nicht verfügbar.
{: shortdesc}

Ein Versuch, ein Data-Warehouse zu erstellen, schlägt mit dem Fehler 500 fehl, oder ein SDP-Load meldet einen SQL-Fehler.
{: tsSymptoms}

Der Service {{site.data.keyword.dashdbshort_notm}} in {{site.data.keyword.Bluemix_notm}} wird momentan einer geplanten Wartung unterzogen oder es kam zu einer geplanten Unterbrechung.
{: tsCauses}

Sie können den Status des Service {{site.data.keyword.dashdbshort_notm}} in {{site.data.keyword.Bluemix_notm}} durch Überprüfen der folgenden Statusseiten feststellen:
{: tsResolve}

* [{{site.data.keyword.Bluemix_notm}}-Support ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://developer.ibm.com/bluemix/support/#status){:new_window}
* Statusüberwachung:
  * [Alle Regionen ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://console.eu-gb.bluemix.net/status?tags=platform,runtimes,services,ibm:yp:eu-gb,ibm:yp:eu-de,ibm:yp:us-south,ibm:yp:au-syd){:new_window}
  <!--[US - South region ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://estado.ng.bluemix.net/internalstatus){:new_window}
  [Europe - United Kingdom region ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://estado.eu-gb.bluemix.net/internalstatus){:new_window}
  [Europe - Germany region ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://estado.eu-de.bluemix.net/internalstatus){:new_window}
  [Australia - Sydney region ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://estado.au-syd.bluemix.net/internalstatus){:new_window}-->


##Hilfe und Unterstützung für dashDB anfordern
{: #gettinghelp}

Sollten bei der Verwendung von {{site.data.keyword.dashdbshort_notm}} Probleme auftreten oder Fragen entstehen, können Sie nach Informationen suchen oder Fragen in einem Forum stellen. Sie haben auch die Möglichkeit, ein Support-Ticket zu öffnen.
{: shortdesc}

Wenn Sie zum Stellen einer Frage die Foren nutzen, versehen Sie Ihre Frage mit entsprechenden Tags, damit die {{site.data.keyword.Bluemix}}-Entwicklerteams Ihre Frage auf Anhieb erkennen können.

* Wenn Sie technische Fragen zur Entwicklung oder Bereitstellung einer App mit {{site.data.keyword.dashdbshort_notm}} haben, posten Sie die Fragen in [Stack Overflow ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](http://stackoverflow.com/search?q=dashdb+bluemix){:new_window} und kennzeichnen Sie die Frage mit den Tags "bluemix" und "dashdb".
* Bei Fragen zum Service und zu den Anweisungen für den Einstieg verwenden Sie das Forum [IBM developerWorks® dW Answers ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://developer.ibm.com/answers/topics/dashdb/?smartspace=bluemix){:new_window}. Geben Sie die Tags "bluemix" und "dashdb" an.

Weitere Details zur Nutzung der Foren finden Sie unter [Hilfe anfordern](/docs/support/index.html#getting-help){:new_window}.

Informationen zum Öffnen eines IBM Support-Tickets oder zu den Supportebenen und den Prioritätsstufen von Tickets finden Sie unter [Support kontaktieren](/docs/support/index.html#contacting-support){:new_window}.




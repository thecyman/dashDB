---

copyright:
  years: 2014, 2017
lastupdated: "2017-05-16"

---

<!-- Attribute definitions --> 
{:javascript: #javascript .ph data-hd-programlang='javascript'}
{:java: #java .ph data-hd-programlang='java'}
{:ruby: #ruby .ph data-hd-programlang='ruby'}
{:php: #php .ph data-hd-programlang='php'}
{:python: #python .ph data-hd-programlang='python'}
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:pre: .pre}

#Einührung in dashDB
{: #dashDB}

Beim verwalteten {{site.data.keyword.IBM}} {{site.data.keyword.dashdbshort}}-Service handelt es sich um eine SQL-Datenbank, die für Sie in der Cloud bereitgestellt wird. Sie können {{site.data.keyword.dashdbshort_notm}} wie jede andere Datenbanksoftware verwenden, der Aufwand und die Kosten für die Hardwareeinrichtung sowie die Softwareinstallation und -verwaltung fallen jedoch weg.
{: shortdesc}

##Schnittstellen
{: #interfaces}

Für die Arbeit mit der {{site.data.keyword.dashdbshort_notm}}-Datenbank stehen Ihnen vier Möglichkeiten zur Verfügung:
{: shortdesc}

   * {{site.data.keyword.dashdbshort_notm}}-Webkonsole
   * REST-APIs
   * Herstellen einer Verbindung für Anwendungen oder bevorzugte Tools auf dem lokalen Computer
   * Verwenden von {{site.data.keyword.dashdbshort_notm}} als Datenquelle für Bluemix-Apps oder -Services

###dashDB-Webkonsole
{: #web_console}

Die Webkonsole bietet eine grafische Schnittstelle für alle Funktionen, die Sie für die Verwendung der Datenbank benötigen. Hierzu gehören z. B. Ladefunktionen, ein SQL-Editor, Treiberdownloads usw.
{: shortdesc}

![Ansicht der Dashboardseite der {{site.data.keyword.dashdbshort_notm}}-Webkonsole](images/console_v1.jpg)
<!-- ![View of {{site.data.keyword.dashdbshort_notm}} web console dashboard page](images/console_v2.jpg) -->

Klicken Sie für eine Tour durch die {{site.data.keyword.dashdbshort_notm}}-Webkonsole auf den Link [Allgemeine Tour ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](http://ibm.biz/dashdb-general-quick-tour){:new_window}.

Für den Zugriff auf die {{site.data.keyword.dashdbshort_notm}}-Webkonsole stehen Ihnen zwei Möglichkeiten zur Verfügung:
   * Über das {{site.data.keyword.Bluemix_notm}}-Dashboard - Sie können die Webkonsole über die Servicedetailseite für Ihren {{site.data.keyword.dashdbshort_notm}}-Service öffnen. 
   * Direkt über die URL - Sie können die URL der Webkonsole für Ihren {{site.data.keyword.dashdbshort_notm}}-Service mit einem Lesezeichen markieren. 

###REST-APIs
{: #apis}

Mit {{site.data.keyword.dashdbshort_notm}} for Analytics-Plänen können Sie Tasks im Zusammenhang mit dem Verwalten von Dateien, dem Laden von Daten und dem Ausführen von R-Scripts ausführen, indem Sie die [{{site.data.keyword.dashdbshort_notm}}-REST-API ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](http://ibm.biz/dashdb-api){:new_window} verwenden.
{: shortdesc}

###Herstellen einer Verbindung für Anwendungen oder bevorzugte Tools vom lokalen Computer
{: #connect_apps}

Führen Sie die folgenden Schritte aus, um die lokale Umgebung für die Verbindung zur {{site.data.keyword.dashdbshort_notm}}-Datenbank zu konfigurieren:
{: shortdesc}

1. Laden Sie das [{{site.data.keyword.dashdbshort_notm}}-Treiberpaket ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/connecting/connect_driver_package.html){:new_window} von der Downloadseite der {{site.data.keyword.dashdbshort_notm}}-Webkonsole herunter. 
2. [Installieren Sie das Treiberpaket ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/connecting/connect_driver_package_install.html){:new_window} auf dem Computer, auf dem Ihre Apps bzw. Tools ausgeführt werden. 
3. [Konfigurieren Sie die Treiberdateien ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://www.ibm.com/support/knowledgecenter/en/SS6NHC/com.ibm.swg.im.dashdb.doc/connecting/connect_driver_package_config.html){:new_window} für Ihre {{site.data.keyword.dashdbshort_notm}}-Datenbank. 

###Verwenden von dashDB als Datenquelle für Bluemix-Apps oder -Services
{: #data_src}

Für Apps, die per Hosting in {{site.data.keyword.Bluemix_notm}} bereitgestellt werden, können Verbindungen zu Ihrer {{site.data.keyword.dashdbshort_notm}}-Datenbank auf dieselbe Weise hergestellt werden wie bei Verbindungen für lokalen Anwendungen zu Ihrer {{site.data.keyword.dashdbshort_notm}}-Datenbank.
{: shortdesc}

Wenn Ihre Apps die {{site.data.keyword.Bluemix_notm}}-Plattform verwenden, können Sie die Umgebungsvariable `VCAP _SERVICES` nutzen, um das Angeben von Datenbankdetails und -berechtigungsnachweisen zu vereinfachen: 
1. Klicken Sie im {{site.data.keyword.Bluemix_notm}}-Dashboard auf der Registerkarte **Verbindungen** der Servicedetailseite für Ihren {{site.data.keyword.dashdbshort_notm}}-Service auf die Schaltfläche **Verbindung erstellen**.
2. Wählen Sie die {{site.data.keyword.Bluemix_notm}}-App aus, die mit der {{site.data.keyword.dashdbshort_notm}}-Datenbank als Datenquelle verwendet werden soll, und klicken Sie dann auf die Schaltfläche **Verbinden**.
3. Aktualisieren Sie den Anwendungscode, um Datenbankdetails- und -berechtigungsnachweise aus der Umgebungsvariablen `VCAP_SERVICES` abzurufen. 

    **Beispiel ohne `VCAP_SERVICES`**

    ```php
    <?php
    $driver      = "DRIVER={IBM DB2 ODBC DRIVER};";

    $database    = "BLUDB";         # Datenbankdetails von der
    $hostname    = "<Host-name>";   # Verbindungsseite der
    $port        = 50000;           # dashDB-Webkonsole abrufen.
    $user        = "<Benutzer-ID >";    #
    $password    = "<Kennwort>";    #
    $dsn         = "DATABASE=$database;" .
                   "HOSTNAME=$hostname;" .
                   "PORT=$port;" .
                   "PROTOCOL=TCPIP;" .
                   "UID=$user;" .
                   "PWD=$password;";

    $conn_string = $driver . $dsn;

    $conn        = db2_connect( $conn_string, "", "" );
    ?>
    ```

    **Beispiel mit `VCAP_SERVICES`**

    ```php
    <?php
    $driver      = "DRIVER={IBM DB2 ODBC DRIVER};";

    $vcap        = json_decode( getenv( "VCAP_SERVICES" ), true );
    $dsn         = $vcap[ "dashDB" ][0][ "credentials" ][ "dsn" ];

    $conn_string = $driver . $dsn;
                                   
    $conn        = db2_connect( $conn_string, "", "" );
    ?>
    ```

##Beispiele
{: #samples}

Über die folgenden Links können Sie Beispiele aufrufen, die veranschaulichen, wie Sie eine Verbindung von Anwendungen in verschiedenen Sprachen zu Ihrer {{site.data.keyword.dashdbshort_notm}}-Datenbank herstellen:
{: shortdesc}

   * [.NET ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/connecting/connect_connecting__net_applications.html){:new_window}
<!-- * [JAVA ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/connecting/connect_connecting_java.html){:new_window} -->
   * [JDBC ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/connecting/connect_connecting_jdbc_applications.html){:new_window}
<!-- * [Node.js ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/connecting/connect_connecting_nodejs.html){:new_window} -->
   * [PHP ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/connecting/connect_connecting_php.html){:new_window}
<!-- * [Python ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/connecting/connect_connecting_python.html){:new_window} -->
   * [dashDB-Beispiele in GitHub ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://github.com/IBM-Bluemix/dashdb-nodejs-helloworld){:new_window}



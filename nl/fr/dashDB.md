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

#Initiation à dashDB
{: #dashDB}

Le service géré {{site.data.keyword.IBM}} {{site.data.keyword.dashdbshort}} est une base de données SQL mise à votre disposition dans le cloud. Vous pouvez utiliser {{site.data.keyword.dashdbshort_notm}} de la même manière que vous utilisez n'importe quel logiciel de base de données, sans les frais associés à la configuration de matériel ou à l'installation et la maintenance de logiciels.
{: shortdesc}

##Interfaces
{: #interfaces}

Vous pouvez utiliser votre base de données {{site.data.keyword.dashdbshort_notm}} de quatre manières :
{: shortdesc}

   * Console Web {{site.data.keyword.dashdbshort_notm}}
   * API REST
   * Connectez des applications ou vos outils préférés depuis votre ordinateur local
   * Utilisez {{site.data.keyword.dashdbshort_notm}} comme source de données pour vos applications ou services Bluemix

###Console Web dashDB
{: #web_console}

La console web fournit une interface graphique pour tous les éléments dont vous avez besoin pour utiliser votre base de données : fonctions de chargement, éditeur SQL, téléchargements de pilotes, et plus encore.
{: shortdesc}

![Vue de la page de tableau de bord de la console Web {{site.data.keyword.dashdbshort_notm}}](images/console_v1.jpg)
<!-- ![View of {{site.data.keyword.dashdbshort_notm}} web console dashboard page](images/console_v2.jpg) -->

Cliquez sur ce lien pour effectuer une visite guidée de la console Web {{site.data.keyword.dashdbshort_notm}} : [Visite générale ![Icône de lien externe](../../icons/launch-glyph.svg "External link icon")](http://ibm.biz/dashdb-general-quick-tour){:new_window}.

Vous pouvez accéder à la console Web {{site.data.keyword.dashdbshort_notm}} de deux manières : 
   * A partir de votre tableau de bord {{site.data.keyword.Bluemix_notm}} : vous pouvez ouvrir la console Web depuis la page Détails du service de votre service {{site.data.keyword.dashdbshort_notm}}.
   * URL directe : vous pouvez ajouter un signet associé à l'URL de la console Web pour votre service {{site.data.keyword.dashdbshort_notm}}.

###API REST
{: #apis}

Grâce aux plans {{site.data.keyword.dashdbshort_notm}} for Analytics, vous pouvez effectuer des tâches liées à la gestion de fichiers, au chargement de données et à l'exécution de scripts R à l'aide de l'[API REST de {{site.data.keyword.dashdbshort_notm}} ![Icône de lien externe](../../icons/launch-glyph.svg "External link icon")](http://ibm.biz/dashdb-api){:new_window}.
{: shortdesc}

###Connectez des applications ou vos outils préférés depuis votre ordinateur local
{: #connect_apps}

Configurez votre environnement local afin qu'il se connecte à votre base de données {{site.data.keyword.dashdbshort_notm}} en procédant comme suit :
{: shortdesc}

1. Téléchargez le [package de pilote {{site.data.keyword.dashdbshort_notm}} ![Icône de lien externe](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/connecting/connect_driver_package.html){:new_window} à partir de la page Downloads de la console Web {{site.data.keyword.dashdbshort_notm}}.
2. [Installez le package de pilote ![Icône de lien externe](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/connecting/connect_driver_package_install.html){:new_window} sur l'ordinateur sur lequel vos applications ou vos outils sont exécutés. 
3. [Configurez les fichiers de pilote ![Icône de lien externe](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/support/knowledgecenter/en/SS6NHC/com.ibm.swg.im.dashdb.doc/connecting/connect_driver_package_config.html){:new_window} pour votre base de données {{site.data.keyword.dashdbshort_notm}}.

###Utilisez dashDB comme source de données pour vos applications ou services Bluemix
{: #data_src}

Les applications hébergées sur {{site.data.keyword.Bluemix_notm}} peuvent se connecter à votre base de données {{site.data.keyword.dashdbshort_notm}} exactement de la même manière que vos applications locales se connectent à votre base de données {{site.data.keyword.dashdbshort_notm}}.
{: shortdesc}

Lorsque vos applications utilisent la plateforme {{site.data.keyword.Bluemix_notm}}, vous pouvez tirer parti de la variable d'environnement `VCAP _SERVICES` pour simplifier la spécification des détails et des données d'identification de la base de données : 
1. Dans le tableau de bord {{site.data.keyword.Bluemix_notm}}, dans l'onglet **Connexions** de la page Détails du service de votre service {{site.data.keyword.dashdbshort_notm}}, cliquez sur le bouton **Créer une connexion**.
2. Sélectionnez l'application {{site.data.keyword.Bluemix_notm}} à utiliser avec votre base de données {{site.data.keyword.dashdbshort_notm}} comme source de données, puis cliquez sur le bouton **Connecter**. 
3. Mettez à jour le code de votre application pour qu'il extraie les détails et les données d'identification de la base de données à partir de la variable d'environnement `VCAP_SERVICES` :

    **Exemple sans 'VCAP_SERVICES'**

    ```php
    <?php
    $driver      = "DRIVER={IBM DB2 ODBC DRIVER};";

    $database    = "BLUDB";         # Obtenez ces infos sur la base de données
    $hostname    = "<Host-name>";   # à partir de la page Connect de
    $port        = 50000;           # la console Web dashDB.
    $user        = "<User-ID >";    #
    $password    = "<Password>";    #
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

    **Exemple avec 'VCAP_SERVICES'**

    ```php
    <?php
    $driver      = "DRIVER={IBM DB2 ODBC DRIVER};";

    $vcap        = json_decode( getenv( "VCAP_SERVICES" ), true );
    $dsn         = $vcap[ "dashDB" ][0][ "credentials" ][ "dsn" ];

    $conn_string = $driver . $dsn;

    $conn        = db2_connect( $conn_string, "", "" );
    ?>
    ```

##Exemples
{: #samples}

Les liens suivants mènent à des exemples de démonstration indiquant comment se connecter à votre base de données {{site.data.keyword.dashdbshort_notm}} à partir d'applications dans différents langages :
{: shortdesc}

   * [.NET ![Icône de lien externe](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/connecting/connect_connecting__net_applications.html){:new_window}
<!-- * [JAVA ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/connecting/connect_connecting_java.html){:new_window} -->
   * [JDBC ![Icône de lien externe](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/connecting/connect_connecting_jdbc_applications.html){:new_window}
<!-- * [Node.js ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/connecting/connect_connecting_nodejs.html){:new_window} -->
   * [PHP ![Icône de lien externe](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/connecting/connect_connecting_php.html){:new_window}
<!-- * [Python ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/connecting/connect_connecting_python.html){:new_window} -->
   * [Exemples dashDB sur GitHub ![Icône de lien externe](../../icons/launch-glyph.svg "External link icon")](https://github.com/IBM-Bluemix/dashdb-nodejs-helloworld){:new_window}



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

#A propos de dashDB
{: #dashDB_overview}

Deux solutions de base de données différentes sont fournies par {{site.data.keyword.IBM}} {{site.data.keyword.dashdbshort}} : une solution de création d'entrepôts de données et d'analyse (plans {{site.data.keyword.dashdbshort_notm}} for Analytics) et une solution de traitement des transactions en ligne (pour les plans {{site.data.keyword.dashdbshort_notm}} for Transactions).
{: shortdesc}

##Service géré dashDB
{: #managed_service}

Le service entièrement géré de {{site.data.keyword.dashdbshort_notm}} est en charge de toutes les mises à
niveau logicielles et mises à jour du système d'exploitation, ainsi que de la maintenance du matériel. Il surveille la santé de la base de données et de l'infrastructure, 24 heures sur 24, 7 jours sur 7. En cas de défaillance matérielle ou logicielle, il est redémarré automatiquement.
{: shortdesc}

Pour plus d'informations sur les aspects de service géré de {{site.data.keyword.dashdbshort_notm}}, voir : [{{site.data.keyword.dashdbshort_notm}} managed service ![Icône de lien externe](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/managed_service.html).

##Plans et configurations
{: #plans_cfgs}

Vous pouvez choisir un plan {{site.data.keyword.dashdbshort_notm}} configuré et optimisé pour le travail que vous devez effectuer :
{: shortdesc}

   * Un plan payant à l'essai
   * Des plans de tailles différentes (petit, moyen, important) pour la production
   * Des configurations de traitement à parallélisme massif pour le traitement parallèle
   * Des plans configurés pour la haute disponibilité ou pour la compatibilité avec Oracle
   * Et plus encore...

Vous pouvez afficher les plans disponibles dans le catalogue {{site.data.keyword.Bluemix}} : 
   * Plans configurés pour les charges de travail liées aux entrepôts de données et à l'analyse (OLAP) : [{{site.data.keyword.dashdbshort_notm}} for Analytics](https://console.ng.bluemix.net/catalog/services/dashdb-for-analytics){:new_window}
   * Plans configurés pour le traitement transactionnel à vitesse élevée (OLTP) : [{{site.data.keyword.dashdbshort_notm}} for Transactions](https://console.ng.bluemix.net/catalog/services/dashdb-for-transactions-sql-database){:new_window}

Si, dans le catalogue, vous ne trouvez pas la configuration dont vous avez besoin, [contactez votre équipe commerciale {{site.data.keyword.IBM_notm}} ![Icône de lien externe](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/connect/ibm/us/en/?lnk=fcw){:new_window} pour rechercher d'autres options.

##dashDB for Analytics
{: #dashDB_an}

Dans les plans d'entreposage des données de {{site.data.keyword.dashdbshort_notm}} for Analytics, utilisez l'entrepôt de données {{site.data.keyword.dashdbshort_notm}} pour stocker les données relationnelles, y compris les types spéciaux tels que les données géospatiales. Vous analysez vos propres données ou des données chargées depuis d'autres services de cloud à l'aide des analyses
intégrées ou en connectant vos propres applications. Vous pouvez optimiser la technologie de base de données en mémoire hautes performances à l'aide de tables à colonnes pour les charges de travail analytiques. La console Web de {{site.data.keyword.dashdbshort_notm}} gère les tâches de
gestion des données courantes, telles que le chargement de données, ainsi que les tâches d'analyse, telles que l'exécution de requêtes et de scripts R.
{: shortdesc}

Vous pouvez aussi connecter des outils et des applications externes à {{site.data.keyword.dashdbshort_notm}}
et les utiliser pour gérer ou analyser vos données. Exemple :
   * Connectez {{site.data.keyword.IBM_notm}} InfoSphere® Data Architect pour concevoir et déployer votre schéma de base de données.
   * Connectez Esri ArcGIS pour effectuer une analyse géospatiale et la publication de carte avec vos données.
   * Connectez un serveur {{site.data.keyword.IBM_notm}} Cognos® afin de générer des rapports Cognos pour vos données.
   * Connectez des outils s'appuyant sur SQL tels que Tableau, Microstrategy ou Microsoft Excel pour manipuler ou analyser vos données.
   * Connectez vos applications {{site.data.keyword.Bluemix_short}} qui nécessitent une base de données analytique.
   * Connectez Aginity Workbench pour migrer des données et des modèles de données Netezza® vers {{site.data.keyword.dashdbshort_notm}}.

##Mise à disposition de dashDB for Analytics
{: #whse_provision}

L'entrepôt de données {{site.data.keyword.IBM_notm}} {{site.data.keyword.dashdbshort_notm}} for Analytics peut être mis à disposition sur {{site.data.keyword.BluSoftlayer_full}} et pour AWS.
{: shortdesc}

Si vous souhaitez mettre à disposition l'entrepôt de données {{site.data.keyword.dashdbshort_notm}} for Analytics pour AWS, sélectionnez le plan **{{site.data.keyword.IBM_notm}} {{site.data.keyword.dashdbshort_notm}} for Analytics MPP Small for AWS**.

##dashDB for Transactions
{: #dashDB_tr}

Dans les plans
{{site.data.keyword.dashdbshort_notm}} for Transactions, utilisez la base de données relationnelle
{{site.data.keyword.dashdbshort_notm}} pour le traitement des transactions en ligne. Vous pouvez connecter des applications nouvelles ou existantes et commencer à traiter les transactions et à stocker vos données. Grâce à la compatibilité avec DB2® et Oracle, vous pouvez connecter de petites ou grandes applications et bénéficier d'un système de base de données géré pour entreprise. Vous pouvez optimiser la
console Web de
{{site.data.keyword.dashdbshort_notm}} for Transactions pour gérer les utilisateurs, charger des données et obtenir les
informations de connexion.
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















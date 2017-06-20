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

#Traitement des incidents liés à dashDB 
{: #tr_dashDB}

Voici des réponses aux questions fréquentes concernant l'utilisation de
{{site.data.keyword.dashdbshort}} dans {{site.data.keyword.Bluemix_short}}.
{: shortdesc}

##Impossible de se connecter à RStudio
{: #r_studio}

La connexion unique pour RStudio n'est pas disponible pour {{site.data.keyword.dashdblong}}.
{: shortdesc}

Vous voulez vous connecter à RStudio depuis {{site.data.keyword.dashdbshort_notm}} en utilisant la connexion unique mais vous êtes invité à entrer un mot de passe.
{: tsSymptoms}

La connexion unique pour RStudio n'est pas disponible dans {{site.data.keyword.dashdbshort_notm}}.
{: tsCauses}

Afin d'obtenir vos données d'identification pour RStudio, consultez votre variable d'environnement `VCAP_SERVICES`. Des informations supplémentaires sont disponibles dans [Initiation à {{site.data.keyword.dashdbshort_notm}}](/docs/services/dashDB/dashDB.html#dashDB){:new_window}.
{: tsResolve}


##Fichier `diag.log` introuvable pour le traitement des incidents
{: #diag_log}

Le fichier `diag.log` n'est pas disponible.
{: shortdesc}

Vous souhaitez traiter les incidents mais vous ne trouvez pas le fichier `diag.log` pour {{site.data.keyword.dashdbshort_notm}}.
{: tsSymptoms}

Le `diag.log` n'est pas disponible dans {{site.data.keyword.dashdbshort_notm}}, ni aucun autre journal propre à DB2.
{: tsCauses}

Les journaux propres à l'application sont accessibles via l'interface de
ligne de commande Cloud Foundry. Depuis l'interface de ligne de commande, entrez **cf
logs --recent**. Vous pouvez également accéder aux journaux sur le site
{{site.data.keyword.Bluemix_notm}} en sélectionnant votre application, puis en accédant à **Fichiers et
journaux**.
{: tsResolve}

##Organisation ou espace introuvable : non-concordance d'ID Bluemix
{: #org_space_id}

Une organisation ou un espace est introuvable pour une nouvelle instance
{{site.data.keyword.dashdbshort_notm}}.
{: shortdesc}

Vous voulez créer une instance de service {{site.data.keyword.dashdbshort_notm}} dans {{site.data.keyword.Bluemix_notm}} à l'aide de la fonction d'entreposage du tableau de bord Cloudant®, mais vous obtenez le message d'erreur suivant : `Cannot find org or space.`
{: tsSymptoms}

Pour mettre à disposition une nouvelle instance de service {{site.data.keyword.dashdbshort_notm}} dans {{site.data.keyword.Bluemix_notm}}, la fonction d'entreposage Cloudant tente d'identifier l'organisation cible {{site.data.keyword.Bluemix_notm}} la plus adaptée pour l'utilisateur {{site.data.keyword.Bluemix_notm}} authentifié. En général, la fonction d'entreposage recherche une organisation
qui correspond à l'ID {{site.data.keyword.Bluemix_notm}}, qui lui-même est souvent l'adresse électronique de
l'utilisateur. Si aucune organisation correspondante n'est trouvée et si l'utilisateur n'a accès qu'à une seule organisation, la fonction d'entreposage sélectionne cette organisation. Dans certains cas, l'utilisateur ne peut accéder à aucune organisation, ou a accès à plusieurs organisations. Cloudant ne peut alors pas déterminer l'emplacement de mise à disposition de l'instance {{site.data.keyword.dashdbshort_notm}} et le message d'erreur s'affiche.
{: tsCauses}

Pour résoudre le problème, choisissez l'une des options suivantes :
{: tsResolve}

* Dans la liste déroulante du tableau de bord Cloudant, sélectionnez l'organisation {{site.data.keyword.Bluemix_notm}} dans laquelle créer l'instance {{site.data.keyword.dashdbshort_notm}}. Une fois l'organisation sélectionnée, choisissez l'espace approprié dans la deuxième liste déroulante.
* Mettez manuellement à disposition une instance {{site.data.keyword.dashdbshort_notm}} directement dans {{site.data.keyword.Bluemix_notm}} et sélectionnez l'instance de service {{site.data.keyword.dashdbshort_notm}} créée dans la liste déroulante du tableau de bord Cloudant.


##Organisation ou espace introuvable : non-concordance des régions
{: #org_space_region}

Une organisation ou un espace est introuvable pour une nouvelle instance {{site.data.keyword.dashdbshort_notm}}.
{: shortdesc}

Vous voulez créer une instance de service {{site.data.keyword.dashdbshort_notm}} mais les listes déroulantes des instances de service {{site.data.keyword.dashdbshort_notm}} ou des organisations {{site.data.keyword.Bluemix_notm}} existantes sont vides. Il n'est pas possible de mettre à disposition une nouvelle instance de service {{site.data.keyword.dashdbshort_notm}} et le message d'erreur suivant s'affiche : `Cannot find org or space.`
{: tsSymptoms}

Si le compte {{site.data.keyword.Bluemix_notm}} de l'utilisateur se trouve dans une région différente de celle du cluster Cloudant, la demande de mise à disposition échoue. Par exemple, le compte {{site.data.keyword.Bluemix_notm}} a été intégré dans la région Europe et Royaume-Uni alors que le cluster Cloudant utilise la région Sud des Etats-Unis. Par conséquent, les listes déroulantes d'instances de service et d'organisations existantes dans le tableau de bord Cloudant peuvent être vides ou afficher des organisations et des espaces qui appartiennent à une autre région.
{: tsCauses}

1. Connectez-vous au tableau de bord {{site.data.keyword.Bluemix_notm}} et accédez à votre région. Suivez les invites pour procéder à l'intégration dans cette région. Vous pouvez aussi créer un compte {{site.data.keyword.Bluemix_notm}} dans la région appropriée.
2. Connectez-vous au tableau de bord Cloudant pour sélectionner également l'instance de service {{site.data.keyword.dashdbshort_notm}}.
{: tsResolve}

##Dépassement des limites pour les services
{: #service_limit}

Le service {{site.data.keyword.dashdbshort_notm}} dans
{{site.data.keyword.Bluemix_notm}} a dépassé sa limite.
{: shortdesc}

Alors que vous utilisez le service {{site.data.keyword.dashdbshort_notm}} dans {{site.data.keyword.Bluemix_notm}}, le message d'erreur suivant s'affiche : `Exceeded your organization’s services limit.`
{: tsSymptoms}

Vous utilisez l'essai
gratuit de {{site.data.keyword.Bluemix_notm}}, qui impose des limites pour les services.
{: tsCauses}

Pour résoudre le problème, choisissez l'une des options suivantes :
{: tsResolve}

* Pour libérer des ressources, supprimez les services que vous n'utilisez plus dans votre tableau de bord
{{site.data.keyword.Bluemix_notm}}. Soumettez à nouveau la demande de mise à disposition pour une nouvelle
instance {{site.data.keyword.dashdbshort_notm}}.
* Utilisez le tableau de bord {{site.data.keyword.Bluemix_notm}} pour mettre manuellement à disposition une
instance {{site.data.keyword.dashdbshort_notm}} dans une organisation ou un espace approprié qui ne présente pas de
limites pour les services. Sélectionnez cette instance depuis le tableau de bord Cloudant.


##Service dashDB non disponible
{: #outages}

Il se peut que le service {{site.data.keyword.dashdbshort_notm}} ne soit pas disponible dans
{{site.data.keyword.Bluemix_notm}}.
{: shortdesc}

Une tentative de création d'un entrepôt de données échoue avec une erreur
500 ou un chargement SDP signale une erreur SQL.
{: tsSymptoms}

Le service
{{site.data.keyword.dashdbshort_notm}} dans
{{site.data.keyword.Bluemix_notm}} fait l'objet d'une procédure de maintenance planifiée ou une indisponibilité
prévue est survenue.
{: tsCauses}

Vous pouvez déterminer le statut du service
{{site.data.keyword.dashdbshort_notm}} dans
{{site.data.keyword.Bluemix_notm}} en consultant les pages de statut suivantes :
{: tsResolve}

* [Support {{site.data.keyword.Bluemix_notm}} ![Icône de lien externe](../../icons/launch-glyph.svg "External link icon")](https://developer.ibm.com/bluemix/support/#status){:new_window}
* Surveillance du statut :
  * [Toutes les régions ![Icône de lien externe](../../icons/launch-glyph.svg "External link icon")](https://console.eu-gb.bluemix.net/status?tags=platform,runtimes,services,ibm:yp:eu-gb,ibm:yp:eu-de,ibm:yp:us-south,ibm:yp:au-syd){:new_window}
  <!--[US - South region ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://estado.ng.bluemix.net/internalstatus){:new_window}
  [Europe - United Kingdom region ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://estado.eu-gb.bluemix.net/internalstatus){:new_window}
  [Europe - Germany region ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://estado.eu-de.bluemix.net/internalstatus){:new_window}
  [Australia - Sydney region ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://estado.au-syd.bluemix.net/internalstatus){:new_window}-->


##Aide et assistance pour dashDB
{: #gettinghelp}

Si vous rencontrez des problèmes ou des questions lors de l'utilisation de
{{site.data.keyword.dashdbshort_notm}}, vous pouvez rechercher des informations ou poser des questions via un
forum. Vous pouvez également ouvrir un ticket de demande de service.
{: shortdesc}

Si vous utilisez les forums pour poser une question, libellez votre question de sorte à être vue par les équipes de développement {{site.data.keyword.Bluemix}}.

* En cas de questions techniques liées au développement ou au déploiement d'une application avec {{site.data.keyword.dashdbshort_notm}}, postez votre question sur le forum [Stack Overflow ![Icône de lien externe](../../icons/launch-glyph.svg "External link icon")](http://stackoverflow.com/search?q=dashdb+bluemix){:new_window} en lui ajoutant les étiquettes "bluemix" et "dashdb".
* Pour les questions liées au service et à la mise en route, utilisez le forum [IBM developerWorks® dW Answers ![Icône de lien externe](../../icons/launch-glyph.svg "External link icon")](https://developer.ibm.com/answers/topics/dashdb/?smartspace=bluemix){:new_window}. Indiquez les étiquettes "bluemix" et "dashdb".

Pour plus d'informations sur l'utilisation des forums, voir
[Comment obtenir de l'aide](/docs/support/index.html#getting-help){:new_window}.

Pour plus d'informations sur l'ouverture d'un ticket de demande de service IBM, ou sur les niveaux de support et les gravités de tickets, voir [Contacter le service de support](/docs/support/index.html#contacting-support){:new_window}.




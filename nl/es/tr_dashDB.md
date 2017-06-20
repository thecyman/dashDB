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

#Resolución de problemas de dashDB 
{: #tr_dashDB}

Aquí se encuentran las respuestas a diversas preguntas comunes sobre el uso de {{site.data.keyword.dashdbshort}} en {{site.data.keyword.Bluemix_short}}.
{: shortdesc}

##No es posible iniciar sesión en RStudio
{: #r_studio}

El inicio de sesión único (SSO) para RStudio no está disponible para {{site.data.keyword.dashdblong}}.
{: shortdesc}

Desea iniciar sesión en RStudio a partir de {{site.data.keyword.dashdbshort_notm}} utilizando
SSO, pero se le solicita una contraseña.
{: tsSymptoms}

SSO para RStudio no está disponible en {{site.data.keyword.dashdbshort_notm}}.
{: tsCauses}

Para obtener las credenciales para RStudio, consulte la variable de entorno `VCAP_SERVICES`. Hay más información disponible en [Iniciación a {{site.data.keyword.dashdbshort_notm}}](/docs/services/dashDB/dashDB.html#dashDB){:new_window}.
{: tsResolve}


##No se puede encontrar el archivo `diag.log` para la resolución de problemas
{: #diag_log}

El archivo `diag.log` no está disponible.
{: shortdesc}

Desea resolver problemas y no puede encontrar el archivo `diag.log` para {{site.data.keyword.dashdbshort_notm}}.
{: tsSymptoms}

El archivo `diag.log` no está disponible en {{site.data.keyword.dashdbshort_notm}}, ni ningún otro registro específico de DB2.
{: tsCauses}

Puede acceder a los registros específicos de la aplicación mediante la interfaz de línea de mandatos (CLI) de Cloud
Foundry. Desde la CLI, escriba **cf
logs --recent**. Para acceder a los registros en el sitio de {{site.data.keyword.Bluemix_notm}}, seleccione la app y vaya a **Archivos y registros**.
{: tsResolve}

##No se puede encontrar la organización o el espacio: discrepancia de ID de Bluemix
{: #org_space_id}

No se puede encontrar una organización o un espacio para una nueva instancia de {{site.data.keyword.dashdbshort_notm}}.
{: shortdesc}

Desea crear una nueva instancia de servicio de {{site.data.keyword.dashdbshort_notm}} en {{site.data.keyword.Bluemix_notm}} utilizando la característica de almacenamiento en el panel de control de Cloudant, pero obtiene el siguiente mensaje de error: `No se puede encontrar la organización o el espacio.`
{: tsSymptoms}

Para suministrar una nueva instancia de servicio de {{site.data.keyword.dashdbshort_notm}} en {{site.data.keyword.Bluemix_notm}}, a característica de almacenamiento Cloudant intentará encontrar la organización de destino {{site.data.keyword.Bluemix_notm}} que encaje mejor para el usuario autenticado de {{site.data.keyword.Bluemix_notm}}. La característica de almacenamiento normalmente busca una organización que coincide
con el ID de {{site.data.keyword.Bluemix_notm}},
que es normalmente la cuenta de correo electrónico del usuario. Si no se ha encontrado una organización coincidente
y el usuario tiene acceso a sólo una organización,
la característica de almacenamiento seleccionará dicha organización. Puede que haya situaciones
en las que el usuario no tenga una organización a la que pueda
acceder o que el usuario tenga acceso a varias organizaciones. En dichas situaciones, Cloudant no podrá determinar dónde suministrar la instancia de {{site.data.keyword.dashdbshort_notm}}
y se mostrará el mensaje de error.
{: tsCauses}

Para resolver el problema, seleccione una de las siguientes
opciones:
{: tsResolve}

* Desde la lista desplegable del panel de control Cloudant,
seleccione la organización de {{site.data.keyword.Bluemix_notm}} en la que desea que se cree la instancia de {{site.data.keyword.dashdbshort_notm}}. Una vez que seleccione la organización, seleccione el espacio adecuado
desde la lista desplegable secundaria.
* Suministre manualmente una instancia de {{site.data.keyword.dashdbshort_notm}} directamente en {{site.data.keyword.Bluemix_notm}} y seleccione la instancia de servicio creada de {{site.data.keyword.dashdbshort_notm}} desde la lista desplegable del panel de control de Cloudant.


##No se puede encontrar la organización o el espacio: discrepancia de regiones
{: #org_space_region}

No se puede encontrar una organización o un espacio para una nueva instancia de {{site.data.keyword.dashdbshort_notm}}.
{: shortdesc}

Desea crear una nueva instancia de servicio de {{site.data.keyword.dashdbshort_notm}},
pero las listas desplegables de instancias de servicio de {{site.data.keyword.dashdbshort_notm}} existentes
o las organizaciones de {{site.data.keyword.Bluemix_notm}}
están vacías. No se puede suministrar una nueva instancia de servicio de {{site.data.keyword.dashdbshort_notm}} y obtendrá el siguiente mensaje de error: `No se puede encontrar la organización o el espacio.`
{: tsSymptoms}

Si la cuenta de {{site.data.keyword.Bluemix_notm}} del usuario
se encuentra en una región distinta que el clúster de Cloudant, fallará la solicitud de suministro. Por ejemplo, la cuenta de {{site.data.keyword.Bluemix_notm}} se incorporó en la región Reino Unido, Europa, pero el clúster de Cloudant funciona con la región de
EE.UU. sur. Como resultado, la instancia de servicio existente y las listas desplegables de la organización del panel de control de Cloudant pueden estar vacías o mostrar organizaciones y espacios que pertenecen a una región distinta.
{: tsCauses}

1. Inicie sesión en el panel de control de {{site.data.keyword.Bluemix_notm}}
y conmute a la región esperada. Siga las indicaciones para completar
la incorporación en dicha región. Como alternativa, cree una cuenta de {{site.data.keyword.Bluemix_notm}} en la región adecuada.
2. Inicie sesión en el panel de control de Cloudant
para repetir la selección de la instancia de servicio de {{site.data.keyword.dashdbshort_notm}}.
{: tsResolve}

##Límite de servicios superado
{: #service_limit}

El servicio de {{site.data.keyword.dashdbshort_notm}}
en {{site.data.keyword.Bluemix_notm}} ha superado
su límite.
{: shortdesc}

Mientras esté utilizando el servicio de {{site.data.keyword.dashdbshort_notm}}
en {{site.data.keyword.Bluemix_notm}}, se mostrará el siguiente mensaje de error: `Se ha superado el límite de servicios de su
organización.`
{: tsSymptoms}

Aún está utilizando la prueba de {{site.data.keyword.Bluemix_notm}} sin coste,
que tiene límites de servicio.
{: tsCauses}

Para resolver el problema, seleccione una de las siguientes
opciones:
{: tsResolve}

* Para liberar recursos, arrastre servicios en el panel de control de {{site.data.keyword.Bluemix_notm}} que ya no desee utilizar. Vuelva a intentar la solicitud de suministro para una instancia nueva de {{site.data.keyword.dashdbshort_notm}}.
* Utilice el panel de control de {{site.data.keyword.Bluemix_notm}}
para suministrar de forma manual una instancia de {{site.data.keyword.dashdbshort_notm}}
a una organización o espacio adecuados que no tenga límites de servicio. Seleccione dicha instancia desde el panel de control de Cloudant.


##El servicio dashDB no está disponible
{: #outages}

Puede que no esté disponible el servicio de {{site.data.keyword.dashdbshort_notm}}
en {{site.data.keyword.Bluemix_notm}}.
{: shortdesc}

Ha fallado un intento por crear un almacén de datos con un error 500,
o una carga de SDP informa de un error de SQL.
{: tsSymptoms}

Al servicio de {{site.data.keyword.dashdbshort_notm}}
en {{site.data.keyword.Bluemix_notm}} se le está realizando
un procedimiento de mantenimiento planificado o se ha producido una caída conocida.
{: tsCauses}

Puede determinar el estado del servicio de {{site.data.keyword.dashdbshort_notm}}
en {{site.data.keyword.Bluemix_notm}} comprobando
las siguientes páginas de estado:
{: tsResolve}

* Soporte de [{{site.data.keyword.Bluemix_notm}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://developer.ibm.com/bluemix/support/#status){:new_window}
* Supervisión de estado:
  * Todas las regiones de [![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://console.eu-gb.bluemix.net/status?tags=platform,runtimes,services,ibm:yp:eu-gb,ibm:yp:eu-de,ibm:yp:us-south,ibm:yp:au-syd){:new_window}
  <!--[US - South region ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://estado.ng.bluemix.net/internalstatus){:new_window}
  [Europe - United Kingdom region ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://estado.eu-gb.bluemix.net/internalstatus){:new_window}
  [Europe - Germany region ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://estado.eu-de.bluemix.net/internalstatus){:new_window}
  [Australia - Sydney region ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://estado.au-syd.bluemix.net/internalstatus){:new_window}-->


##Obtención de ayuda y soporte para dashDB
{: #gettinghelp}

Si tiene problemas o preguntas sobre el uso de {{site.data.keyword.dashdbshort_notm}}, puede obtener ayuda buscando información o formulando preguntas en un foro. También puede abrir una incidencia de soporte.
{: shortdesc}

Al utilizar los foros para formular una pregunta, etiquete la pregunta de forma que la puedan ver los equipos de desarrollo de {{site.data.keyword.Bluemix}}.

* Si tiene preguntas técnicas sobre el desarrollo o el despliegue de una app con {{site.data.keyword.dashdbshort_notm}}, publíquelas en [Stack Overflow ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](http://stackoverflow.com/search?q=dashdb+bluemix){:new_window} y etiquételas con "bluemix" y "dashdb".
* Para formular preguntas sobre el servicio y obtener instrucciones de iniciación, utilice el foro de [IBM developerWorks® dW Answers ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://developer.ibm.com/answers/topics/dashdb/?smartspace=bluemix){:new_window}. Incluya las etiquetas "bluemix" y "dashdb".

Consulte [Obtención de ayuda](/docs/support/index.html#getting-help){:new_window} para obtener más detalles sobre el uso de los foros.

Para obtener información sobre cómo abrir una incidencia de soporte de IBM, o sobre los niveles de soporte y la gravedad de las incidencias, consulte: [Cómo obtener soporte](/docs/support/index.html#contacting-support){:new_window}.




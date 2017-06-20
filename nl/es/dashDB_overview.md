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

#Acerca de dashDB
{: #dashDB_overview}

Existen dos soluciones de bases de datos distintas que proporciona {{site.data.keyword.IBM}} {{site.data.keyword.dashdbshort}}: una solución de depósito de datos y análisis (planes {{site.data.keyword.dashdbshort_notm}} for Analytics), y una solución de procesamiento de transacciones en línea (planes {{site.data.keyword.dashdbshort_notm}} for Transactions).
{: shortdesc}

##servicio gestionado dashDB
{: #managed_service}

El servicio completamente gestionado de {{site.data.keyword.dashdbshort_notm}} maneja todas las actualizaciones de software, actualizaciones de sistema operativo y mantenimiento de hardware. El servicio incluye supervisión de estado de tipo 24x7 de la base de datos y de la infraestructura. En el caso de que se produzca un error de hardware o de software, el servicio se reinicia automáticamente.
{: shortdesc}

Para obtener más información sobre los aspectos del servicio gestionado de {{site.data.keyword.dashdbshort_notm}}, consulte: servicio gestionado de [{{site.data.keyword.dashdbshort_notm}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/managed_service.html).

##Planes y configuraciones
{: #plans_cfgs}

Puede elegir un plan {{site.data.keyword.dashdbshort_notm}} que está configurado y optimizado para el trabajo que necesita realizar:
{: shortdesc}

   * Un plan de entrada para realizar pruebas
   * Planes pequeños, medianos y grandes para producción
   * Configuraciones MPP para procesamientos paralelos
   * Planes configurados para Alta disponibilidad o para compatibilidad con Oracle
   * Y más...

Vea los planes disponibles en el catálogo {{site.data.keyword.Bluemix}}:
   * Planes configurados para almacenes de datos y cargas de trabajo analíticas (OLAP): [{{site.data.keyword.dashdbshort_notm}} para Analytics](https://console.ng.bluemix.net/catalog/services/dashdb-for-analytics){:new_window}
   * Planes configurados para procesamientos transaccionales de alta velocidad (OLTP): [{{site.data.keyword.dashdbshort_notm}} para transacciones](https://console.ng.bluemix.net/catalog/services/dashdb-for-transactions-sql-database){:new_window}

Si no ve una configuración en el catálogo que necesita, [póngase en contacto con ventas {{site.data.keyword.IBM_notm}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/connect/ibm/us/en/?lnk=fcw){:new_window} para debatir otras opciones.

##dashDB for Analytics
{: #dashDB_an}

En los planes de almacén de datos de análisis de {{site.data.keyword.dashdbshort_notm}}, utilice el almacén de datos {{site.data.keyword.dashdbshort_notm}} para guardar datos relacionales, incluidos tipos especiales como datos geoespaciales. Analice sus propios datos, o los datos cargados desde otros servicios de nube, utilizando las herramientas de análisis incluidas o conectando sus propias apps. Puede aprovecharse del alto rendimiento, tecnología de base de datos en memoria con tablas con columnas para cargas de trabajo de análisis. La consola web de {{site.data.keyword.dashdbshort_notm}} puede trabajar con tareas de gestión de datos comunes, como cargar datos, y con tareas de análisis, como ejecutar consultas y scripts R.
{: shortdesc}

También puede conectar aplicaciones externas a {{site.data.keyword.dashdbshort_notm}} y utilizarlas para gestionar o analizar todavía más sus datos. Por ejemplo:
   * Conecte {{site.data.keyword.IBM_notm}} InfoSphere Data Architect para diseñar y desplegar su esquema de base de datos.
   * Conecte Esri ArcGIS para realizar análisis geoespaciales y publicar mapas con sus datos.
   * Conecte un servidor {{site.data.keyword.IBM_notm}} Cognos para ejecutar informes de Cognos de sus datos.
   * Conecte herramientas basadas en SQL, como Tableau, Microstrategy o Microsoft Excel para manipular o analizar sus datos.
   * Conecte sus aplicaciones {{site.data.keyword.Bluemix_short}} que necesitan una base de datos de análisis.
   * Conecte Aginity Workbench para migrar modelos de datos y datos de Netezza a {{site.data.keyword.dashdbshort_notm}}.

##Suministro de dashDB for Analytics
{: #whse_provision}

El almacén de datos de {{site.data.keyword.IBM_notm}} {{site.data.keyword.dashdbshort_notm}} for Analytics puede suministrarse en {{site.data.keyword.BluSoftlayer_full}} y para AWS.
{: shortdesc}

Si desea que se suministre el almacén de datos de {{site.data.keyword.dashdbshort_notm}} for Analytics,
seleccione el plan **{{site.data.keyword.IBM_notm}} {{site.data.keyword.dashdbshort_notm}}for Analytics MPP
Small for AWS**.

##dashDB for Transactions
{: #dashDB_tr}

En el plan {{site.data.keyword.dashdbshort_notm}} for Transactions, utilice la base de datos relacional
de {{site.data.keyword.dashdbshort_notm}} para el proceso de transacciones en línea. No puede conectar aplicaciones nuevas o existentes y puede empezar a procesar transacciones y a guardar sus datos. Con la compatibilidad con DB2 y Oracle, puede conectar aplicaciones pequeñas grandes y aprovechar el sistema de bases de datos gestionadas a nivel de toda la organización. Puede aprovechar la consola web de {{site.data.keyword.dashdbshort_notm}} for Transactions para gestionar usuarios, cargar datos y obtener información sobre la conexión.
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















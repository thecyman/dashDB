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

#Iniciación a dashDB
{: #dashDB}

El servicio gestionado de {{site.data.keyword.IBM}} {{site.data.keyword.dashdbshort}} es una base de datos SQL suministrada para usted en el cloud. Puede utilizar {{site.data.keyword.dashdbshort_notm}} como utilizaría cualquier software de base de datos, pero sin la sobrecarga ni el gasto de la configuración de hardware o la instalación y el mantenimiento de software. 
{: shortdesc}

##Interfaces
{: #interfaces}

Puede trabajar con la base de datos de {{site.data.keyword.dashdbshort_notm}} de cuatro modos:
{: shortdesc}

   * Consola web de {{site.data.keyword.dashdbshort_notm}}
   * API REST
   * Conecte aplicaciones o herramientas preferidas desde el sistema local
   * Utilice {{site.data.keyword.dashdbshort_notm}} como origen de datos para apps o servicios de Bluemix

###Consola web de dashDB
{: #web_console}

La consola web proporciona una interfaz gráfica para todo lo que puede utilizar su base de datos, incluyendo: recursos de cargas, un editor SQL, descargas de controladores, etc.
{: shortdesc}

![Vea la página del panel de control de la consola web de {{site.data.keyword.dashdbshort_notm}}](images/console_v1.jpg)
<!-- ![View of {{site.data.keyword.dashdbshort_notm}} web console dashboard page](images/console_v2.jpg) -->

Pulse el enlace para realizar una visita guiada de la consola web de {{site.data.keyword.dashdbshort_notm}}: Visita guiada general de [![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](http://ibm.biz/dashdb-general-quick-tour){:new_window}.

Puede acceder a la consola web de {{site.data.keyword.dashdbshort_notm}} de dos modos:
   * Desde el panel de control de {{site.data.keyword.Bluemix_notm}} - Puede abrir la consola web desde la página Detalles de servicio para el servicio de {{site.data.keyword.dashdbshort_notm}}.
   * URL directo - Puede marcar como favorito el URL de la consola web para el servicio de {{site.data.keyword.dashdbshort_notm}}.

###API REST
{: #apis}

Con los panes de {{site.data.keyword.dashdbshort_notm}} for Analytics, puede realizar tareas relacionadas con la gestión de archivos, carga de datos y ejecución de scripts R utilizando la API REST de [{{site.data.keyword.dashdbshort_notm}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](http://ibm.biz/dashdb-api){:new_window}.
{: shortdesc}

###Conecte aplicaciones o herramientas preferidas desde el sistema local
{: #connect_apps}

Configure el entorno local para conectar la base de datos de {{site.data.keyword.dashdbshort_notm}} siguiendo estos pasos:
{: shortdesc}

1. Descargue el paquete de controladores de [{{site.data.keyword.dashdbshort_notm}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/connecting/connect_driver_package.html){:new_window} de la página Descargas de la consola web de {{site.data.keyword.dashdbshort_notm}}.
2. [Instale el paquete de controladores de ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/connecting/connect_driver_package_install.html){:new_window} en el sistema donde esté ejecutando las apps o las herramientas.
3. [Configure los archivos de controladores ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/support/knowledgecenter/en/SS6NHC/com.ibm.swg.im.dashdb.doc/connecting/connect_driver_package_config.html){:new_window} para la base de datos de {{site.data.keyword.dashdbshort_notm}}.

###Utilice dashDB como origen de datos para apps o servicios de Bluemix
{: #data_src}

Las apps alojadas en {{site.data.keyword.Bluemix_notm}} pueden conectarse a la base de datos de {{site.data.keyword.dashdbshort_notm}} exactamente del mismo modo que pueden conectarse las aplicaciones locales a la base de datos de {{site.data.keyword.dashdbshort_notm}}.
{: shortdesc}

Cuando las apps utilizan la plataforma de {{site.data.keyword.Bluemix_notm}}, puede sacar partido de la variable de entorno `VCAP _SERVICES` para simplificar la tarea de especificar detalles y credenciales de bases de datos:
1. En el panel de control de {{site.data.keyword.Bluemix_notm}}, en el separador **Conexiones** de la página Detalles del servicio para el servicio de {{site.data.keyword.dashdbshort_notm}}, pulse el botón **Crear conexión**.
2. Seleccione la app de {{site.data.keyword.Bluemix_notm}} para utilizarla con la base de datos de {{site.data.keyword.dashdbshort_notm}} como origen de datos y luego pulse el botón **Conectar**.
3. Actualice el código de aplicación para recuperar detalles y credenciales de la base de datos desde la variable de entorno `VCAP_SERVICES`:

    **Ejemplo sin `VCAP_SERVICES`**

    ```php
    <?php
    $driver      = "DRIVER={IBM DB2 ODBC DRIVER};";

    $database    = "BLUDB";         # Obtenga los detalles de la base de datos desde
    $hostname    = "<Host-name>";   # la página Conectar de dashDB
    $port        = 50000;           # consola web.
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

    **Ejemplo con `VCAP_SERVICES`**

    ```php
    <?php
    $driver      = "DRIVER={IBM DB2 ODBC DRIVER};";

    $vcap        = json_decode( getenv( "VCAP_SERVICES" ), true );
    $dsn         = $vcap[ "dashDB" ][0][ "credentials" ][ "dsn" ];

    $conn_string = $driver . $dsn;
                                   
    $conn        = db2_connect( $conn_string, "", "" );
    ?>
    ```

##Ejemplos
{: #samples}

Aquí tiene los enlaces a ejemplos que demuestran cómo conectarse a la base de datos de {{site.data.keyword.dashdbshort_notm}} desde aplicaciones en distintos idiomas:
{: shortdesc}

   * [.NET ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/connecting/connect_connecting__net_applications.html){:new_window}
<!-- * [JAVA ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/connecting/connect_connecting_java.html){:new_window} -->
   * [JDBC ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/connecting/connect_connecting_jdbc_applications.html){:new_window}
<!-- * [Node.js ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/connecting/connect_connecting_nodejs.html){:new_window} -->
   * [PHP ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/connecting/connect_connecting_php.html){:new_window}
<!-- * [Python ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/connecting/connect_connecting_python.html){:new_window} -->
   * Ejemplos de [dashDB en GitHub ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://github.com/IBM-Bluemix/dashdb-nodejs-helloworld){:new_window}



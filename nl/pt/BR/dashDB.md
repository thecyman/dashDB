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

#Introdução ao dashDB
{: #dashDB}

O serviço gerenciado do {{site.data.keyword.IBM}} {{site.data.keyword.dashdbshort}} é um banco de dados SQL provisionado para você na nuvem. É possível usar o {{site.data.keyword.dashdbshort_notm}} da mesma forma que usaria qualquer software de banco de dados, mas sem o gasto adicional e a despesa de configuração de hardware e instalação e manutenção de software.
{: shortdesc}

##Interfaces
{: #interfaces}

É possível trabalhar com seu banco de dados do {{site.data.keyword.dashdbshort_notm}} de quatro maneiras:
{: shortdesc}

   * Console da Web do {{site.data.keyword.dashdbshort_notm}}
   * APIs REST
   * Conecte aplicativos ou suas ferramentas favoritas por meio do seu computador local
   * Use o {{site.data.keyword.dashdbshort_notm}} como uma origem de dados para seus apps ou serviços Bluemix

###Console da web do dashDB
{: #web_console}

O console da web fornece uma interface gráfica para tudo o que precisar para usar seu banco de dados, incluindo: instalações de carga, um editor de SQL, downloads de driver e mais.
{: shortdesc}

![Visualização da página do painel do console da web do {{site.data.keyword.dashdbshort_notm}}](images/console_v1.jpg)
<!-- ![View of {{site.data.keyword.dashdbshort_notm}} web console dashboard page](images/console_v2.jpg) -->

Clique no link para fazer um tour do console da web do {{site.data.keyword.dashdbshort_notm}}: [Tour geral ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](http://ibm.biz/dashdb-general-quick-tour){:new_window}.

É possível acessar seu console da web do {{site.data.keyword.dashdbshort_notm}} de duas maneiras:
   * No painel do {{site.data.keyword.Bluemix_notm}}: é possível abrir o console da web por meio da página Detalhes do serviço para seu serviço do {{site.data.keyword.dashdbshort_notm}}.
   * URL direta: é possível marcar como favorita a URL do console da web para seu serviço do {{site.data.keyword.dashdbshort_notm}}.

###APIs REST
{: #apis}

Com planos {{site.data.keyword.dashdbshort_notm}} for Analytics, é possível executar tarefas relacionadas ao gerenciamento de arquivos, carregar dados e executar scripts R usando a API de REST do [{{site.data.keyword.dashdbshort_notm}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](http://ibm.biz/dashdb-api){:new_window}.
{: shortdesc}

###Conecte aplicativos ou suas ferramentas favoritas por meio do seu computador local
{: #connect_apps}

Configure seu ambiente local para se conectar ao seu banco de dados do {{site.data.keyword.dashdbshort_notm}} concluindo as etapas a seguir:
{: shortdesc}

1. Faça download do [Pacote de drivers do {{site.data.keyword.dashdbshort_notm}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/connecting/connect_driver_package.html){:new_window} na página Downloads do console da web do {{site.data.keyword.dashdbshort_notm}}.
2. [Instale o pacote de drivers ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/connecting/connect_driver_package_install.html){:new_window} no computador em que seus apps ou ferramentas estão em execução.
3. [Configure os arquivos de drivers ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://www.ibm.com/support/knowledgecenter/en/SS6NHC/com.ibm.swg.im.dashdb.doc/connecting/connect_driver_package_config.html){:new_window} para seu banco de dados do {{site.data.keyword.dashdbshort_notm}}.

###Use o dashDB como uma origem de dados para seus apps ou serviços do Bluemix
{: #data_src}

Apps hospedados no {{site.data.keyword.Bluemix_notm}} podem se conectar ao seu banco de dados do {{site.data.keyword.dashdbshort_notm}} exatamente da mesma forma que seus aplicativos locais se conectam ao seu banco de dados do {{site.data.keyword.dashdbshort_notm}}.
{: shortdesc}

Quando seus apps usam a plataforma {{site.data.keyword.Bluemix_notm}}, é possível aproveitar a variável de ambiente `VCAP _SERVICES` para simplificar a tarefa de especificar detalhes e credenciais do banco de dados:
1. Em seu painel do {{site.data.keyword.Bluemix_notm}}, na guia **Conexões** da página Detalhes do serviço para seu serviço do {{site.data.keyword.dashdbshort_notm}}, clique no botão **Criar conexão**.
2. Selecione o app do {{site.data.keyword.Bluemix_notm}} para usar com seu banco de dados do {{site.data.keyword.dashdbshort_notm}} como uma origem de dados e, em seguida, clique no botão **Conectar**.
3. Atualize seu código do aplicativo para recuperar detalhes e credenciais do banco de dados por meio da variável de ambiente `VCAP_SERVICES`:

    **Exemplo sem `VCAP_SERVICES`**

    ```php
    <?php
    $driver      = "DRIVER={IBM DB2 ODBC DRIVER};";

    $database    = "BLUDB";         # Obtenha esses detalhes do banco de dados na
    $hostname    = "<Host-name>";   # página Conectar do console da web
    $port        = 50000;           # dashDB.
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

    **Exemplo com `VCAP_SERVICES`**

    ```php
    <?php
    $driver      = "DRIVER={IBM DB2 ODBC DRIVER};";

    $vcap        = json_decode( getenv( "VCAP_SERVICES" ), true );
    $dsn         = $vcap[ "dashDB" ][0][ "credentials" ][ "dsn" ];

    $conn_string = $driver . $dsn;

    $conn        = db2_connect( $conn_string, "", "" );
    ?>
    ```

##Amostra
{: #samples}

Aqui estão links para amostras que demonstram como se conectar a seu banco de dados do {{site.data.keyword.dashdbshort_notm}} por meio de aplicativos em diferentes idiomas:
{: shortdesc}

   * [.NET ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/connecting/connect_connecting__net_applications.html){:new_window}
<!-- * [JAVA ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/connecting/connect_connecting_java.html){:new_window} -->
   * [JDBC ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/connecting/connect_connecting_jdbc_applications.html){:new_window}
<!-- * [Node.js ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/connecting/connect_connecting_nodejs.html){:new_window} -->
   * [PHP ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/connecting/connect_connecting_php.html){:new_window}
<!-- * [Python ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/connecting/connect_connecting_python.html){:new_window} -->
   * [Amostras do dashDB no GitHub![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://github.com/IBM-Bluemix/dashdb-nodejs-helloworld){:new_window}



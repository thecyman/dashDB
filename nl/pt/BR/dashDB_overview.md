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

#Sobre o dashDB
{: #dashDB_overview}

Há duas soluções de banco de dados diferentes fornecidas pelo {{site.data.keyword.IBM}} {{site.data.keyword.dashdbshort}}: uma solução de data warehousing e de analítica (planos {{site.data.keyword.dashdbshort_notm}} for Analytics) e uma solução de processamento de transações on-line (planos {{site.data.keyword.dashdbshort_notm}} for Transactions).
{: shortdesc}

##serviço gerenciado
dashDB
{: #managed_service}

O serviço totalmente gerenciado do {{site.data.keyword.dashdbshort_notm}} manipula de todos os upgrades de software, atualizações de sistema operacional e manutenção de hardware. O serviço inclui monitoramento de funcionamento 24x7 do banco de dados e da infraestrutura. No caso de falha de hardware ou software, o serviço é reiniciado automaticamente.
{: shortdesc}

Para obter mais informações sobre os aspectos de serviço gerenciado do {{site.data.keyword.dashdbshort_notm}}, consulte: [Serviço gerenciado do {{site.data.keyword.dashdbshort_notm}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/managed_service.html).

##Planos e configurações
{: #plans_cfgs}

É possível escolher um plano {{site.data.keyword.dashdbshort_notm}} que esteja configurado e otimizado para o trabalho que você precise fazer:
{: shortdesc}

   * Um plano de entrada para teste
   * Planos pequeno, médio e grande para produção
   * Configurações de MPP para processamento paralelo
   * Planos configurados para Alta disponibilidade ou para compatibilidade de Oracle
   * E muito mais...

Visualize planos disponíveis no catálogo do {{site.data.keyword.Bluemix}}:
   * Planos configurados para cargas de trabalho de data warehouse e analítica (OLAP): [{{site.data.keyword.dashdbshort_notm}} for Analytics](https://console.ng.bluemix.net/catalog/services/dashdb-for-analytics){:new_window}
   * Planos configurados para processamento transacional de alta velocidade (OLTP): [{{site.data.keyword.dashdbshort_notm}} for Transactions](https://console.ng.bluemix.net/catalog/services/dashdb-for-transactions-sql-database){:new_window}

Se você não vir no catálogo uma configuração da qual precise, [entre em contato com o departamento de vendas do {{site.data.keyword.IBM_notm}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://www.ibm.com/connect/ibm/us/en/?lnk=fcw){:new_window} para discutir sobre outras opções.

##dashDB for Analytics
{: #dashDB_an}

Nos planos de data warehouse do {{site.data.keyword.dashdbshort_notm}} for Analytics, use o data warehouse do {{site.data.keyword.dashdbshort_notm}} para armazenar dados relacionais, incluindo tipos especiais, como dados geoespaciais. Analise seus próprios dados ou os dados carregados de outros serviços de nuvem, usando nossa analítica integrada
ou ao conectar seus próprios aplicativos. É possível alavancar a tecnologia de banco de dados na
memória de alto desempenho com tabelas com colunas para cargas de trabalho analíticas. O console da web do {{site.data.keyword.dashdbshort_notm}} manipula
tarefas de gerenciamento de dados comuns, como carregamento de dados e tarefas de análise, como execução de consultas e
scripts R.
{: shortdesc}

Também
é possível conectar ferramentas e aplicativos externos ao {{site.data.keyword.dashdbshort_notm}} e
utilizá-los para gerenciar ou analisar ainda mais os dados. Por exemplo:
   * Conecte o {{site.data.keyword.IBM_notm}} InfoSphere® Data Architect para projetar e implementar seu esquema do banco de dados.
   * Conecte o Esri ArcGIS para executar análise geoespacial e mapear a publicação
com seus dados.
   * Conecte um servidor {{site.data.keyword.IBM_notm}} Cognos® para executar relatórios do Cognos em relação aos seus dados.
   * Conecte ferramentas baseadas em SQL, como Tableau, Microstrategy ou Microsoft Excel, para manipular ou analisar seus dados.
   * Conecte seus aplicativos {{site.data.keyword.Bluemix_short}} que precisam de um banco de dados de análise.
   * Conecte o Aginity Workbench para migrar dados e modelos de dados do Netezza® para o {{site.data.keyword.dashdbshort_notm}}.

##Fornecimento de dashDB for Analytics
{: #whse_provision}

O data warehouse do {{site.data.keyword.IBM_notm}} {{site.data.keyword.dashdbshort_notm}} for Analytics pode ser provisionado no {{site.data.keyword.BluSoftlayer_full}} e para AWS.
{: shortdesc}

Se desejar que o data warehouse do {{site.data.keyword.dashdbshort_notm}} for Analytics seja provisionado para AWS, selecione o plano **{{site.data.keyword.IBM_notm}} {{site.data.keyword.dashdbshort_notm}} for Analytics MPP Small for AWS**.

##dashDB for Transactions
{: #dashDB_tr}

Nos
planos do {{site.data.keyword.dashdbshort_notm}} for Transactions, use o banco de dados relacional do {{site.data.keyword.dashdbshort_notm}} para o processamento de transações on-line. É possível conectar aplicativos novos ou existentes e começar a processar transações e a armazenar dados. Com a compatibilidade com DB2® e Oracle, é possível conectar aplicativos pequenos ou grandes e se beneficiar de um sistema de banco de dados de classe corporativa gerenciado. É possível alavancar o console da web do {{site.data.keyword.dashdbshort_notm}} for Transactions para gerenciar usuários, carregar dados e obter informações de conexão.
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















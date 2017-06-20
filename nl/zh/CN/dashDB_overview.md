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

#关于 dashDB
{: #dashDB_overview}

{{site.data.keyword.IBM}} {{site.data.keyword.dashdbshort}} 提供了两种不同的数据库解决方案：数据仓储和分析解决方案（{{site.data.keyword.dashdbshort_notm}} for Analytics 计划）和联机事务处理解决方案（{{site.data.keyword.dashdbshort_notm}} for Transactions 计划）。
{: shortdesc}

##dashDB 受管服务
{: #managed_service}

{{site.data.keyword.dashdbshort_notm}} 的全面受管服务会处理所有软件升级、操作系统更新和硬件维护。该服务全天不间断监视数据库和基础架构的运行状况。当硬件或软件发生故障时，该服务将自动重新启动。
{: shortdesc}

有关 {{site.data.keyword.dashdbshort_notm}} 的受管服务方面的更多信息，请参阅：[{{site.data.keyword.dashdbshort_notm}} 受管服务 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/managed_service.html)。

##计划和配置
{: #plans_cfgs}

您可以选择针对您需要执行的工作所配置和优化的 {{site.data.keyword.dashdbshort_notm}} 计划：
{: shortdesc}

   * 入门级计划，进行尝试
   * 用于生产的小型、中型和大型计划
   * 用于并行处理的 MPP 配置
   * 为高可用性或 Oracle 兼容性配置的计划
   * 其他更多...

在 {{site.data.keyword.Bluemix}} 目录中查看可用的计划：
   * 为数据仓库和分析 (OLAP) 工作负载配置的计划：[{{site.data.keyword.dashdbshort_notm}} for Analytics](https://console.ng.bluemix.net/catalog/services/dashdb-for-analytics){:new_window}
   * 为高速事务处理 (OLTP) 配置的计划：[{{site.data.keyword.dashdbshort_notm}} for Transactions](https://console.ng.bluemix.net/catalog/services/dashdb-for-transactions-sql-database){:new_window}

如果您在目录中看不到所需的配置，请[联系 {{site.data.keyword.IBM_notm}} 销售人员 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/connect/ibm/us/en/?lnk=fcw){:new_window}，以讨论其他选择。

##dashDB for Analytics
{: #dashDB_an}

在 {{site.data.keyword.dashdbshort_notm}} for Analytics 数据仓库计划中，使用 {{site.data.keyword.dashdbshort_notm}} 数据仓库来存储关系数据，包括地理空间数据等特殊类型。通过使用我们的内置分析或通过连接您自己的应用程序，分析自己的数据或从其他云服务装入的数据。您可以在列式表中利用高性能内存中数据库技术进行分析工作负载。{{site.data.keyword.dashdbshort_notm}} Web 控制台处理常见数据管理任务（如装入数据）和分析任务（如运行查询和 R 脚本）。
{: shortdesc}

您还可以将外部应用程序和工具连接到 {{site.data.keyword.dashdbshort_notm}}，以使用其进一步管理或分析数据。例如：
   * 连接 {{site.data.keyword.IBM_notm}} InfoSphere® Data Architect，以设计和部署数据库模式。
   * 连接 Esri ArcGIS，以使用您的数据执行地理空间分析和地图发布。
   * 连接 {{site.data.keyword.IBM_notm}} Cognos® 服务器，以对数据运行 Cognos 报告。
   * 连接基于 SQL 的工具（如 Tableau、Microstrategy 或 Microsoft Excel），以控制或分析数据。
   * 连接需要分析数据库的 {{site.data.keyword.Bluemix_short}} 应用程序。
   * 连接 Aginity Workbench，以将 Netezza® 数据模型和数据迁移到 {{site.data.keyword.dashdbshort_notm}}。

##供应 dashDB for Analytics
{: #whse_provision}

{{site.data.keyword.IBM_notm}} {{site.data.keyword.dashdbshort_notm}} for Analytics 数据仓库可在 {{site.data.keyword.BluSoftlayer_full}} 上和针对 AWS 进行供应。
{: shortdesc}

如果希望对 AWS 供应 {{site.data.keyword.dashdbshort_notm}} for Analytics 数据仓库，请选择 **{{site.data.keyword.IBM_notm}} {{site.data.keyword.dashdbshort_notm}} for Analytics MPP Small for AWS** 计划。

##dashDB for Transactions
{: #dashDB_tr}

在 {{site.data.keyword.dashdbshort_notm}} for Transactions 计划中，使用 {{site.data.keyword.dashdbshort_notm}} 关系数据库来进行联机事务处理。您可以连接新的或现有的应用程序，然后即可开始处理事务并存储数据。通过 DB2® 和 Oracle 兼容性，您可以连接小型或大型应用程序，并从受管企业级数据库系统受益。您可以利用 {{site.data.keyword.dashdbshort_notm}} for Transactions Web 控制台来管理用户、装入数据以及获取连接信息。
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















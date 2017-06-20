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

#dashDB 故障诊断 
{: #tr_dashDB}

下面是在 {{site.data.keyword.Bluemix_short}} 中使用 {{site.data.keyword.dashdbshort}} 时遇到的几个常见问题的解决方法。
{: shortdesc}

##无法登录到 RStudio
{: #r_studio}

用于 RStudio 的单点登录 (SSO) 不可用于 {{site.data.keyword.dashdblong}}。
{: shortdesc}

您要使用 SSO 从 {{site.data.keyword.dashdbshort_notm}} 登录到 RStudio，但系统提示您输入密码。
{: tsSymptoms}

用于 RStudio 的 SSO 在 {{site.data.keyword.dashdbshort_notm}} 中不可用。
{: tsCauses}

要获取 RStudio 的凭证，请查阅 `VCAP_SERVICES` 环境变量。更多信息可在 [{{site.data.keyword.dashdbshort_notm}} 入门](/docs/services/dashDB/dashDB.html#dashDB){:new_window} 中找到。
{: tsResolve}


##找不到用于故障诊断的 `diag.log` 文件
{: #diag_log}

`diag.log` 文件不可用。
{: shortdesc}

您希望进行故障诊断，但找不到 {{site.data.keyword.dashdbshort_notm}} 的 `diag.log` 文件。
{: tsSymptoms}

{{site.data.keyword.dashdbshort_notm}} 上没有 `diag.log` 文件，也没有其他任何特定于 DB2® 的日志。
{: tsCauses}

可通过 Cloud Foundry CLI（命令行界面）访问特定于应用程序的日志。从 CLI 输入 **cf logs --recent**。您还可以在 {{site.data.keyword.Bluemix_notm}} 站点上通过选择应用程序，然后转至**文件和日志**来访问这些日志。
{: tsResolve}

##找不到组织或空间：Bluemix 标识不匹配
{: #org_space_id}

找不到新 {{site.data.keyword.dashdbshort_notm}} 实例的组织或空间。
{: shortdesc}

您要在 {{site.data.keyword.Bluemix_notm}} 中，使用 Cloudant® 仪表板中的仓储功能来创建新的 {{site.data.keyword.dashdbshort_notm}} 服务实例，但收到以下错误消息：`找不到组织或空间。`
{: tsSymptoms}

要在 {{site.data.keyword.Bluemix_notm}} 中供应新的 {{site.data.keyword.dashdbshort_notm}} 服务实例，Cloudant 仓储功能会尝试为已认证的 {{site.data.keyword.Bluemix_notm}} 用户查找“最佳匹配”的 {{site.data.keyword.Bluemix_notm}} 目标组织。通常，仓储功能会查找与 {{site.data.keyword.Bluemix_notm}} 标识匹配的组织，该标识通常是用户的电子邮件地址。如果找不到匹配的组织，并且用户只有权访问一个组织，那么仓储功能会选择该组织。可能存在用户无权访问任何组织或者用户有权访问多个组织的情况。在这些情况下，Cloudant 无法确定供应 {{site.data.keyword.dashdbshort_notm}} 实例的位置，因此会显示错误消息。
{: tsCauses}

要解决此问题，请选择以下某个选项：
{: tsResolve}

* 从 Cloudant 仪表板的下拉列表中，选择要在其中创建 {{site.data.keyword.dashdbshort_notm}} 实例的 {{site.data.keyword.Bluemix_notm}} 组织。选择组织后，请从第二个下拉列表中选择相应的空间。
* 在 {{site.data.keyword.Bluemix_notm}} 中直接手动供应 {{site.data.keyword.dashdbshort_notm}} 实例，然后从 Cloudant 仪表板的下拉列表中选择创建的 {{site.data.keyword.dashdbshort_notm}} 服务实例。


##找不到组织或空间：区域不匹配
{: #org_space_region}

找不到新 {{site.data.keyword.dashdbshort_notm}} 实例的组织或空间。
{: shortdesc}

您要创建新的 {{site.data.keyword.dashdbshort_notm}} 服务实例，但是现有 {{site.data.keyword.dashdbshort_notm}} 服务实例或 {{site.data.keyword.Bluemix_notm}} 组织的下拉列表为空。无法供应新 {{site.data.keyword.dashdbshort_notm}} 服务实例，并且将收到以下错误消息：`找不到组织或空间。`
{: tsSymptoms}

如果用户的 {{site.data.keyword.Bluemix_notm}} 帐户所在的区域与 Cloudant 集群所在的区域不同，那么供应请求会失败。例如，{{site.data.keyword.Bluemix_notm}} 帐户是在欧洲英国区域上线的，而 Cloudant 集群使用的是美国南部区域。那么，Cloudant 仪表板中的现有服务实例和组织下拉列表可能为空，或者一并显示属于其他区域的组织和空间。
{: tsCauses}

1. 登录到 {{site.data.keyword.Bluemix_notm}} 仪表板，并切换到所需区域。遵循所有提示以完成在该区域上线。或者，也可以在相应的区域中创建 {{site.data.keyword.Bluemix_notm}} 帐户。
2. 登录到 Cloudant 仪表板以重复 {{site.data.keyword.dashdbshort_notm}} 服务实例选择。
{: tsResolve}

##超过服务限制
{: #service_limit}

{{site.data.keyword.Bluemix_notm}} 中的 {{site.data.keyword.dashdbshort_notm}} 服务超过其限制。
{: shortdesc}

在 {{site.data.keyword.Bluemix_notm}} 中使用 {{site.data.keyword.dashdbshort_notm}} 服务时，显示以下错误消息：`已超过您组织的服务限制。`
{: tsSymptoms}

您使用的仍是 {{site.data.keyword.Bluemix_notm}} 免费试用版，此版本是有服务限制的。
{: tsCauses}

要解决此问题，请选择以下某个选项：
{: tsResolve}

* 要释放资源，请删除 {{site.data.keyword.Bluemix_notm}} 仪表板中不再使用的服务。重试对新 {{site.data.keyword.dashdbshort_notm}} 实例的供应请求。
* 使用 {{site.data.keyword.Bluemix_notm}} 仪表板在没有服务限制的相应组织或空间中手动供应 {{site.data.keyword.dashdbshort_notm}} 实例。从 Cloudant 仪表板中选择该实例。


##dashDB 服务不可用
{: #outages}

{{site.data.keyword.Bluemix_notm}} 中的 {{site.data.keyword.dashdbshort_notm}} 服务可能不可用。
{: shortdesc}

尝试创建数据仓库失败并返回错误 500，或者 SDP 装入报告 SQL 错误。
{: tsSymptoms}

{{site.data.keyword.Bluemix_notm}} 中的 {{site.data.keyword.dashdbshort_notm}} 服务正在执行安排的维护过程，或者发生了已知的中断。
{: tsCauses}

您可以通过检查以下状态页面，确定 {{site.data.keyword.Bluemix_notm}} 中 {{site.data.keyword.dashdbshort_notm}} 服务的状态：
{: tsResolve}

* [{{site.data.keyword.Bluemix_notm}} 支持 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://developer.ibm.com/bluemix/support/#status){:new_window}
* 状态监视：
  * [所有区域 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://console.eu-gb.bluemix.net/status?tags=platform,runtimes,services,ibm:yp:eu-gb,ibm:yp:eu-de,ibm:yp:us-south,ibm:yp:au-syd){:new_window}
  <!--[US - South region ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://estado.ng.bluemix.net/internalstatus){:new_window}
  [Europe - United Kingdom region ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://estado.eu-gb.bluemix.net/internalstatus){:new_window}
  [Europe - Germany region ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://estado.eu-de.bluemix.net/internalstatus){:new_window}
  [Australia - Sydney region ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://estado.au-syd.bluemix.net/internalstatus){:new_window}-->


##获取有关 dashDB 的帮助和支持
{: #gettinghelp}

如果您在使用 {{site.data.keyword.dashdbshort_notm}} 时有任何疑问或遇到任何问题，您可以在论坛中搜索相关信息或进行提问来获取帮助。还可以提交支持凭单。
{: shortdesc}

使用论坛进行提问时，请使用适当的标记来标注您的问题，以方便 {{site.data.keyword.Bluemix}} 开发团队识别。

* 有关使用 {{site.data.keyword.dashdbshort_notm}} 开发或部署应用程序的技术问题，请将您的问题发布到 [Stack Overflow ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](http://stackoverflow.com/search?q=dashdb+bluemix){:new_window} 上，并使用“bluemix”和“dashdb”标记您的问题。
* 有关服务的问题和入门指示信息，请使用 [IBM developerWorks® dW Answers ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://developer.ibm.com/answers/topics/dashdb/?smartspace=bluemix){:new_window} 论坛。请包括“bluemix”和“dashdb”标记。

有关使用论坛的更多详细信息，请参阅[获取帮助](/docs/support/index.html#getting-help){:new_window}。

有关开具 IBM 支持凭单或支持级别和凭单严重性的信息，请参阅：[联系支持人员](/docs/support/index.html#contacting-support){:new_window}。




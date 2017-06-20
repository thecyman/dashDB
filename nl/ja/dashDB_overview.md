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

#dashDB について
{: #dashDB_overview}

{{site.data.keyword.IBM}} {{site.data.keyword.dashdbshort}} は 2 つのデータベース・ソリューションを提供します。1 つは、データウェアハウジングおよび分析ソリューション ({{site.data.keyword.dashdbshort_notm}} for Analytics プラン) であり、もう 1 つは、オンライン・トランザクション処理ソリューション ({{site.data.keyword.dashdbshort_notm}} for Transactions プラン) です。
{: shortdesc}

##dashDB マネージド・サービス
{: #managed_service}

{{site.data.keyword.dashdbshort_notm}} の完全マネージド・サービスは、すべてのソフトウェア・アップグレード、オペレーティング・システム更新、およびハードウェア保守を処理します。
このサービスには、データベースおよびインフラストラクチャーの 24 時間 365 日ヘルス・モニターが含まれています。
ハードウェアまたはソフトウェアの障害が発生した場合は、このサービスが自動的に再始動されます。
{: shortdesc}

{{site.data.keyword.dashdbshort_notm}} のマネージド・サービスの特徴について詳しくは、[{{site.data.keyword.dashdbshort_notm}} マネージド・サービス ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/managed_service.html) を参照してください。

##プランおよび構成
{: #plans_cfgs}

お客様の用途に合わせて構成および最適化されている {{site.data.keyword.dashdbshort_notm}} プランを選択できます。
{: shortdesc}

   * 試行用のエントリー・プラン
   * 実動用の小規模プラン、中規模プラン、および大規模プラン
   * 並列処理用の MPP 構成
   * 高可用性のために構成されたプラン、または、Oracle 互換性のために構成されたプラン
   * その他 ...

{{site.data.keyword.Bluemix}} カタログで、使用可能なプランを確認してください。
   * データウェアハウスおよび分析 (OLAP) ワークロード用に構成されたプラン: [{{site.data.keyword.dashdbshort_notm}} for Analytics](https://console.ng.bluemix.net/catalog/services/dashdb-for-analytics){:new_window}
   * 高速トランザクション処理 (OLTP) 用に構成されたプラン: [{{site.data.keyword.dashdbshort_notm}} for Transactions](https://console.ng.bluemix.net/catalog/services/dashdb-for-transactions-sql-database){:new_window}

必要な構成がカタログにない場合は、[{{site.data.keyword.IBM_notm}} 営業担当員に連絡 ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://www.ibm.com/connect/ibm/us/en/?lnk=fcw){:new_window} して、他のオプションについて相談してください。

##dashDB for Analytics
{: #dashDB_an}

{{site.data.keyword.dashdbshort_notm}} for Analytics データウェアハウスのプランでは、{{site.data.keyword.dashdbshort_notm}} データウェアハウスを使用して、地理情報データなどの特殊なタイプを含むリレーショナル・データを保管します。組み込み分析を使用するか、お客様独自のアプリケーションを接続して、お客様独自のデータまたは他のクラウド・サービスからロードしたデータを分析します。分析ワークロードに対して、縦欄の表で高性能のメモリー内データベース・テクノロジーを活用できます。{{site.data.keyword.dashdbshort_notm}} Web コンソールは、
共通データ管理タスク (データのロードなど) および分析タスク (照会や R スクリプトの実行など) を処理します。
{: shortdesc}

また、外部アプリケーションやツールを {{site.data.keyword.dashdbshort_notm}} に接続して利用し、
データをさらに管理または分析することも可能です。
例えば、以下を行えます。
   * {{site.data.keyword.IBM_notm}} InfoSphere® Data Architect を接続して、データベース・スキーマを設計およびデプロイします。
   * Esri ArcGIS を接続して、ご使用のデータで地理情報分析やマップ・パブリッシュを実行します。
   * {{site.data.keyword.IBM_notm}} Cognos® サーバーを接続して、データに対して Cognos レポートを実行します。
   * SQL ベースのツール (Tableau、Microstrategy、Microsoft Excel など) を接続して、データを操作または分析します。
   * 分析データベースを必要とする {{site.data.keyword.Bluemix_short}} アプリケーションを接続します。

   * Aginity Workbench を接続して、Netezza® データ・モデルおよびデータを {{site.data.keyword.dashdbshort_notm}} にマイグレーションします。

##dashDB for Analytics のプロビジョニング
{: #whse_provision}

{{site.data.keyword.IBM_notm}} {{site.data.keyword.dashdbshort_notm}} for Analytics データウェアハウスを {{site.data.keyword.BluSoftlayer_full}} 上で AWS 用にプロビジョンできます。
{: shortdesc}

{{site.data.keyword.dashdbshort_notm}} for Analytics データウェアハウスを AWS 用にプロビジョンしたい場合は、**{{site.data.keyword.IBM_notm}} {{site.data.keyword.dashdbshort_notm}} for Analytics MPP Small for AWS** プランを選択してください。

##dashDB for Transactions
{: #dashDB_tr}

{{site.data.keyword.dashdbshort_notm}} for Transactions プランでは、オンライン・トランザクション処理に {{site.data.keyword.dashdbshort_notm}} リレーショナル・データベースを使用します。新しいアプリケーションや既存のアプリケーションを接続し、トランザクションの処理とデータの保管を開始することができます。
DB2® と Oracle は互換性があるため、小規模または大規模なアプリケーションを接続し、管理対象エンタープライズ・クラス・データベース・システムの利点を活用できます。{{site.data.keyword.dashdbshort_notm}} for Transactions Web コンソールを活用して、ユーザーの管理、データのロード、および接続情報の取得を行うことができます。
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















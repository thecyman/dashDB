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

#dashDB 정보
{: #dashDB_overview}

{{site.data.keyword.IBM}} {{site.data.keyword.dashdbshort}}에서 제공하는 두 개의 서로 다른 데이터베이스 솔루션이 있습니다. 이 두 솔루션은 데이터 웨어하우징 및 분석 솔루션({{site.data.keyword.dashdbshort_notm}} for Analytics 플랜)과 온라인 트랜잭션 처리 솔루션({{site.data.keyword.dashdbshort_notm}} for Transactions 플랜)입니다.
{: shortdesc}

##dashDB 관리 서비스
{: #managed_service}

{{site.data.keyword.dashdbshort_notm}}의 완전한 관리 서비스는 소프트웨어 업그레이드, 운영 체제 업데이트 및 하드웨어 유지보수 모두를 처리합니다. 서비스에는 데이터베이스 및 인프라의 24x7 상태 모니터링이 포함됩니다. 하드웨어 또는 소프트웨어 장애가 발생하는 경우 서비스는 자동으로 다시 시작됩니다.
{: shortdesc}

{{site.data.keyword.dashdbshort_notm}}의 관리 서비스 측면에 대한 자세한 정보는 [{{site.data.keyword.dashdbshort_notm}} 관리 서비스(![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘"))](https://www.ibm.com/support/knowledgecenter/SS6NHC/com.ibm.swg.im.dashdb.doc/managed_service.html)를 참조하십시오.

##플랜 및 구성
{: #plans_cfgs}

수행해야 하는 작업에 맞게 구성되고 최적화된 {{site.data.keyword.dashdbshort_notm}} 플랜을 선택할 수 있습니다.
{: shortdesc}

   * 테스트를 위한 입력 플랜
   * 프로덕션을 위한 소규모, 중간 규모, 대규모 플랜
   * 병렬 처리를 위한 MPP 구성
   * 고가용성 또는 Oracle 호환성을 위해 구성된 플랜
   * 기타...

{{site.data.keyword.Bluemix}} 카탈로그에서 사용 가능한 플랜 보기:
   * 데이터 웨어하우스 및 분석(OLAP) 워크로드에 맞게 구성된 플랜: [{{site.data.keyword.dashdbshort_notm}} for Analytics ](https://console.ng.bluemix.net/catalog/services/dashdb-for-analytics){:new_window}
   * 고속 트랜잭션 처리(OLTP)에 맞게 구성된 플랜: [{{site.data.keyword.dashdbshort_notm}} for Transactions](https://console.ng.bluemix.net/catalog/services/dashdb-for-transactions-sql-database){:new_window}

필요한 구성이 카탈로그에 없으면 [{{site.data.keyword.IBM_notm}} 영업 팀에 문의(![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘"))](https://www.ibm.com/connect/ibm/us/en/?lnk=fcw){:new_window}하여 다른 옵션을 논의하십시오.

##dashDB for Analytics
{: #dashDB_an}

{{site.data.keyword.dashdbshort_notm}} for Analytics 데이터 웨어하우스 플랜에서는 {{site.data.keyword.dashdbshort_notm}} 데이터 웨어하우스를 사용하여 특수 유형(예: 지리공간 데이터)을 포함한 관계형 데이터를 저장합니다. 기본 제공 분석을 사용하거나 사용자의 앱에 연결하여 다른 클라우드 서비스에서 로드한 데이터 또는 사용자 고유의 데이터를 분석하십시오. 분석 워크로드에 대한 종횡배열 테이블이 있는 고성능, 인메모리 데이터베이스 기술을 활용할 수 있습니다. {{site.data.keyword.dashdbshort_notm}} 웹 콘솔은 데이터 로드와 같은 일반 데이터 관리 태스크, 쿼리 및 R 스크립트 실행과 같은 분석 태스크를 처리합니다.
{: shortdesc}

외부 애플리케이션과 도구를 {{site.data.keyword.dashdbshort_notm}}에 연결하고 이 기능들을 사용하여 데이터를 더 정교하게 관리, 분석할 수도 있습니다. 예: 
   * {{site.data.keyword.IBM_notm}} InfoSphere® Data Architect를 연결하여 데이터베이스 스키마를 디자인하고 배치합니다.
   * Esri ArcGIS를 연결하여 지리 공간 분석을 수행하고 공개된 내용과 사용자의 데이터를 맵핑합니다. 
   * {{site.data.keyword.IBM_notm}} Cognos® 서버를 연결하여 데이터에 대해 Cognos 보고서를 실행합니다.
   * Tableau, Microstrategy 또는 Microsoft Excel 등의 SQL 기반 도구를 연결하여 데이터를 조작하거나 분석합니다.
   * 분석 데이터베이스가 필요한 {{site.data.keyword.Bluemix_short}} 애플리케이션을 연결합니다.
   * Aginity Workbench를 연결하여 Netezza® 데이터 모델과 데이터를 {{site.data.keyword.dashdbshort_notm}}로 마이그레이션합니다.

##dashDB for Analytics 프로비저닝
{: #whse_provision}

{{site.data.keyword.IBM_notm}} {{site.data.keyword.dashdbshort_notm}} for Analytics 데이터 웨어하우스는 {{site.data.keyword.BluSoftlayer_full}}에서 AWS용으로 프로비저닝할 수 있습니다.
{: shortdesc}

{{site.data.keyword.dashdbshort_notm}} for Analytics 데이터 웨어하우스를 AWS용으로 프로비저닝하려면 **{{site.data.keyword.IBM_notm}} {{site.data.keyword.dashdbshort_notm}} for Analytics MPP Small for AWS** 플랜을 선택하십시오.

##dashDB for Transactions
{: #dashDB_tr}

{{site.data.keyword.dashdbshort_notm}} for Transactions 플랜에서는 온라인 트랜잭션 처리에 {{site.data.keyword.dashdbshort_notm}} 관계형 데이터베이스를 사용합니다. 새 애플리케이션 또는 기존 애플리케이션을 연결할 수 있으며 트랜잭션 처리와 데이터 저장을 시작할 수 있습니다. DB2® 및 Oracle 호환성을 통해 소형 또는 대형 애플리케이션을 연결할 수 있으며 관리된 엔터프라이즈급 데이터베이스 시스템의 이점을 활용할 수 있습니다. {{site.data.keyword.dashdbshort_notm}} for Transactions 웹 콘솔을 이용하여 사용자를 관리하고 데이터를 로드하고 연결 정보를 가져올 수 있습니다.
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















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

#dashDB 문제점 해결 
{: #tr_dashDB}

{{site.data.keyword.Bluemix_short}}에서 {{site.data.keyword.dashdbshort}}를 사용하는 것에 대한 몇 가지 일반적인 질문과 답변이 나와 있습니다.
{: shortdesc}

##RStudio에 로그인할 수 없음
{: #r_studio}

RStudio의 싱글 사인온(SSO)은 {{site.data.keyword.dashdblong}}에서 사용할 수 없습니다.
{: shortdesc}

SSO를 사용하여 {{site.data.keyword.dashdbshort_notm}}에서 RStudio에 로그인하려고 하지만, 비밀번호를 묻는 프롬프트가 표시됩니다.
{: tsSymptoms}

{{site.data.keyword.dashdbshort_notm}}에서 SSO를 통해 RStudio를 사용할 수 없습니다.
{: tsCauses}

RStudio에 대한 신임 정보를 가져오려면 `VCAP_SERVICES` 환경 변수를 확인하십시오. 자세한 정보는 [{{site.data.keyword.dashdbshort_notm}} 시작하기](/docs/services/dashDB/dashDB.html#dashDB){:new_window}에 있습니다.
{: tsResolve}


##문제점 해결을 위한 `diag.log` 파일 찾기 실패
{: #diag_log}

`diag.log` 파일을 사용할 수 없습니다.
{: shortdesc}

문제점을 해결하려고 하지만 {{site.data.keyword.dashdbshort_notm}}에 대해 `diag.log` 파일을 찾을 수 없습니다.
{: tsSymptoms}

`diag.log` 파일은 {{site.data.keyword.dashdbshort_notm}}에서 사용할 수 없으며 DB2®에 대한 다른 로그도 마찬가지입니다.
{: tsCauses}

애플리케이션 특정 로그는 Cloud Foundry CLI(명령행 인터페이스)에서 액세스가 가능합니다. CLI에서 **cf logs --recent**를 입력하십시오. 앱을 선택하고 **파일 및 로그**로 이동하여 {{site.data.keyword.Bluemix_notm}} 사이트에서도 해당 로그에 액세스할 수 있습니다.
{: tsResolve}

##조직 또는 영역을 찾을 수 없음: Bluemix ID 불일치
{: #org_space_id}

새 {{site.data.keyword.dashdbshort_notm}} 인스턴스에 대해 조직 또는 영역을 찾을 수 없습니다.
{: shortdesc}

Cloudant® 대시보드에서 웨어하우징 기능을 사용하여 {{site.data.keyword.Bluemix_notm}}의 새 {{site.data.keyword.dashdbshort_notm}} 서비스 인스턴스를 작성하려고 하지만 다음 오류 메시지를 수신합니다. `Cannot find org or space.`
{: tsSymptoms}

{{site.data.keyword.Bluemix_notm}}에서 새 {{site.data.keyword.dashdbshort_notm}} 서비스 인스턴스를 프로비저닝하기 위해, Cloudant 웨어하우징 기능은 인증된 {{site.data.keyword.Bluemix_notm}} 사용자에 대한 "최적 맞춤" {{site.data.keyword.Bluemix_notm}} 대상 조직을 찾으려고 시도합니다. 웨어하우징 기능은 일반적으로 {{site.data.keyword.Bluemix_notm}} ID(일반적으로 사용자의 이메일 주소인 ID)와 일치하는 조직을 찾습니다. 일치하는 조직을 찾을 수 없으며 사용자가 하나의 조직에만 액세스할 수 있는 경우 웨어하우징 기능은 해당 조직을 선택합니다. 사용자에게 자신이 액세스할 수 있는 조직이 없거나 사용자가 여러 조직에 액세스할 수 있는 상황이 있을 수 있습니다. 이 상황에서 Cloudant는 {{site.data.keyword.dashdbshort_notm}} 인스턴스를 프로비저닝하는 위치를 판별할 수 없으며 오류 메시지가 표시됩니다.
{: tsCauses}

문제점을 해결하려면 다음 옵션 중 하나를 선택하십시오.
{: tsResolve}

* Cloudant 대시보드의 드롭 다운 목록에서 {{site.data.keyword.dashdbshort_notm}} 인스턴스가 작성되는 {{site.data.keyword.Bluemix_notm}} 조직을 선택하십시오. 조직을 선택한 후에 두 번째 드롭 다운 목록에서 적합한 영역을 선택하십시오.
* {{site.data.keyword.Bluemix_notm}}에서 직접 {{site.data.keyword.dashdbshort_notm}} 인스턴스를 수동으로 프로비저닝하고, Cloudant 대시보드의 드롭 다운 목록에서 작성된 {{site.data.keyword.dashdbshort_notm}} 서비스 인스턴스를 선택하십시오.


##조직 또는 영역을 찾을 수 없음: 지역 불일치
{: #org_space_region}

새 {{site.data.keyword.dashdbshort_notm}} 인스턴스에 대해 조직 또는 영역을 찾을 수 없습니다.
{: shortdesc}

새 {{site.data.keyword.dashdbshort_notm}} 서비스 인스턴스를 작성하려고 하지만 기존 {{site.data.keyword.dashdbshort_notm}} 서비스 인스턴스 또는 {{site.data.keyword.Bluemix_notm}} 조직의 드롭 다운 목록이 비어 있습니다. 새 {{site.data.keyword.dashdbshort_notm}} 서비스 인스턴스를 프로비저닝할 수 없으며 다음 오류 메시지를 수신합니다. `Cannot find org or space.`
{: tsSymptoms}

사용자의 {{site.data.keyword.Bluemix_notm}} 계정이 Cloudant 클러스터와 다른 지역에 있는 경우 프로비저닝 요청이 실패합니다. 예를 들어, {{site.data.keyword.Bluemix_notm}} 계정은 유럽 영국 지역에서 온보드되었지만 Cloudant 클러스터가 미국 남부 지역에서 작동합니다. 이에 따라 Cloudant 대시보드의 기존 서비스 인스턴스 및 조직 드롭 다운 목록이 비어 있거나 모두 다른 지역에 속하는 조직 및 영역을 표시할 수 있습니다.
{: tsCauses}

1. {{site.data.keyword.Bluemix_notm}} 대시보드에 로그인하고 예상 지역으로 스위칭하십시오. 프롬프트에 따라 해당 영역의 온보딩을 완료하십시오. 대안으로서, 적합한 영역에서 {{site.data.keyword.Bluemix_notm}} 계정을 작성하십시오. 
2. Cloudant 대시보드에 로그인하여 {{site.data.keyword.dashdbshort_notm}} 서비스 인스턴스 선택을 반복하십시오.
{: tsResolve}

##서비스 한계 초과
{: #service_limit}

{{site.data.keyword.Bluemix_notm}}의 {{site.data.keyword.dashdbshort_notm}} 서비스가 자체 한계를 초과했습니다.
{: shortdesc}

{{site.data.keyword.Bluemix_notm}}에 있는 {{site.data.keyword.dashdbshort_notm}} 서비스를 사용하는 중에 다음 오류 메시지가 표시됩니다. `Exceeded your organization’s services limit.`
{: tsSymptoms}

서비스에 제한이 있는 {{site.data.keyword.Bluemix_notm}} 평가판을 사용 중입니다.
{: tsCauses}

문제점을 해결하려면 다음 옵션 중 하나를 선택하십시오.
{: tsResolve}

* 리소스를 확보하려면, 더 이상 사용하지 않는 {{site.data.keyword.Bluemix_notm}} 대시보드의 서비스를 삭제하십시오. 새 {{site.data.keyword.dashdbshort_notm}} 인스턴스에 대해 프로비저닝 요청을 재시도하십시오.
* {{site.data.keyword.Bluemix_notm}} 대시보드를 사용하여 서비스 제한이 없는 적절한 조직 또는 영역에서 {{site.data.keyword.dashdbshort_notm}} 인스턴스를 수동으로 프로비저닝하십시오. Cloudant 대시보드에서 해당 인스턴스를 선택하십시오.


##dashDB 서비스가 사용 불가능함
{: #outages}

{{site.data.keyword.Bluemix_notm}}의 {{site.data.keyword.dashdbshort_notm}} 서비스를 사용할 수 없습니다.
{: shortdesc}

데이터 웨어하우스를 작성하려는 시도가 500 오류로 실패했거나, SDP 로드에서 SQL 오류를 보고합니다.
{: tsSymptoms}

{{site.data.keyword.Bluemix_notm}}의 {{site.data.keyword.dashdbshort_notm}} 서비스가 스케줄된 유지보수 프로시저를 진행 중이거나 알려진 가동 중단이 발생했습니다.
{: tsCauses}

다음 상태 페이지를 확인하여 {{site.data.keyword.Bluemix_notm}}에서 {{site.data.keyword.dashdbshort_notm}} 서비스의 상태를 판별할 수 있습니다.
{: tsResolve}

* [{{site.data.keyword.Bluemix_notm}} 지원 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://developer.ibm.com/bluemix/support/#status){:new_window}
* 상태 모니터링:
  * [모든 지역 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://console.eu-gb.bluemix.net/status?tags=platform,runtimes,services,ibm:yp:eu-gb,ibm:yp:eu-de,ibm:yp:us-south,ibm:yp:au-syd){:new_window}
  <!--[US - South region ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://estado.ng.bluemix.net/internalstatus){:new_window}
  [Europe - United Kingdom region ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://estado.eu-gb.bluemix.net/internalstatus){:new_window}
  [Europe - Germany region ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://estado.eu-de.bluemix.net/internalstatus){:new_window}
  [Australia - Sydney region ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://estado.au-syd.bluemix.net/internalstatus){:new_window}-->


##dashDB에 대한 도움 및 지원 받기
{: #gettinghelp}

{{site.data.keyword.dashdbshort_notm}} 사용 시 문제점 또는 질문이 있는 경우, 정보를 검색하거나 포럼을 통해 질문하여 도움을 받을 수 있습니다. 또한 지원 티켓을 열 수도 있습니다.
{: shortdesc}

포럼을 사용하여 질문하는 경우, {{site.data.keyword.Bluemix}} 개발 팀에 표시되도록 질문에 태그를 지정하십시오.

* {{site.data.keyword.dashdbshort_notm}}에서 앱을 개발하거나 배치하는 데 대한 기술적 질문이 있는 경우 [Stack Overflow(![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘"))](http://stackoverflow.com/search?q=dashdb+bluemix){:new_window}에 질문을 게시하고 "bluemix" 및 "dashdb"로 질문에 태그를 지정하십시오.
* 서비스 및 시작하기 지시사항에 대해 질문하려면 [IBM developerWorks® dW Answers(![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘"))](https://developer.ibm.com/answers/topics/dashdb/?smartspace=bluemix){:new_window} 포럼을 사용하십시오. "bluemix" 및 "dashdb" 태그를 포함하십시오.

포럼 사용에 대한 자세한 내용은 [도움 받기](/docs/support/index.html#getting-help){:new_window}를 참조하십시오. 

IBM 지원 티켓 열기에 대한 정보 또는 지원 레벨 및 티켓 심각도에 대한 정보는 [지원 문의](/docs/support/index.html#contacting-support){:new_window}를 참조하십시오.




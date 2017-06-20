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

#dashDB のトラブルシューティング 
{: #tr_dashDB}

{{site.data.keyword.Bluemix_short}} における
{{site.data.keyword.dashdbshort}} の使用に関するいくつかの一般的な質問に対する答えを以下に示します。
{: shortdesc}

##RStudio にログインできない
{: #r_studio}

{{site.data.keyword.dashdblong}} では、RStudio へのシングル・サインオン (SSO) は使用できません。
{: shortdesc}

{{site.data.keyword.dashdbshort_notm}} から SSO を使用して RStudio にログインしようとしたが、パスワードの入力を求められる。
{: tsSymptoms}

{{site.data.keyword.dashdbshort_notm}} では RStudio への SSO は使用できません。
{: tsCauses}

RStudio の資格情報を入手するには、`VCAP_SERVICES` 環境変数を調べてください。[{{site.data.keyword.dashdbshort_notm}} 概説](/docs/services/dashDB/dashDB.html#dashDB){:new_window}に詳しい説明があります。
{: tsResolve}


##トラブルシューティング用の `diag.log` ファイルが見つからない
{: #diag_log}

`diag.log` ファイルが使用可能でありません。
{: shortdesc}

トラブルシューティングを実行しようとしたが、{{site.data.keyword.dashdbshort_notm}} 用の `diag.log` ファイルが見つからない。
{: tsSymptoms}

{{site.data.keyword.dashdbshort_notm}} に `diag.log` ファイルがなく、他の DB2® 固有のログもありません。
{: tsCauses}

アプリケーション固有のログには、Cloud Foundry CLI (コマンド・ライン・インターフェース) からアクセスできます。CLI から **cf logs --recent** と入力します。
これらのログには、アプリを選択してから**「ファイルとログ」**に移動することによって、{{site.data.keyword.Bluemix_notm}} サイトでもアクセスできます。
{: tsResolve}

##組織またはスペースが見つからない: Bluemix ID の不一致
{: #org_space_id}

新規の {{site.data.keyword.dashdbshort_notm}} インスタンス用の組織またはスペースが見つかりません。
{: shortdesc}

Cloudant® ダッシュボードのウェアハウジング・フィーチャーを使用して {{site.data.keyword.Bluemix_notm}} 内に新規の {{site.data.keyword.dashdbshort_notm}} サービス・インスタンスを作成しようとしたが、`Cannot find org or space.` というエラー・メッセージが出される。
{: tsSymptoms}

{{site.data.keyword.Bluemix_notm}} 内で新規の {{site.data.keyword.dashdbshort_notm}} サービス・インスタンスをプロビジョンするために、Cloudant ウェアハウジング・フィーチャーは、認証済みの {{site.data.keyword.Bluemix_notm}} ユーザーのために最適の {{site.data.keyword.Bluemix_notm}} ターゲット組織を見つけようとします。一般的にウェアハウジング・フィーチャーは、{{site.data.keyword.Bluemix_notm}} ID (通常、ユーザーの E メール・アドレスである ID) に一致する組織を検索します。一致する組織が検出されず、ユーザーがアクセスできるのが 1 つの組織のみの場合、ウェアハウジング・フィーチャーはその組織を選択します。アクセス可能な組織をユーザーが持っていない状態や、ユーザーが複数の組織にアクセスできる状態も考えられます。そのような状態の場合、Cloudant は、{{site.data.keyword.dashdbshort_notm}} インスタンスのプロビジョン先を判断できず、エラー・メッセージが表示されます。
{: tsCauses}

この問題を解決するには、次のいずれかのオプションを選択してください。
{: tsResolve}

* Cloudant ダッシュボードのドロップダウン・リストから、{{site.data.keyword.dashdbshort_notm}} インスタンスを作成したい {{site.data.keyword.Bluemix_notm}} 組織を選択します。組織を選択したら、2 番目のドロップダウン・リストから適切なスペースを選択します。
* {{site.data.keyword.dashdbshort_notm}} インスタンスを {{site.data.keyword.Bluemix_notm}} に直接、手動でプロビジョンし、Cloudant ダッシュボードのドロップダウン・リストから、作成された {{site.data.keyword.dashdbshort_notm}} サービス・インスタンスを選択します。


##組織またはスペースが見つからない: 地域の不一致
{: #org_space_region}

新規の {{site.data.keyword.dashdbshort_notm}} インスタンス用の組織またはスペースが見つかりません。
{: shortdesc}

新規の {{site.data.keyword.dashdbshort_notm}} サービス・インスタンスを作成しようとしているが、既存の {{site.data.keyword.dashdbshort_notm}} サービス・インスタンスまたは {{site.data.keyword.Bluemix_notm}} 組織のドロップダウン・リストが空である。新規の {{site.data.keyword.dashdbshort_notm}} サービス・インスタンスをプロビジョンできず、`Cannot find org or space.` というメッセージが出される。
{: tsSymptoms}

ユーザーの {{site.data.keyword.Bluemix_notm}} アカウントが Cloudant クラスターとは異なる地域にある場合、プロビジョニング要求は失敗します。例えば、{{site.data.keyword.Bluemix_notm}} アカウントは欧州英国地域でオンボーディングされたが、Cloudant クラスターが米国南部地域で作業を行っている場合などです。その結果、Cloudant ダッシュボードにある既存のサービス・インスタンスおよび組織のドロップダウン・リストが空になったり、完全に他の地域に属する組織およびスペースが表示されたりする可能性があります。
{: tsCauses}

1. {{site.data.keyword.Bluemix_notm}} ダッシュボードにログインし、予期されている地域に切り替えてください。すべてのプロンプトに従い、その地域でのオンボーディングを完了してください。あるいは、対象の地域に {{site.data.keyword.Bluemix_notm}} アカウントを作成してください。
2. Cloudant ダッシュボードにログインして、{{site.data.keyword.dashdbshort_notm}} サービス・インスタンスの選択を繰り返してください。
{: tsResolve}

##サービス制限を超えた
{: #service_limit}

{{site.data.keyword.Bluemix_notm}} での {{site.data.keyword.dashdbshort_notm}} サービス制限を超えました。
{: shortdesc}

{{site.data.keyword.Bluemix_notm}} で {{site.data.keyword.dashdbshort_notm}} サービスを使用中に、`Exceeded your organization’s services limit.` というエラー・メッセージが表示される。
{: tsSymptoms}

無料の {{site.data.keyword.Bluemix_notm}} トライアルをまだ使用していますが、そのトライアルにはサービス制限があります。
{: tsCauses}

この問題を解決するには、次のいずれかのオプションを選択してください。
{: tsResolve}

* リソースを解放するために、もう使用していない、{{site.data.keyword.Bluemix_notm}} ダッシュボード内のサービスを削除してください。新規の {{site.data.keyword.dashdbshort_notm}} インスタンスのプロビジョニング要求を再試行してください。
* {{site.data.keyword.Bluemix_notm}} ダッシュボードを使用して、サービス制限のない、対象の組織またはスペース内に {{site.data.keyword.dashdbshort_notm}} インスタンスを手動でプロビジョンします。Cloudant ダッシュボードからそのインスタンスを選択してください。


##dashDB サービスが使用不可である
{: #outages}

{{site.data.keyword.Bluemix_notm}} 内の {{site.data.keyword.dashdbshort_notm}} サービスが使用不可である可能性があります。
{: shortdesc}

データウェアハウスを作成しようとしたが、500 エラーで失敗するか、SDP ロードが SQL エラーを報告する。
{: tsSymptoms}

{{site.data.keyword.Bluemix_notm}} 内の {{site.data.keyword.dashdbshort_notm}} サービスで定期保守手順が実行されているか、既知の障害が発生しました。
{: tsCauses}

以下の状況ページを確認することにより、{{site.data.keyword.Bluemix_notm}} 内の {{site.data.keyword.dashdbshort_notm}} サービスの状況を判別できます。
{: tsResolve}

* [{{site.data.keyword.Bluemix_notm}} サポート ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://developer.ibm.com/bluemix/support/#status){:new_window}
* 状況モニター:
  * [すべての地域 ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://console.eu-gb.bluemix.net/status?tags=platform,runtimes,services,ibm:yp:eu-gb,ibm:yp:eu-de,ibm:yp:us-south,ibm:yp:au-syd){:new_window}
  <!--[US - South region ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://estado.ng.bluemix.net/internalstatus){:new_window}
  [Europe - United Kingdom region ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://estado.eu-gb.bluemix.net/internalstatus){:new_window}
  [Europe - Germany region ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://estado.eu-de.bluemix.net/internalstatus){:new_window}
  [Australia - Sydney region ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://estado.au-syd.bluemix.net/internalstatus){:new_window}-->


##dashDB のヘルプおよびサポートの利用
{: #gettinghelp}

{{site.data.keyword.dashdbshort_notm}} を使用しているときに問題や質問がある場合は、情報を検索したり、フォーラムで質問したりして、
ヘルプを利用することができます。また、サポート・チケットをオープンすることもできます。
{: shortdesc}

フォーラムを使用して質問する場合は、{{site.data.keyword.Bluemix}} の開発チームの目に触れるように、質問にタグを付けます。

* {{site.data.keyword.dashdbshort_notm}} を使用したアプリの開発やデプロイについて技術的な質問がある場合は、質問を [Stack Overflow ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](http://stackoverflow.com/search?q=dashdb+bluemix){:new_window} に投稿し、質問に「bluemix」と「dashdb」のタグを付けます。
* サービスや開始手順に関する質問については、[IBM developerWorks® dW Answers ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://developer.ibm.com/answers/topics/dashdb/?smartspace=bluemix){:new_window} フォーラムを使用します。「bluemix」と「dashdb」のタグを付けてください。

フォーラムの使用について詳しくは、[ヘルプの利用](/docs/support/index.html#getting-help){:new_window}を参照してください。

IBM サポート・チケットのオープンや、サポート・レベルおよびチケットの重大度について詳しくは、[サポートへのお問い合わせ](/docs/support/index.html#contacting-support){:new_window}を参照してください。




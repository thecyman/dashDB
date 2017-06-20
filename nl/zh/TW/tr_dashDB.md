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

#dashDB 疑難排解 
{: #tr_dashDB}

以下是關於在 {{site.data.keyword.Bluemix_short}} 中使用 {{site.data.keyword.dashdbshort}} 的數個常見問題的回答。
{: shortdesc}

##無法登入 RStudio
{: #r_studio}

RStudio 的單一登入 (SSO) 無法用於 {{site.data.keyword.dashdblong}}。
{: shortdesc}

您要使用 SSO 從 {{site.data.keyword.dashdbshort_notm}} 登入 RStudio，但系統提示您輸入密碼。
{: tsSymptoms}

SSO to RStudio 無法用於 {{site.data.keyword.dashdbshort_notm}}。
{: tsCauses}

若要取得 RStudio 的認證，請參閱 `VCAP_SERVICES` 環境變數。如需進一步資訊，請參閱[開始使用 {{site.data.keyword.dashdbshort_notm}}](/docs/services/dashDB/dashDB.html#dashDB){:new_window}。
{: tsResolve}


##找不到 `diag.log` 檔來進行疑難排解
{: #diag_log}

無法使用 `diag.log` 檔。
{: shortdesc}

您要疑難排解但找不到 {{site.data.keyword.dashdbshort_notm}} 的 `diag.log` 檔。
{: tsSymptoms}

{{site.data.keyword.dashdbshort_notm}} 上沒有 `diag.log` 檔，也沒有任何其他 DB2® 特定的日誌。
{: tsCauses}

可以透過 Cloud Foundry CLI（指令行介面）存取應用程式特定的日誌。從 CLI 輸入 **cf logs --recent**。也可以在 {{site.data.keyword.Bluemix_notm}} 網站上存取日誌，方法是選取您的應用程式，然後移至**檔案及日誌**。
{: tsResolve}

##找不到組織或空間：Bluemix ID 不符
{: #org_space_id}

找不到新 {{site.data.keyword.dashdbshort_notm}} 實例的組織或空間。
{: shortdesc}

您要使用 Cloudant® 儀表板中的倉儲特性，在 {{site.data.keyword.Bluemix_notm}} 中建立新的 {{site.data.keyword.dashdbshort_notm}} 服務實例，但收到下列錯誤訊息：`找不到組織或空間`。
{: tsSymptoms}

為了在 {{site.data.keyword.Bluemix_notm}} 中佈建新的 {{site.data.keyword.dashdbshort_notm}} 服務實例，Cloudant 倉儲特性會嘗試為已鑑別 {{site.data.keyword.Bluemix_notm}} 使用者尋找「最適合」的 {{site.data.keyword.Bluemix_notm}} 目標組織。倉儲特性一般會尋找與 {{site.data.keyword.Bluemix_notm}} ID 相符的組織，而此 ID 通常是使用者的電子郵件位址。如果找不到相符的組織，而且使用者只能存取一個組織，則倉儲特性會選取該組織。在某些情況下，使用者可能沒有可存取的組織，或使用者可以存取多個組織。在那些狀況下，Cloudant 無法判定在何處佈建 {{site.data.keyword.dashdbshort_notm}} 實例，並且會顯示錯誤訊息。
{: tsCauses}

若要解決此問題，請選擇下列其中一個選項：
{: tsResolve}

* 從 Cloudant 儀表板的下拉清單中，選取要在其中建立 {{site.data.keyword.dashdbshort_notm}} 實例的 {{site.data.keyword.Bluemix_notm}} 組織。在您選取組織之後，請從次要下拉清單中選取適當的空間。
* 在 {{site.data.keyword.Bluemix_notm}} 中直接手動佈建 {{site.data.keyword.dashdbshort_notm}} 實例，並從 Cloudant 儀表板的下拉清單中選取所建立的 {{site.data.keyword.dashdbshort_notm}} 服務實例。


##找不到組織或空間：地區不符
{: #org_space_region}

找不到新 {{site.data.keyword.dashdbshort_notm}} 實例的組織或空間。
{: shortdesc}

您要建立新的 {{site.data.keyword.dashdbshort_notm}} 服務實例，但是現有 {{site.data.keyword.dashdbshort_notm}} 服務實例或 {{site.data.keyword.Bluemix_notm}} 組織的下拉清單是空的。無法佈建新的 {{site.data.keyword.dashdbshort_notm}} 服務實例，並收到下列錯誤訊息：`找不到組織或空間`。
{: tsSymptoms}

如果使用者的 {{site.data.keyword.Bluemix_notm}} 帳戶位於與 Cloudant 叢集不同的地區，則佈建要求會失敗。例如，{{site.data.keyword.Bluemix_notm}} 帳戶是在歐洲英國地區上線，但是 Cloudant 叢集運作於美國南部地區。因此，Cloudant 儀表板中的現有服務實例及組織下拉清單可能是空的，或顯示屬於完全不同地區的組織及空間。
{: tsCauses}

1. 登入 {{site.data.keyword.Bluemix_notm}} 儀表板，並切換至預期的地區。請遵循所有提示來完成該地區中的上線作業。替代方案是在適當地區中建立 {{site.data.keyword.Bluemix_notm}} 帳戶。
2. 登入 Cloudant 儀表板，以重複 {{site.data.keyword.dashdbshort_notm}} 服務實例選項。
{: tsResolve}

##已超出服務限制
{: #service_limit}

{{site.data.keyword.Bluemix_notm}} 中的 {{site.data.keyword.dashdbshort_notm}} 服務已超出其限制。
{: shortdesc}

在 {{site.data.keyword.Bluemix_notm}} 中使用 {{site.data.keyword.dashdbshort_notm}} 服務時，會顯示下列錯誤訊息：`已超出組織的服務限制`。
{: tsSymptoms}

您仍在使用具有服務限制的免費 {{site.data.keyword.Bluemix_notm}} 試用。
{: tsCauses}

若要解決此問題，請選擇下列其中一個選項：
{: tsResolve}

* 若要釋放資源，請捨棄 {{site.data.keyword.Bluemix_notm}} 儀表板中您不再使用的服務。請重試新 {{site.data.keyword.dashdbshort_notm}} 實例的佈建要求。
* 使用 {{site.data.keyword.Bluemix_notm}} 儀表板，以在沒有服務限制的適當組織或空間中手動佈建 {{site.data.keyword.dashdbshort_notm}} 實例。請從 Cloudant 儀表板中選取該實例。


##dashDB 服務無法使用
{: #outages}

{{site.data.keyword.Bluemix_notm}} 中的 {{site.data.keyword.dashdbshort_notm}} 服務可能無法使用。
{: shortdesc}

嘗試建立資料倉儲失敗且錯誤為 500，或 SDP 載入報告 SQL 錯誤。
{: tsSymptoms}

{{site.data.keyword.Bluemix_notm}} 中的 {{site.data.keyword.dashdbshort_notm}} 服務正在進行排程的維護程序，或發生已知的中斷。
{: tsCauses}

檢查下列狀態頁面，您就可以判定 {{site.data.keyword.Bluemix_notm}} 中 {{site.data.keyword.dashdbshort_notm}} 服務的狀態：
{: tsResolve}

* [{{site.data.keyword.Bluemix_notm}} 支援中心 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://developer.ibm.com/bluemix/support/#status){:new_window}
* 狀態監視：
  * [所有地區 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://console.eu-gb.bluemix.net/status?tags=platform,runtimes,services,ibm:yp:eu-gb,ibm:yp:eu-de,ibm:yp:us-south,ibm:yp:au-syd){:new_window}
  <!--[US - South region ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://estado.ng.bluemix.net/internalstatus){:new_window}
  [Europe - United Kingdom region ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://estado.eu-gb.bluemix.net/internalstatus){:new_window}
  [Europe - Germany region ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://estado.eu-de.bluemix.net/internalstatus){:new_window}
  [Australia - Sydney region ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://estado.au-syd.bluemix.net/internalstatus){:new_window}-->


##取得 dashDB 的協助及支援
{: #gettinghelp}

如果您在使用 {{site.data.keyword.dashdbshort_notm}} 時有任何問題，可以搜尋資訊或透過討論區來發問。您也可以開啟支援問題單。
{: shortdesc}

使用討論區來發問時，請標記您的問題，讓 {{site.data.keyword.Bluemix}} 開發團隊可以看到它。

* 如果您對於使用 {{site.data.keyword.dashdbshort_notm}} 來開發或部署應用程式有技術方面的問題，請將您的問題張貼在 [Stack Overflow ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](http://stackoverflow.com/search?q=dashdb+bluemix){:new_window}，並且在您的問題上標記 "bluemix" 及 "dashdb"。
* 對於服務的相關問題，以及開始使用的指示，請使用 [IBM developerWorks® dW Answers ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://developer.ibm.com/answers/topics/dashdb/?smartspace=bluemix){:new_window} 討論區。請包含 "bluemix" 及 "dashdb" 標籤。

如需使用討論區的詳細資訊，請參閱[取得協助](/docs/support/index.html#getting-help){:new_window}。

如需開啟 IBM 支援問題單，或是支援層次和問題單嚴重性的相關資訊，請參閱：[與支援中心聯絡](/docs/support/index.html#contacting-support){:new_window}。




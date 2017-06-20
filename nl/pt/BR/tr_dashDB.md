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

#Resolução de problemas do dashDB 
{: #tr_dashDB}

Aqui estão as respostas a várias perguntas sobre o uso do {{site.data.keyword.dashdbshort}} no {{site.data.keyword.Bluemix_short}}.
{: shortdesc}

##Não é possível efetuar login no RStudio
{: #r_studio}

A SSO (Conexão única) para o RStudio não está disponível para o {{site.data.keyword.dashdblong}}.
{: shortdesc}

Você deseja efetuar login no RStudio pelo {{site.data.keyword.dashdbshort_notm}} usando a SSO, mas uma senha é solicitada.
{: tsSymptoms}

A SSO para RStudio não está disponível em {{site.data.keyword.dashdbshort_notm}}.
{: tsCauses}

Para obter suas credenciais para o RStudio, consulte sua variável de ambiente `VCAP_SERVICES`. Informações adicionais
estão disponíveis em [Introdução ao {{site.data.keyword.dashdbshort_notm}}](/docs/services/dashDB/dashDB.html#dashDB){:new_window}.
{: tsResolve}


##Não é possível localizar o arquivo `diag.log` para resolução de problemas
{: #diag_log}

O arquivo `diag.log` não está disponível.
{: shortdesc}

Você deseja solucionar problemas e não consegue localizar o arquivo `diag.log` para o {{site.data.keyword.dashdbshort_notm}}.
{: tsSymptoms}

O arquivo `diag.log` não está disponível no {{site.data.keyword.dashdbshort_notm}} nem em qualquer outro log específico ao DB2®.
{: tsCauses}

Os logs específicos do aplicativo podem ser acessados pela
CLI (interface de linha de comandos) do Cloud Foundry. Na CLI, insira **cf
logs --recent**. Os logs também podem ser acessados no site
do {{site.data.keyword.Bluemix_notm}} selecionando seu aplicativo e acessando **Arquivos e logs**.
{: tsResolve}

##Não é possível localizar a organização ou o espaço: incompatibilidade de ID do Bluemix
{: #org_space_id}

Uma organização ou um espaço não pode ser localizado para uma nova instância do {{site.data.keyword.dashdbshort_notm}}.
{: shortdesc}

Você deseja criar uma nova instância de serviço do {{site.data.keyword.dashdbshort_notm}} no {{site.data.keyword.Bluemix_notm}} usando o recurso de warehousing no painel Cloudant®, mas obtém a mensagem de erro a seguir: `Não é possível localizar a organização ou o espaço.`
{: tsSymptoms}

Para provisionar uma nova instância de serviço do {{site.data.keyword.dashdbshort_notm}} no {{site.data.keyword.Bluemix_notm}}, o recurso de warehousing do Cloudant tenta localizar a organização de destino do
{{site.data.keyword.Bluemix_notm}} "mais adequada" para o usuário autenticado do {{site.data.keyword.Bluemix_notm}}. Em geral, o recurso de warehousing procura uma organização que corresponda
ao ID do {{site.data.keyword.Bluemix_notm}},
um ID que geralmente é o endereço de e-mail do usuário. Se uma organização
correspondente não for localizada e o usuário tiver acesso a somente uma organização,
o recurso de warehousing selecionará essa organização. Pode haver
situações em que o usuário não tenha uma organização à qual possa
ter acesso ou o usuário tenha acesso a várias organizações. Nessas situações, o Cloudant não pode determinar onde provisionar a instância do {{site.data.keyword.dashdbshort_notm}} e a mensagem de erro é exibida.
{: tsCauses}

Para resolver o problema, escolha uma das opções
a seguir:
{: tsResolve}

* Na lista suspensa no painel do Cloudant, selecione a organização do {{site.data.keyword.Bluemix_notm}} na qual deseja que a instância do {{site.data.keyword.dashdbshort_notm}} seja criada. Depois de selecionar a organização, selecione o espaço
apropriado na lista suspensa secundária.
* Provisione manualmente uma instância do {{site.data.keyword.dashdbshort_notm}} diretamente no {{site.data.keyword.Bluemix_notm}} e selecione a instância de serviço criada do {{site.data.keyword.dashdbshort_notm}} na lista suspensa no painel Cloudant.


##Não é possível localizar organização ou espaço: incompatibilidade de regiões
{: #org_space_region}

Uma organização ou um espaço não pode ser localizado para uma nova instância do {{site.data.keyword.dashdbshort_notm}}.
{: shortdesc}

Você deseja criar uma nova instância de serviço do {{site.data.keyword.dashdbshort_notm}},
mas as listas suspensas de instâncias de serviço do {{site.data.keyword.dashdbshort_notm}}
ou de organizações do {{site.data.keyword.Bluemix_notm}} existentes
estão vazias. Uma nova instância de serviço do {{site.data.keyword.dashdbshort_notm}} não pode ser provisionada e você obtém a mensagem de erro a seguir: `Não é possível localizar a organização ou o espaço.`
{: tsSymptoms}

Se a conta do usuário do {{site.data.keyword.Bluemix_notm}} estiver em uma região diferente do cluster do Cloudant, a solicitação de fornecimento falhará. Por exemplo, a conta do {{site.data.keyword.Bluemix_notm}} foi integrada na região do Reino Unido, mas o cluster do Cloudant funciona na região do sul dos EUA. Como resultado, a instância de serviço existente e as listas suspensas da organização no painel do Cloudant podem estar vazias ou mostrarem organizações e espaços juntos que pertençam a uma região diferente.
{: tsCauses}

1. Efetue login no painel do {{site.data.keyword.Bluemix_notm}}
e alterne para a região esperada. Siga os prompts para concluir
o onboarding nessa região. Como alternativa, crie uma conta do {{site.data.keyword.Bluemix_notm}}
na região apropriada.
2. Efetue login no painel do Cloudant para repetir a seleção da instância de serviço do {{site.data.keyword.dashdbshort_notm}}.
{: tsResolve}

##Limite de serviços excedido
{: #service_limit}

O serviço {{site.data.keyword.dashdbshort_notm}}
no {{site.data.keyword.Bluemix_notm}} excedeu
seu limite.
{: shortdesc}

Enquanto estiver usando o serviço do {{site.data.keyword.dashdbshort_notm}} no {{site.data.keyword.Bluemix_notm}}, a mensagem de erro a seguir será exibida: `Limite de serviços da organização excedido.`
{: tsSymptoms}

Você continua na avaliação sem custo do {{site.data.keyword.Bluemix_notm}},
que possui limites de serviço.
{: tsCauses}

Para resolver o problema, escolha uma das opções
a seguir:
{: tsResolve}

* Para liberar recursos, elimine serviços no painel do {{site.data.keyword.Bluemix_notm}}
que não são mais usados. Tente novamente a solicitação de fornecimento de uma nova instância do {{site.data.keyword.dashdbshort_notm}}.
* Use o painel do {{site.data.keyword.Bluemix_notm}}
para provisionar manualmente uma instância do {{site.data.keyword.dashdbshort_notm}}
em uma organização ou um espaço apropriado que não possua limites de
serviço. Selecione essa instância no painel do Cloudant.


##O serviço dashDB não está disponível
{: #outages}

O serviço {{site.data.keyword.dashdbshort_notm}}
no {{site.data.keyword.Bluemix_notm}} pode
não estar disponível.
{: shortdesc}

Uma tentativa de criar um data warehouse falha com um erro 500
ou um carregamento SDP relata um erro de SQL.
{: tsSymptoms}

O serviço {{site.data.keyword.dashdbshort_notm}}
no {{site.data.keyword.Bluemix_notm}} está
passando por um procedimento de manutenção planejada ou ocorreu uma indisponibilidade
conhecida.
{: tsCauses}

É possível determinar o status do serviço {{site.data.keyword.dashdbshort_notm}}
no {{site.data.keyword.Bluemix_notm}}
verificando as páginas de status a seguir:
{: tsResolve}

* [{{site.data.keyword.Bluemix_notm}} Suporte
![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://developer.ibm.com/bluemix/support/#status){:new_window}
* Monitoramento de status:
  * [Todas
as regiões ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://console.eu-gb.bluemix.net/status?tags=platform,runtimes,services,ibm:yp:eu-gb,ibm:yp:eu-de,ibm:yp:us-south,ibm:yp:au-syd){:new_window}
  <!--[US - South region ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://estado.ng.bluemix.net/internalstatus){:new_window}
  [Europe - United Kingdom region ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://estado.eu-gb.bluemix.net/internalstatus){:new_window}
  [Europe - Germany region ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://estado.eu-de.bluemix.net/internalstatus){:new_window}
  [Australia - Sydney region ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://estado.au-syd.bluemix.net/internalstatus){:new_window}-->


##Obtendo ajuda e suporte para o dashDB
{: #gettinghelp}

Se você tiver problemas ou perguntas ao usar o
{{site.data.keyword.dashdbshort_notm}},
poderá obter ajuda procurando por informações ou fazendo perguntas
através de um fórum. Também é possível abrir um chamado de suporte.
{: shortdesc}

Ao usar os fóruns para fazer uma pergunta, marque a sua pergunta
para que ela possa ser vista pelas equipes de desenvolvimento do {{site.data.keyword.Bluemix}}.

* Se você tiver questões técnicas sobre como desenvolver ou implementar um app com o {{site.data.keyword.dashdbshort_notm}}, poste sua questão no [Stack Overflow ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](http://stackoverflow.com/search?q=dashdb+bluemix){:new_window} e identifique sua questão com "bluemix" e "dashdb".
* Para questões sobre o serviço e instruções para introdução, use o fórum [IBM developerWorks® dW Answers ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://developer.ibm.com/answers/topics/dashdb/?smartspace=bluemix){:new_window}. Inclua as tags "bluemix" e "dashdb".

Consulte
[Obtendo
ajuda](/docs/support/index.html#getting-help){:new_window} para obter mais detalhes sobre o uso dos fóruns.

Para obter informações sobre como abrir um chamado de suporte da IBM ou sobre níveis de suporte e severidades de chamados, consulte [Entrando em contato com o suporte](/docs/support/index.html#contacting-support){:new_window}.




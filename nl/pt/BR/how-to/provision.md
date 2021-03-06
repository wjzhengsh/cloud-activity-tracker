---

copyright:
  years: 2016, 2019
lastupdated: "2019-03-06"

keywords: IBM Cloud, Activity Tracker, provision instance

subcollection: cloud-activity-tracker

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:codeblock: .codeblock}
{:tip: .tip}
{:download: .download}
{:important: .important}
{:note: .note}



# Rastreador de Atividade de Provisionamento
{: #provision}

É possível fornecer o serviço do {{site.data.keyword.cloudaccesstraillong}}
por meio da UI do {{site.data.keyword.cloud_notm}} ou da linha de comandos.
{:shortdesc}


## Provisionando por meio da UI
{: #provision_ui}

Conclua as etapas a seguir para provisionar uma instância do serviço {{site.data.keyword.cloudaccesstraillong_notm}} no {{site.data.keyword.cloud_notm}}:

1. [Efetue login em sua conta do {{site.data.keyword.cloud_notm}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://cloud.ibm.com/login){:new_window}.
    
	Após você efetuar login com o seu ID do usuário e senha, a UI do {{site.data.keyword.cloud_notm}} será aberta.

2. Clique em **Catálogo**. A lista dos serviços que estão disponíveis no {{site.data.keyword.cloud_notm}} é aberta.

3. Selecione a categoria **Segurança** para filtrar a lista de serviços que é exibida.

    O serviço também está disponível sob a categoria **DevOps**.

4. Clique no tile **Activity Tracker**.

5. Configure as informações que definem onde o serviço será provisionado. 

    Insira os dados conforme indicado na tabela a seguir: 

    <table>
	  <caption>Tabela 1. Campos que são necessários para provisionar o serviço {{site.data.keyword.cloudaccesstrailshort}}</caption>
	  <tr>
	    <th>Campo</th>
		<th>Valor</th>
	  </tr>
	  <tr>
	    <td>Selecionar região para implementar em:</td>
		<td>Os valores válidos são: Sul dos EUA, Reino Unido, Alemanha, Sydney</td>
	  </tr>
	  <tr>
	    <td>Escolha uma organização:</td>
		<td>Selecione a organização na qual você planeja monitorar a atividade.</td>
	  </tr>
	  <tr>
	    <td>Escolha um espaço:</td>
		<td>Selecione um espaço na organização que você selecionou no qual planeja monitorar a atividade.</td>
	  </tr>
	</table>

6. Selecione um plano de serviço. 

    Por padrão, o plano **grátis** está configurado.

    Para obter mais informações, veja [Planos de serviço](/docs/services/cloud-activity-tracker/how-to?topic=cloud-activity-tracker-change_plan#change_plan).
	
7. Clique em **Criar** para provisionar o serviço do {{site.data.keyword.cloudaccesstrailshort}} no espaço do {{site.data.keyword.cloud_notm}} no qual você está com login efetuado.
  
 

## Provisionando por meio da CLI
{: #provision_cli}

Conclua as etapas a seguir para provisionar uma instância do serviço do {{site.data.keyword.cloudaccesstrailshort}} no {{site.data.keyword.cloud_notm}} por meio da linha de comandos:

1. [Pré-requisito] Instale a CLI do {{site.data.keyword.cloud_notm}}.

   Para obter mais informações, consulte [Instalando a CLI do {{site.data.keyword.cloud_notm}} ](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli).
   
   Se a CLI estiver instalada, continue com a próxima etapa.
    
2. Efetue login no {{site.data.keyword.cloud_notm}}. 

    Execute o comando [ibmcloud login](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_login) para efetuar login no {{site.data.keyword.cloud_notm}} e, em seguida, execute o comando [ibmcloud target](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_target) para configurar a organização e o espaço nos quais você deseja provisionar o serviço {{site.data.keyword.cloudaccesstrailshort}}.
	
3. Execute o comando `ibmcloud service create` para provisionar uma instância.

    ```
	  serviço ibmcloud create service_name service_plan service_instance_name
    ```
	  {: codeblock}
	
	  Em que
	
	  * service_name é o nome do serviço, isto é, **accessTrail**.

	  * service_plan é o nome do plano de serviço. Para obter uma lista de planos, veja [Planos de serviço](/docs/services/cloud-activity-tracker/how-to?topic=cloud-activity-tracker-change_plan#change_plan).

	  * service_instance_name é o nome que você deseja usar para a nova instância de serviço criada.

	  Por exemplo, para criar uma instância do serviço {{site.data.keyword.cloudaccesstrailshort}} com o plano padrão, execute o comando a seguir:
	
	  ```
	  ibmcloud service create accessTrail free my_activitytracker_svc
	  ```
	  {: codeblock}
	
4. Verifique se o serviço foi criado com sucesso. Execute o seguinte comando:

  ```	
	ibmcloud service list
	```
	{: codeblock}
	
	A saída da execução do comando é semelhante ao seguinte:
	
	```
    Getting services in org MyOrg / space MySpace as xxx@yyy.com...
    OK
    
    name                           service                  plan                   bound apps              last operation
    my_activitytracker_svc         accessTrail             free                                            create succeeded
	```
	{: screen}

	





---

copyright:
  years: 2016, 2019
lastupdated: "2019-03-06"

keywords: IBM Cloud, Activity Tracker, delete events

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


# Suppression d'événements
{: #deleting_events}

Utilisez la commande *ibmcloud at delete* pour supprimer manuellement des événements stockés dans {{site.data.keyword.cloudaccesstrailshort}}.
{:shortdesc}

Effectuez les opérations suivantes :

## Etape 1 : Connexion à {{site.data.keyword.cloud_notm}}
{: #deleting_events_prereq}

Connectez-vous à {{site.data.keyword.cloud_notm}}. Effectuez les opérations suivantes :

1. Exécutez la commande [ibmcloud login](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_login) pour vous connecter à {{site.data.keyword.cloud_notm}}.
2. Exécutez la commande [ibmcloud target](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_target) pour définir l'organisation et l'espace où mettre le service {{site.data.keyword.cloudaccesstrailshort}} à disposition.

**Remarque :** définissez l'organisation et l'espace où {{site.data.keyword.cloudaccesstrailshort}} est mis à disposition.

## Etape 2 : Identification des événements disponibles
{: #deleting_events_step2}

Utilisez la commande `ibmcloud at status` pour afficher les informations relatives aux événements disponibles dans un domaine d'espace.

* Pour obtenir des informations sur les événements d'un domaine d'espace, exécutez la commande `ibmcloud at status`.
* Pour obtenir des informations sur les événements d'un domaine de compte, exécutez la commande `ibmcloud at status` avec l'option `-a`.

Pour plus d'informations, voir [Affichage des informations sur les événements](/docs/services/cloud-activity-tracker/how-to?topic=cloud-activity-tracker-viewing_event_status#viewing_event_status).
	
  
## Etape 3 : Suppression d'événements
{: #deleting_events_step3}
	
Pour supprimer des événements, exécutez la commande `ibmcloud at delete`.

```
ibmcloud at delete -s YYYY-MM-DD -e YYYY-MM-DD 
```
{: codeblock}
    
où

* *-s* est utilisé pour définir la date de début en UTC (Universal Coordinated Time) : *AAAA-MM-JJ*.
* *-e* est utilisé pour définir la date de fin en UTC (Universal Coordinated Time) : *AAAA-MM-JJ*.

Par exemple, pour supprimer les événements du 10 juin 2017, exécutez la commande suivante :

```
ibmcloud at delete -s 2017-06-10 -e 2017-06-10
```
{: screen}

Vous recevez des informations sur les enregistrements d'événement qui ont été supprimés.











---
title: Задача удаления кластера Azure HDInsight | Документы Майкрософт
ms.custom: ''
ms.date: 02/28/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpdelcltask.f1
- sql11.dts.designer.afpdelcltask.f1
ms.assetid: e298776e-d18a-4393-a8e6-65ee3d555749
author: chugugrace
ms.author: chugu
ms.openlocfilehash: db0a15aaea37c6d18c1d3c2136e0fd0c94eb7506
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667352"
---
# <a name="azure-hdinsight-delete-cluster-task"></a><span data-ttu-id="11a9b-102">Задача удаления кластера Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="11a9b-102">Azure HDInsight Delete Cluster Task</span></span>
<span data-ttu-id="11a9b-103">**Задача удаления кластера Azure HDInsight** позволяет пакету служб SSIS удалить кластер Azure HDInsight в указанной подписке и группе ресурсов Azure.</span><span class="sxs-lookup"><span data-stu-id="11a9b-103">The **Azure HDInsight Delete Cluster Task** enables an SSIS package to delete an Azure HDInsight cluster in the specified Azure subscription and resource group.</span></span>
  
> [!NOTE]
> <span data-ttu-id="11a9b-104">Удаление кластера HDInsight может занимать от 10 до 20 минут.</span><span class="sxs-lookup"><span data-stu-id="11a9b-104">Deleting an HDInsight cluster may take 10~20 minutes.</span></span>  
  
<span data-ttu-id="11a9b-105">Чтобы добавить **задачу удаления кластера Azure HDInsight**, перетащите ее в конструкторе служб SSIS и дважды щелкните или щелкните правой кнопкой мыши и выберите **Изменить** , чтобы вызвать диалоговое окно **Редактор задач удаления кластера Azure HDInsight** .</span><span class="sxs-lookup"><span data-stu-id="11a9b-105">To add an **Azure HDInsight Delete Cluster Task**, drag-drop it to the SSIS Designer, and double-click or right-click and click **Edit** to see the following **Azure HDInsight Delete Cluster Task Editor** dialog box.</span></span>  
  
<span data-ttu-id="11a9b-106">Следующая таблица содержит описание полей этого диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="11a9b-106">The following table provides a description for the fields in the dialog box.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="11a9b-107">**Поле**</span><span class="sxs-lookup"><span data-stu-id="11a9b-107">**Field**</span></span>|<span data-ttu-id="11a9b-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="11a9b-108">**Description**</span></span>|  
|<span data-ttu-id="11a9b-109">AzureResourceManagerConnection</span><span class="sxs-lookup"><span data-stu-id="11a9b-109">AzureResourceManagerConnection</span></span>|<span data-ttu-id="11a9b-110">Выберите существующий или создайте новый диспетчер подключений Azure Resource Manager, который будет использоваться для удаления кластера HDInsight.</span><span class="sxs-lookup"><span data-stu-id="11a9b-110">Select an existing Azure Resource Manager Connection Manager or create a new one that will be used to delete the HDInsight cluster.</span></span>|
|<span data-ttu-id="11a9b-111">SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="11a9b-111">SubscriptionId</span></span>|<span data-ttu-id="11a9b-112">Укажите идентификатор подписки, в которую входит кластер HDInsight.</span><span class="sxs-lookup"><span data-stu-id="11a9b-112">Specify the ID of the subscription the HDInsight cluster is in.</span></span>|
|<span data-ttu-id="11a9b-113">ResourceGroup</span><span class="sxs-lookup"><span data-stu-id="11a9b-113">ResourceGroup</span></span>|<span data-ttu-id="11a9b-114">Укажите идентификатор группы ресурсов Azure, в которую входит кластер HDInsight.</span><span class="sxs-lookup"><span data-stu-id="11a9b-114">Specify the Azure resource group the HDInsight cluster is in.</span></span>|
|<span data-ttu-id="11a9b-115">ClusterName</span><span class="sxs-lookup"><span data-stu-id="11a9b-115">ClusterName</span></span>|<span data-ttu-id="11a9b-116">Укажите имя кластера для удаления.</span><span class="sxs-lookup"><span data-stu-id="11a9b-116">Specify the name of the cluster to be deleted.</span></span>|  
|<span data-ttu-id="11a9b-117">FailIfNotExists</span><span class="sxs-lookup"><span data-stu-id="11a9b-117">FailIfNotExists</span></span>|<span data-ttu-id="11a9b-118">Укажите, следует ли завершать задачу сбоем, если кластер не существует.</span><span class="sxs-lookup"><span data-stu-id="11a9b-118">Specify whether the task should fail if the cluster does not exist.</span></span>|

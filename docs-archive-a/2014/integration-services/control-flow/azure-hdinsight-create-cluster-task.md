---
title: Задача создания кластера Azure HDInsight | Документы Майкрософт
ms.custom: ''
ms.date: 02/28/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpcreatecltask.f1
- sql11.dts.designer.afpcreatecltask.f1
ms.assetid: a8ec413a-38d3-45df-887e-6f5f4d9f8465
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e4029e3a01cbcfe04be5f2879a9b60866bfc867a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729710"
---
# <a name="azure-hdinsight-create-cluster-task"></a><span data-ttu-id="cbb2c-102">Задача создания кластера Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="cbb2c-102">Azure HDInsight Create Cluster Task</span></span>
<span data-ttu-id="cbb2c-103">**Задача создания кластера Azure HDInsight** позволяет пакету служб SSIS создать кластер Azure HDInsight в указанной подписке и группе ресурсов Azure.</span><span class="sxs-lookup"><span data-stu-id="cbb2c-103">The **Azure HDInsight Create Cluster Task** enables an SSIS package to create an Azure HDInsight cluster in the specified Azure subscription and resource group.</span></span>
  
> [!NOTE]  
> - <span data-ttu-id="cbb2c-104">Создание кластера HDInsight может занимать от 10 до 20 минут.</span><span class="sxs-lookup"><span data-stu-id="cbb2c-104">Creating a new HDInsight cluster may take 10~20 minutes.</span></span>  
> - <span data-ttu-id="cbb2c-105">Создание кластера Azure HDInsight и управление им сопряжено с определенными затратами.</span><span class="sxs-lookup"><span data-stu-id="cbb2c-105">There is a cost associated with creating and running an Azure HDInsight cluster.</span></span> <span data-ttu-id="cbb2c-106">Дополнительные сведения см. в статье [Цены на HDInsight](https://azure.microsoft.com/pricing/details/hdinsight/).</span><span class="sxs-lookup"><span data-stu-id="cbb2c-106">See [HDInsight Pricing](https://azure.microsoft.com/pricing/details/hdinsight/) for details.</span></span>  
  
<span data-ttu-id="cbb2c-107">Чтобы добавить **задачу создания кластера Azure HDInsight**, перетащите ее в конструктор служб SSIS и дважды щелкните или щелкните правой кнопкой мыши и выберите пункт **Изменить** , чтобы вызвать диалоговое окно **Azure HDInsight Create Cluster Task Editor** (Редактор задач создания кластера Azure HDInsight).</span><span class="sxs-lookup"><span data-stu-id="cbb2c-107">To add an **Azure HDInsight Create Cluster Task**, drag-drop it to the SSIS Designer, and double-click or right-click and click **Edit** to see the following **Azure HDInsight Create Cluster Task Editor** dialog box.</span></span>  
  
<span data-ttu-id="cbb2c-108">Следующая таблица содержит описание полей этого диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="cbb2c-108">The following table provides a description of the fields in this dialog box.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cbb2c-109">**Поле**</span><span class="sxs-lookup"><span data-stu-id="cbb2c-109">**Field**</span></span>|<span data-ttu-id="cbb2c-110">**Описание**</span><span class="sxs-lookup"><span data-stu-id="cbb2c-110">**Description**</span></span>|  
|<span data-ttu-id="cbb2c-111">AzureResourceManagerConnection</span><span class="sxs-lookup"><span data-stu-id="cbb2c-111">AzureResourceManagerConnection</span></span>|<span data-ttu-id="cbb2c-112">Выберите существующий или создайте новый диспетчер подключений Azure Resource Manager, который будет использоваться для создания кластера HDInsight.</span><span class="sxs-lookup"><span data-stu-id="cbb2c-112">Select an existing Azure Resource Manager Connection Manager or create a new one that will be used to create the HDInsight cluster.</span></span>|  
|<span data-ttu-id="cbb2c-113">AzureStorageConnection</span><span class="sxs-lookup"><span data-stu-id="cbb2c-113">AzureStorageConnection</span></span>|<span data-ttu-id="cbb2c-114">Выберите существующий диспетчер подключений службы хранилища Azure или создайте диспетчер подключений, который ссылается на учетную запись хранения Azure, которая будет связана с кластером HDInsight.</span><span class="sxs-lookup"><span data-stu-id="cbb2c-114">Select an existing Azure Storage Connection Manager or create a new one that refers to an Azure Storage Account that will be associated with the HDInsight cluster.</span></span>|
|<span data-ttu-id="cbb2c-115">SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="cbb2c-115">SubscriptionId</span></span>|<span data-ttu-id="cbb2c-116">Укажите идентификатор подписки, где будет создан кластер HDInsight.</span><span class="sxs-lookup"><span data-stu-id="cbb2c-116">Specify the ID of the subscription the HDInsight cluster will be created in.</span></span>|
|<span data-ttu-id="cbb2c-117">ResourceGroup</span><span class="sxs-lookup"><span data-stu-id="cbb2c-117">ResourceGroup</span></span>|<span data-ttu-id="cbb2c-118">Укажите группу ресурсов Azure, где будет создан кластер HDInsight.</span><span class="sxs-lookup"><span data-stu-id="cbb2c-118">Specify the Azure resource group the HDInsight cluster will be created in.</span></span>|
|<span data-ttu-id="cbb2c-119">Расположение</span><span class="sxs-lookup"><span data-stu-id="cbb2c-119">Location</span></span>|<span data-ttu-id="cbb2c-120">Определите расположение кластера HDInsight.</span><span class="sxs-lookup"><span data-stu-id="cbb2c-120">Specify the location of the HDInsight cluster.</span></span> <span data-ttu-id="cbb2c-121">Кластер нужно создавать в том же расположении, где находится указанная учетная запись службы хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="cbb2c-121">The cluster must be created in the same location as the Azure Storage Account specified.</span></span>|  
|<span data-ttu-id="cbb2c-122">ClusterName</span><span class="sxs-lookup"><span data-stu-id="cbb2c-122">ClusterName</span></span>|<span data-ttu-id="cbb2c-123">Укажите имя для создаваемого кластера HDInsight.</span><span class="sxs-lookup"><span data-stu-id="cbb2c-123">Specify a name for the HDInsight cluster to be created.</span></span>|  
|<span data-ttu-id="cbb2c-124">clusterSize (размер кластера)</span><span class="sxs-lookup"><span data-stu-id="cbb2c-124">ClusterSize</span></span>|<span data-ttu-id="cbb2c-125">Укажите число узлов, которые нужно создать в кластере.</span><span class="sxs-lookup"><span data-stu-id="cbb2c-125">Specify the number of nodes to create in the cluster.</span></span>|  
|<span data-ttu-id="cbb2c-126">BlobContainer</span><span class="sxs-lookup"><span data-stu-id="cbb2c-126">BlobContainer</span></span>|<span data-ttu-id="cbb2c-127">Укажите имя контейнера хранилища по умолчанию, связываемого с кластером HDInsight.</span><span class="sxs-lookup"><span data-stu-id="cbb2c-127">Specify the name of the default storage container to be associated with the HDInsight cluster.</span></span>|  
|<span data-ttu-id="cbb2c-128">UserName</span><span class="sxs-lookup"><span data-stu-id="cbb2c-128">UserName</span></span>|<span data-ttu-id="cbb2c-129">Укажите имя пользователя, используемое для подключения к кластеру HDInsight.</span><span class="sxs-lookup"><span data-stu-id="cbb2c-129">Specify the user name to be used for connecting to the HDInsight cluster.</span></span>|  
|<span data-ttu-id="cbb2c-130">Пароль</span><span class="sxs-lookup"><span data-stu-id="cbb2c-130">Password</span></span>|<span data-ttu-id="cbb2c-131">Укажите пароль, используемый для подключения к кластеру HDInsight.</span><span class="sxs-lookup"><span data-stu-id="cbb2c-131">Specify the password to be used for connecting to the HDInsight cluster.</span></span>|
|<span data-ttu-id="cbb2c-132">SshUserName</span><span class="sxs-lookup"><span data-stu-id="cbb2c-132">SshUserName</span></span>|<span data-ttu-id="cbb2c-133">Укажите имя пользователя, используемое для удаленного доступа к кластеру HDInsight с помощью SSH.</span><span class="sxs-lookup"><span data-stu-id="cbb2c-133">Specify the user name used to remotely access the HDInsight cluster using SSH.</span></span>|
|<span data-ttu-id="cbb2c-134">SshPassword</span><span class="sxs-lookup"><span data-stu-id="cbb2c-134">SshPassword</span></span>|<span data-ttu-id="cbb2c-135">Укажите пароль, используемый для удаленного доступа к кластеру HDInsight с помощью SSH.</span><span class="sxs-lookup"><span data-stu-id="cbb2c-135">Specify the password used to remotely access the HDInsight cluster using SSH.</span></span>|
|<span data-ttu-id="cbb2c-136">FailIfExists</span><span class="sxs-lookup"><span data-stu-id="cbb2c-136">FailIfExists</span></span>|<span data-ttu-id="cbb2c-137">Укажите, следует ли завершать задачу сбоем, если кластер уже существует.</span><span class="sxs-lookup"><span data-stu-id="cbb2c-137">Specify whether the task should fail if the cluster already exists.</span></span>|  
  
> [!NOTE]  
> <span data-ttu-id="cbb2c-138">Расположения кластера HDInsight и учетной записи службы хранилища Azure должны совпадать.</span><span class="sxs-lookup"><span data-stu-id="cbb2c-138">The locations of the HDInsight cluster and the Azure Storage Account must be the same.</span></span>

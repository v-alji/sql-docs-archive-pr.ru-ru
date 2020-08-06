---
title: Пакет дополнительных компонентов Azure | Документация Майкрософт
ms.custom: ''
ms.date: 08/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL11.SSIS.AZURE.F1
- SQL12.SSIS.AZURE.F1
ms.assetid: 31de555f-ae62-4f2f-a6a6-77fea1fa8189
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8bca2b4d3ce91f6010fbe01da836efd8a67ca6bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728654"
---
# <a name="azure-feature-pack"></a><span data-ttu-id="4eed3-102">Пакет дополнительных компонентов Azure</span><span class="sxs-lookup"><span data-stu-id="4eed3-102">Azure Feature Pack</span></span>
<span data-ttu-id="4eed3-103">Пакет дополнительных компонентов Azure для служб SQL Server Integration Services (SSIS) — это дополнение, которое предоставляет перечисленные на этой странице компоненты для подключения служб SSIS к Azure, передачи данных между Azure и локальными источниками данных и обработки данных, хранящихся в Azure.</span><span class="sxs-lookup"><span data-stu-id="4eed3-103">SQL Server Integration Services (SSIS) Feature Pack for Azure is an extension that provides the components listed on this page for SSIS to connect to Azure services, transfer data between Azure and on-premises data sources, and process data stored in Azure.</span></span>

## <a name="components-in-the-feature-pack"></a><span data-ttu-id="4eed3-104">Компоненты в составе пакета дополнительных компонентов</span><span class="sxs-lookup"><span data-stu-id="4eed3-104">Components in the Feature Pack</span></span>
  
-   <span data-ttu-id="4eed3-105">Диспетчеры соединений</span><span class="sxs-lookup"><span data-stu-id="4eed3-105">Connection Managers</span></span>  
  
    -   [<span data-ttu-id="4eed3-106">Диспетчер подключений службы хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="4eed3-106">Azure Storage Connection Manager</span></span>](connection-manager/azure-storage-connection-manager.md)  
  
    -   [<span data-ttu-id="4eed3-107">Диспетчер подключений подписки Azure</span><span class="sxs-lookup"><span data-stu-id="4eed3-107">Azure Subscription Connection Manager</span></span>](connection-manager/azure-subscription-connection-manager.md)  
    
    -   [<span data-ttu-id="4eed3-108">Диспетчер подключений Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="4eed3-108">Azure Data Lake Store Connection Manager</span></span>](../../2014/integration-services/azure-data-lake-store-connection-manager.md)
    
    -   [<span data-ttu-id="4eed3-109">Диспетчер подключений Azure Resource Manager</span><span class="sxs-lookup"><span data-stu-id="4eed3-109">Azure Resource Manager Connection Manager</span></span>](../../2014/integration-services/azure-resource-manager-connection-manager.md)
    
    -   [<span data-ttu-id="4eed3-110">Диспетчер подключений Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="4eed3-110">Azure HDInsight Connection Manager</span></span>](../../2014/integration-services/azure-hdinsight-connection-manager.md)
  
-   <span data-ttu-id="4eed3-111">Задания</span><span class="sxs-lookup"><span data-stu-id="4eed3-111">Tasks</span></span>  
  
    -   [<span data-ttu-id="4eed3-112">Задача передачи больших двоичных объектов Azure</span><span class="sxs-lookup"><span data-stu-id="4eed3-112">Azure Blob Upload Task</span></span>](control-flow/azure-blob-upload-task.md)  
  
    -   [<span data-ttu-id="4eed3-113">Задача скачивания BLOB-объектов Azure</span><span class="sxs-lookup"><span data-stu-id="4eed3-113">Azure Blob Download Task</span></span>](control-flow/azure-blob-download-task.md)  
  
    -   [<span data-ttu-id="4eed3-114">Задача Hive для Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="4eed3-114">Azure HDInsight Hive Task</span></span>](control-flow/azure-hdinsight-hive-task.md)  
  
    -   <span data-ttu-id="4eed3-115">[Задача Pig для Azure HDInsight](https://msdn.microsoft.com/library/mt146781(v=sql.120).aspx)</span><span class="sxs-lookup"><span data-stu-id="4eed3-115">[Azure HDInsight Pig Task](https://msdn.microsoft.com/library/mt146781(v=sql.120).aspx)</span></span>
  
    -   [<span data-ttu-id="4eed3-116">Задача создания кластера Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="4eed3-116">Azure HDInsight Create Cluster Task</span></span>](control-flow/azure-hdinsight-create-cluster-task.md)  
  
    -   [<span data-ttu-id="4eed3-117">Задача удаления кластера Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="4eed3-117">Azure HDInsight Delete Cluster Task</span></span>](control-flow/azure-hdinsight-delete-cluster-task.md)
    
    -   [<span data-ttu-id="4eed3-118">Задача отправки в хранилище данных Azure SQL</span><span class="sxs-lookup"><span data-stu-id="4eed3-118">Azure SQL DW Upload Task</span></span>](../../2014/integration-services/azure-sql-dw-upload-task.md)    
    
    -   [<span data-ttu-id="4eed3-119">Задача «Файловая система» для Azure Data Lake</span><span class="sxs-lookup"><span data-stu-id="4eed3-119">Azure Data Lake Store File System Task</span></span>](control-flow/file-system-task.md)    
  
-   <span data-ttu-id="4eed3-120">Компоненты потока данных</span><span class="sxs-lookup"><span data-stu-id="4eed3-120">Data Flow Components</span></span>  
  
    -   <span data-ttu-id="4eed3-121">[Компонент Azure Blob Source](https://msdn.microsoft.com/library/mt146775(v=sql.120).aspx)</span><span class="sxs-lookup"><span data-stu-id="4eed3-121">[Azure Blob Source](https://msdn.microsoft.com/library/mt146775(v=sql.120).aspx)</span></span>  
  
    -   [<span data-ttu-id="4eed3-122">Назначение больших двоичных объектов Azure</span><span class="sxs-lookup"><span data-stu-id="4eed3-122">Azure Blob Destination</span></span>](data-flow/azure-blob-destination.md)  
    
    -   [<span data-ttu-id="4eed3-123">Источник Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="4eed3-123">Azure Data Lake Store Source</span></span>](../../2014/integration-services/azure-data-lake-store-source.md)
    
    -   [<span data-ttu-id="4eed3-124">Цель Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="4eed3-124">Azure Data Lake Store Destination</span></span>](../../2014/integration-services/azure-data-lake-store-destination.md)
  
-   <span data-ttu-id="4eed3-125">Перечислитель BLOB-объектов Azure & перечислитель файлов ADLS.</span><span class="sxs-lookup"><span data-stu-id="4eed3-125">Azure Blob Enumerator & ADLS File Enumerator.</span></span> <span data-ttu-id="4eed3-126">См. раздел [контейнер «цикл по каждому](control-flow/foreach-loop-container.md)элементу».</span><span class="sxs-lookup"><span data-stu-id="4eed3-126">See [Foreach Loop Container](control-flow/foreach-loop-container.md).</span></span>  
  
 
## <a name="download-the-feature-pack"></a><span data-ttu-id="4eed3-127">Скачивание пакета дополнительных компонентов</span><span class="sxs-lookup"><span data-stu-id="4eed3-127">Download the Feature Pack</span></span>  
<span data-ttu-id="4eed3-128">Скачайте пакет дополнительных компонентов SQL Server Integration Services (SSIS) для Azure.</span><span class="sxs-lookup"><span data-stu-id="4eed3-128">Download the SQL Server Integration Services (SSIS) Feature Pack for Azure.</span></span>  
  
-   [<span data-ttu-id="4eed3-129">Пакет дополнительных компонентов служб SQL Server Integration Services 2014 для Azure</span><span class="sxs-lookup"><span data-stu-id="4eed3-129">Microsoft SQL Server 2014 Integration Services Feature Pack for Azure</span></span>](https://www.microsoft.com/download/details.aspx?id=47366)  

## <a name="prerequisites"></a><span data-ttu-id="4eed3-130">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="4eed3-130">Prerequisites</span></span>  
<span data-ttu-id="4eed3-131">Перед установкой этого пакета необходимо установить следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="4eed3-131">You must install the following prerequisites before installing this feature pack.</span></span>  
  
-   <span data-ttu-id="4eed3-132">SQL Server Integration Services</span><span class="sxs-lookup"><span data-stu-id="4eed3-132">SQL Server Integration Services</span></span>  
-   <span data-ttu-id="4eed3-133">.NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="4eed3-133">.Net Framework 4.5</span></span>  
  
## <a name="scenarios"></a><span data-ttu-id="4eed3-134">Сценарии</span><span class="sxs-lookup"><span data-stu-id="4eed3-134">Scenarios</span></span>  
  
### <a name="big-data-processing"></a><span data-ttu-id="4eed3-135">Обработка больших данных</span><span class="sxs-lookup"><span data-stu-id="4eed3-135">Big Data Processing</span></span>  
 <span data-ttu-id="4eed3-136">Используйте соединитель Azure для выполнения следующих задач по обработке больших данных:</span><span class="sxs-lookup"><span data-stu-id="4eed3-136">Use Azure Connector to complete following big data processing work:</span></span>  
  
1.  <span data-ttu-id="4eed3-137">Передача входных данных в хранилище больших двоичных объектов Azure с помощью задачи передачи больших двоичных объектов Azure.</span><span class="sxs-lookup"><span data-stu-id="4eed3-137">Use the Azure Blob Upload Task to upload input data to Azure Blob Storage.</span></span>  
  
2.  <span data-ttu-id="4eed3-138">Создание кластера Azure HDInsight с помощью задачи создания кластера Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="4eed3-138">Use the Azure HDInsight Create Cluster Task to create an Azure HDInsight cluster.</span></span> <span data-ttu-id="4eed3-139">Если вы хотите использовать собственный кластер, этот шаг является необязательным.</span><span class="sxs-lookup"><span data-stu-id="4eed3-139">This step is optional if you want to use your own cluster.</span></span>  
  
3.  <span data-ttu-id="4eed3-140">Запуск задания Pig или Hive в кластере Azure HDInsight с помощью задачи по запуску задания Pig в Azure HDInsight или задачи по запуску задания Hive в Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="4eed3-140">Use the Azure HDInsight Hive Task or Azure HDInsight Pig Task to invoke a Pig or Hive job on the Azure HDInsight cluster.</span></span>  
  
4.  <span data-ttu-id="4eed3-141">Удаление кластера Azure HDInsight после использования (если вы создавали кластер HDInsight по требованию на шаге 2) с помощью задачи удаления кластера Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="4eed3-141">Use the Azure HDInsight Delete Cluster Task to delete the HDInsight Cluster after use if you have created an on-demand HDInsight cluster in step #2.</span></span>  
  
5.  <span data-ttu-id="4eed3-142">Скачивание выходных данных из хранилища больших двоичных объектов Azure с помощью задачи скачивания больших двоичных объектов Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="4eed3-142">Use the Azure HDInsight Blob Download Task to download the Pig/Hive output data from the Azure Blob Storage.</span></span>  
  
 <span data-ttu-id="4eed3-143">![SSIS-AzureConnector-BigDataScenario](media/ssis-azureconnector-bigdatascenario.png "SSIS-AzureConnector-BigDataScenario")</span><span class="sxs-lookup"><span data-stu-id="4eed3-143">![SSIS-AzureConnector-BigDataScenario](media/ssis-azureconnector-bigdatascenario.png "SSIS-AzureConnector-BigDataScenario")</span></span>  
  
### <a name="cloud-data-archiving"></a><span data-ttu-id="4eed3-144">Архивация данных облака</span><span class="sxs-lookup"><span data-stu-id="4eed3-144">Cloud Data Archiving</span></span>  
 <span data-ttu-id="4eed3-145">Используйте назначение больших двоичных объектов Azure в пакете служб SSIS для записи выходных данных в хранилище больших двоичных объектов Azure или используйте источник больших двоичных объектов Azure для чтения данных из хранилища больших двоичных объектов Azure.</span><span class="sxs-lookup"><span data-stu-id="4eed3-145">Use the Azure Blob Destination in an SSIS package to write output data to an Azure Blob Storage, or use the Azure Blob Source to read data from an Azure Blob Storage.</span></span>  
  
 <span data-ttu-id="4eed3-146">![SSIS-AzureConnector-CloudArchive-1](media/ssis-azureconnector-cloudarchive-1.png "SSIS-AzureConnector-CloudArchive-1")</span><span class="sxs-lookup"><span data-stu-id="4eed3-146">![SSIS-AzureConnector-CloudArchive-1](media/ssis-azureconnector-cloudarchive-1.png "SSIS-AzureConnector-CloudArchive-1")</span></span>  
  
 <span data-ttu-id="4eed3-147">![SSIS-AzureConnector-CloudArchive-2](media/ssis-azureconnector-cloudarchive-2.png "SSIS-AzureConnector-CloudArchive-2")</span><span class="sxs-lookup"><span data-stu-id="4eed3-147">![SSIS-AzureConnector-CloudArchive-2](media/ssis-azureconnector-cloudarchive-2.png "SSIS-AzureConnector-CloudArchive-2")</span></span>  
  
 <span data-ttu-id="4eed3-148">Используйте контейнер цикла Foreach с перечислителем больших двоичных объектов Azure для обработки данных в нескольких файлах больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="4eed3-148">And use the Foreach Loop Container with Azure Blob Enumerator to process data in multiple bob files.</span></span>  
  
 <span data-ttu-id="4eed3-149">![SSIS-AzureConnector-CloudArchive-3](media/ssis-azureconnector-cloudarchive-3.png "SSIS-AzureConnector-CloudArchive-3")</span><span class="sxs-lookup"><span data-stu-id="4eed3-149">![SSIS-AzureConnector-CloudArchive-3](media/ssis-azureconnector-cloudarchive-3.png "SSIS-AzureConnector-CloudArchive-3")</span></span>  
  
  

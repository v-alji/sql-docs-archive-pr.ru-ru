---
title: Места обработки и хранения (мастер секционирования) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitionwizard.specifyprocessingandstorage.f1
ms.assetid: dda2dc57-923d-4db9-93a7-38e95770f3df
author: minewiskan
ms.author: owend
ms.openlocfilehash: 00ab88bac184f57bd2b4dcfdb8d00909a85ece4f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750251"
---
# <a name="processing-and-storage-locations-partition-wizard"></a><span data-ttu-id="54dff-102">Места обработки и хранения (мастер секционирования)</span><span class="sxs-lookup"><span data-stu-id="54dff-102">Processing and Storage Locations (Partition Wizard)</span></span>
  <span data-ttu-id="54dff-103">На странице **Места обработки и хранения** можно определить экземпляр служб [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] куба, владеющий секцией, а также экземпляр служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , где хранятся данные секции.</span><span class="sxs-lookup"><span data-stu-id="54dff-103">Use the **Processing and Storage Locations** page to specify the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance of the cube that owns the partition, as well as the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance that stores the data for the partition.</span></span> <span data-ttu-id="54dff-104">Чтобы определить секцию как удаленную, укажите либо удаленный экземпляр служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , либо место хранения, отличающееся от места хранения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="54dff-104">You can define a partition as a remote partition by specifying either a remote [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance or a storage location other than the default storage location.</span></span> <span data-ttu-id="54dff-105">Дополнительные сведения об удаленных секциях см. в разделе [Удаленные секции](multidimensional-models-olap-logical-cube-objects/partitions-remote-partitions.md).</span><span class="sxs-lookup"><span data-stu-id="54dff-105">For more information about remote partitions, see [Remote Partitions](multidimensional-models-olap-logical-cube-objects/partitions-remote-partitions.md).</span></span>  
  
## <a name="processing-location-options"></a><span data-ttu-id="54dff-106">Параметры места обработки</span><span class="sxs-lookup"><span data-stu-id="54dff-106">Processing location Options</span></span>  
 <span data-ttu-id="54dff-107">**Текущий экземпляр сервера**</span><span class="sxs-lookup"><span data-stu-id="54dff-107">**Current server instance**</span></span>  
 <span data-ttu-id="54dff-108">Назначает текущий экземпляр служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ответственным за обработку секции.</span><span class="sxs-lookup"><span data-stu-id="54dff-108">Makes the current [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance responsible for processing the partition.</span></span>  
  
 <span data-ttu-id="54dff-109">**Удаленный источник данных служб Analysis Services**</span><span class="sxs-lookup"><span data-stu-id="54dff-109">**Remote Analysis Services data source**</span></span>  
 <span data-ttu-id="54dff-110">Назначает удаленный экземпляр служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ответственным за обработку этой секции.</span><span class="sxs-lookup"><span data-stu-id="54dff-110">Makes a remote [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance responsible for processing this partition.</span></span>  
  
 <span data-ttu-id="54dff-111">Из раскрывающегося списка выберите источник данных, являющийся удаленным экземпляром служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , который будет отвечать за обработку секции.</span><span class="sxs-lookup"><span data-stu-id="54dff-111">From the dropdown list, select the data source representing the remote [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance that will be responsible for processing the partition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="54dff-112">Если выбран источник данных, в котором значение свойства строки соединения `Initial Catalog` не соответствует допустимой базе данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], либо если база данных, указанная в свойстве строки соединения `Initial Catalog`, не поддерживает удаленные секции (то есть значение свойства `MasterDatasourceID` для указанной базы данных не является допустимым), возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="54dff-112">An error occurs if you select a data source in which the `Initial Catalog` connection string property is not set to a valid [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, or if the database specified in the `Initial Catalog` connection string property does not support remote partitions (in other words, the `MasterDatasourceID` property of the specified database is not set to a valid value).</span></span>  
  
 <span data-ttu-id="54dff-113">**Создать**</span><span class="sxs-lookup"><span data-stu-id="54dff-113">**New**</span></span>  
 <span data-ttu-id="54dff-114">Создание нового источника данных, представляющего собой удаленный экземпляр служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , ответственный за обработку секции.</span><span class="sxs-lookup"><span data-stu-id="54dff-114">Creates a new data source representing the remote [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance responsible for processing the partition.</span></span>  
  
## <a name="storage-location-options"></a><span data-ttu-id="54dff-115">Параметры места хранения</span><span class="sxs-lookup"><span data-stu-id="54dff-115">Storage location Options</span></span>  
 <span data-ttu-id="54dff-116">**Размещение сервера по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="54dff-116">**Default server location**</span></span>  
 <span data-ttu-id="54dff-117">Папка данных текущего экземпляра служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] становится местом хранения статистических данных и данных индексирования для секции.</span><span class="sxs-lookup"><span data-stu-id="54dff-117">Makes the data folder of the current [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance the storage location of the aggregation and indexing data for the partition.</span></span>  
  
 <span data-ttu-id="54dff-118">**Указанная папка**</span><span class="sxs-lookup"><span data-stu-id="54dff-118">**Specified folder**</span></span>  
 <span data-ttu-id="54dff-119">Задает место хранения статистических данных и данных индексирования для секции.</span><span class="sxs-lookup"><span data-stu-id="54dff-119">Specifies the storage location of the aggregation and indexing data for the partition.</span></span>  
  
 <span data-ttu-id="54dff-120">**...**</span><span class="sxs-lookup"><span data-stu-id="54dff-120">**...**</span></span>  
 <span data-ttu-id="54dff-121">Выводит диалоговое окно **Выбор удаленной папки** , в котором можно выбрать папку для поля **Указанная папка**.</span><span class="sxs-lookup"><span data-stu-id="54dff-121">Displays the **Browse for Remote Folder** dialog box in which you can select a folder for **Specified folder**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54dff-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="54dff-122">See Also</span></span>  
 <span data-ttu-id="54dff-123">[Справка F1 мастера секционирования &#40;Analysis Services многомерных данных&#41;](partition-wizard-f1-help-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="54dff-123">[Partition Wizard F1 Help &#40;Analysis Services - Multidimensional Data&#41;](partition-wizard-f1-help-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="54dff-124">[Секции &#40;Analysis Services многомерных данных&#41;](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="54dff-124">[Partitions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="54dff-125">Диалоговое окно «Выбор удаленной папки» &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="54dff-125">Browse for Remote Folder Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](browse-for-remote-folder-dialog-box-analysis-services-multidimensional-data.md)  
  
  

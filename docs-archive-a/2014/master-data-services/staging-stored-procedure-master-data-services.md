---
title: Промежуточная хранимая процедура (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 6a613106-9f87-4caf-a23a-a726fc6561c5
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9259352350a099db5d9b18411ad4da06dfb19819
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668964"
---
# <a name="staging-stored-procedure-master-data-services"></a><span data-ttu-id="82377-102">Промежуточная хранимая процедура (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="82377-102">Staging Stored Procedure (Master Data Services)</span></span>
  <span data-ttu-id="82377-103">При запуске промежуточного процесса из [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]используется одна из трех хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="82377-103">When initiating the staging process from [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], you use one of three stored procedures.</span></span>  
  
-   <span data-ttu-id="82377-104">stg.udp_name_Leaf</span><span class="sxs-lookup"><span data-stu-id="82377-104">stg.udp_name_Leaf</span></span>  
  
-   <span data-ttu-id="82377-105">stg.udp_name_Consolidated</span><span class="sxs-lookup"><span data-stu-id="82377-105">stg.udp_name_Consolidated</span></span>  
  
-   <span data-ttu-id="82377-106">stg.udp_name_Relationship</span><span class="sxs-lookup"><span data-stu-id="82377-106">stg.udp_name_Relationship</span></span>  
  
 <span data-ttu-id="82377-107">Где имя — это имя промежуточной таблицы, определенной при создании сущности.</span><span class="sxs-lookup"><span data-stu-id="82377-107">Where name is the name of the staging table that was specified when the entity was created.</span></span>  
  
## <a name="staging-process-stored-procedure-parameters"></a><span data-ttu-id="82377-108">Параметры хранимой процедуры промежуточного процесса</span><span class="sxs-lookup"><span data-stu-id="82377-108">Staging Process Stored Procedure Parameters</span></span>  
 <span data-ttu-id="82377-109">В следующей таблице приведены параметры этих хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="82377-109">The following table lists the parameters of these stored procedures.</span></span>  
  
|<span data-ttu-id="82377-110">Параметр</span><span class="sxs-lookup"><span data-stu-id="82377-110">Parameter</span></span>|<span data-ttu-id="82377-111">Описание</span><span class="sxs-lookup"><span data-stu-id="82377-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="82377-112">**VersionName**</span><span class="sxs-lookup"><span data-stu-id="82377-112">**VersionName**</span></span><br /><br /> <span data-ttu-id="82377-113">Обязательный</span><span class="sxs-lookup"><span data-stu-id="82377-113">Required</span></span>|<span data-ttu-id="82377-114">Имя версии.</span><span class="sxs-lookup"><span data-stu-id="82377-114">The name of the version.</span></span> <span data-ttu-id="82377-115">С учетом или без учета регистра, в зависимости от параметров сортировки [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="82377-115">This may or may not be case-sensitive, depending on your [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] collation setting.</span></span>|  
|<span data-ttu-id="82377-116">**LogFlag**</span><span class="sxs-lookup"><span data-stu-id="82377-116">**LogFlag**</span></span><br /><br /> <span data-ttu-id="82377-117">Обязательный</span><span class="sxs-lookup"><span data-stu-id="82377-117">Required</span></span>|<span data-ttu-id="82377-118">Определяет, будут ли регистрироваться транзакции в ходе промежуточного процесса.</span><span class="sxs-lookup"><span data-stu-id="82377-118">Determines whether transactions are logged during the staging process.</span></span> <span data-ttu-id="82377-119">Возможны следующие значения:</span><span class="sxs-lookup"><span data-stu-id="82377-119">Possible values are:</span></span><br /><br /> <span data-ttu-id="82377-120">**0**: не регистрировать транзакции.</span><span class="sxs-lookup"><span data-stu-id="82377-120">**0**: Do not log transactions.</span></span><br /><span data-ttu-id="82377-121">**1**: регистрировать транзакции.</span><span class="sxs-lookup"><span data-stu-id="82377-121">**1**: Log transactions.</span></span><br /><br /> <br /><br /> <span data-ttu-id="82377-122">Дополнительные сведения о транзакциях см. в разделе [Транзакции (службы Master Data Services)](transactions-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="82377-122">For more information about transactions, see [Transactions &#40;Master Data Services&#41;](transactions-master-data-services.md).</span></span>|  
|<span data-ttu-id="82377-123">**BatchTag**</span><span class="sxs-lookup"><span data-stu-id="82377-123">**BatchTag**</span></span><br /><br /> <span data-ttu-id="82377-124">Требуется, за исключением веб-службы</span><span class="sxs-lookup"><span data-stu-id="82377-124">Required, except by web service</span></span>|<span data-ttu-id="82377-125">Значение **BatchTag** , как указано в промежуточной таблице.</span><span class="sxs-lookup"><span data-stu-id="82377-125">The **BatchTag** value as specified in the staging table.</span></span>|  
|<span data-ttu-id="82377-126">**Batch_ID**</span><span class="sxs-lookup"><span data-stu-id="82377-126">**Batch_ID**</span></span><br /><br /> <span data-ttu-id="82377-127">Требуется только для веб-службы</span><span class="sxs-lookup"><span data-stu-id="82377-127">Required by web service only</span></span>|<span data-ttu-id="82377-128">Значение **Batch_ID** , как указано в промежуточной таблице.</span><span class="sxs-lookup"><span data-stu-id="82377-128">The **Batch_ID** value as specified in the staging table.</span></span>|  
  
### <a name="staging-process-stored-procedure-example"></a><span data-ttu-id="82377-129">Пример хранимой процедуры промежуточного процесса</span><span class="sxs-lookup"><span data-stu-id="82377-129">Staging Process Stored Procedure Example</span></span>  
 <span data-ttu-id="82377-130">В следующем примере показан запуск промежуточного процесса с помощью хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="82377-130">The following example shows how to start the staging process by using the staging stored procedure.</span></span>  
  
```  
USE [DATABASE_NAME]  
GO  
  
EXEC[stg].[udp_name_Leaf]  
      @VersionName = N'VERSION_1',  
@LogFlag = 1,  
@BatchTag = N'batch1'  
  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="82377-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="82377-131">See Also</span></span>  
 <span data-ttu-id="82377-132">[Master Data Services &#40;хранимой процедуры проверки&#41;](../../2014/master-data-services/validation-stored-procedure-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="82377-132">[Validation Stored Procedure &#40;Master Data Services&#41;](../../2014/master-data-services/validation-stored-procedure-master-data-services.md) </span></span>  
 <span data-ttu-id="82377-133">[Загрузка или обновление элементов в Master Data Services с помощью промежуточного процесса](add-update-and-delete-data-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="82377-133">[Load or Update Members in Master Data Services by Using the Staging Process](add-update-and-delete-data-master-data-services.md) </span></span>  
 [<span data-ttu-id="82377-134">Просмотрите ошибки, возникающие во время промежуточного процесса &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="82377-134">View Errors that Occur During the Staging Process &#40;Master Data Services&#41;</span></span>](view-errors-that-occur-during-staging-master-data-services.md)  
  
  

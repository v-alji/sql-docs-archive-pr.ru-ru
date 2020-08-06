---
title: Выполнение бизнес-логики при синхронизации слиянием | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- custom error resolution [SQL Server replication]
- custom change handling [SQL Server replication]
- errors [SQL Server replication], business logic handlers
- merge replication business logic handlers [SQL Server replication]
- conflict resolution [SQL Server replication], merge replication
- business logic handlers [SQL Server replication]
ms.assetid: 9d4da2ef-c17f-4a31-a1f6-5c3b7ca85f71
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1e082cbbb46ceae712cd39925c28fe89988a3793
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654218"
---
# <a name="execute-business-logic-during-merge-synchronization"></a><span data-ttu-id="d76da-102">Выполнение бизнес-логики при синхронизации слиянием</span><span class="sxs-lookup"><span data-stu-id="d76da-102">Execute Business Logic During Merge Synchronization</span></span>
  <span data-ttu-id="d76da-103">Платформа обработчика бизнес-логики всегда доступна для добавления сборки управляемого кода, который выполняется во время процесса синхронизации слиянием.</span><span class="sxs-lookup"><span data-stu-id="d76da-103">The business logic handler framework allows you to write a managed code assembly that is called during the merge synchronization process.</span></span> <span data-ttu-id="d76da-104">Сборка включает бизнес-логику, которая может учитывать ряд условий во время синхронизации: изменения данных, конфликты и ошибки.</span><span class="sxs-lookup"><span data-stu-id="d76da-104">The assembly includes business logic that can respond to a number of conditions during synchronization: data changes, conflicts, and errors.</span></span> <span data-ttu-id="d76da-105">Платформа обработчика бизнес-логики предоставляет простую программируемую модель; данные, которые процесс слияния предоставляет для вашей сборки, находятся в форме набора данных ADO.NET, поэтому удобнее эффективно использовать знание ADO.NET, чем изучать патентованный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="d76da-105">The business logic handler framework provides a simple programming model, and the data that the merge process provides to your assembly is in the form of an ADO.NET data set, so you can leverage knowledge of ADO.NET rather than learning a proprietary interface.</span></span> <span data-ttu-id="d76da-106">Дополнительные сведения о программируемых обработчиках бизнес-логики см. в следующих источниках:</span><span class="sxs-lookup"><span data-stu-id="d76da-106">For more information on programming business logic handlers, see:</span></span>  
  
-   <span data-ttu-id="d76da-107">Справочник по программным интерфейсам (API): <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport></span><span class="sxs-lookup"><span data-stu-id="d76da-107">The application programming interface (API) reference: <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport></span></span>  
  
-   <span data-ttu-id="d76da-108">Инструкции по реализации обработчика бизнес-логики: [Реализация обработчика бизнес-логики для статьи слияния](../implement-a-business-logic-handler-for-a-merge-article.md)</span><span class="sxs-lookup"><span data-stu-id="d76da-108">Instructions on how to implement a business logic handler: [Implement a Business Logic Handler for a Merge Article](../implement-a-business-logic-handler-for-a-merge-article.md)</span></span>  
  
## <a name="uses-for-business-logic-handlers"></a><span data-ttu-id="d76da-109">Применения обработчиков бизнес-логики</span><span class="sxs-lookup"><span data-stu-id="d76da-109">Uses for Business Logic Handlers</span></span>  
 <span data-ttu-id="d76da-110">Процесс синхронизации слиянием может вызывать обработчики бизнес-логики для выполнения следующих задач:</span><span class="sxs-lookup"><span data-stu-id="d76da-110">The merge synchronization process can invoke business logic handlers to perform:</span></span>  
  
-   <span data-ttu-id="d76da-111">обработка пользовательских изменений;</span><span class="sxs-lookup"><span data-stu-id="d76da-111">Custom change handling</span></span>  
  
-   <span data-ttu-id="d76da-112">устранение пользовательских конфликтов;</span><span class="sxs-lookup"><span data-stu-id="d76da-112">Custom conflict resolution</span></span>  
  
-   <span data-ttu-id="d76da-113">разрешение пользовательских ошибок.</span><span class="sxs-lookup"><span data-stu-id="d76da-113">Custom error resolution</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d76da-114">Указанный обработчик бизнес-логики выполняется для каждой синхронизируемой строки.</span><span class="sxs-lookup"><span data-stu-id="d76da-114">The business logic handler you specify is executed for every row that is synchronized.</span></span> <span data-ttu-id="d76da-115">Сложная логика и вызовы других приложений или сетевых служб могут влиять на производительность.</span><span class="sxs-lookup"><span data-stu-id="d76da-115">Complex logic and calls to other applications or network services can impact performance.</span></span>  
  
### <a name="custom-change-handling"></a><span data-ttu-id="d76da-116">обработка пользовательских изменений;</span><span class="sxs-lookup"><span data-stu-id="d76da-116">Custom Change Handling</span></span>  
 <span data-ttu-id="d76da-117">Обработчик бизнес-логики может вызываться во время обработки бесконфликтных изменений данных и может выполнять одно из трех действий:</span><span class="sxs-lookup"><span data-stu-id="d76da-117">The business logic handler can be invoked during the processing of non-conflicting data changes and can perform one of three actions:</span></span>  
  
-   <span data-ttu-id="d76da-118">Отклонить данные</span><span class="sxs-lookup"><span data-stu-id="d76da-118">Reject the data</span></span>  
  
     <span data-ttu-id="d76da-119">Это применимо для приложений, которые не распространяют изменения на данный подписчик или от него.</span><span class="sxs-lookup"><span data-stu-id="d76da-119">This is useful for applications that do not want changes propagated to or from a given Subscriber.</span></span> <span data-ttu-id="d76da-120">Например, администратор может отфильтровывать вставки, не относящиеся к секции подписчика, или отклонять удаления, выполненные на подписчике.</span><span class="sxs-lookup"><span data-stu-id="d76da-120">For example, an administrator could filter out inserts that do not belong in the Subscriber's partition, or possibly reject deletes performed at a Subscriber.</span></span> <span data-ttu-id="d76da-121">Другой пример: приложение может отклонить заказ, введенный на подписчике, потому что материально-производственные запасы более не доступны.</span><span class="sxs-lookup"><span data-stu-id="d76da-121">As another example, an application could reject an order entered at a Subscriber because the inventory is no longer available.</span></span>  
  
-   <span data-ttu-id="d76da-122">Принять данные</span><span class="sxs-lookup"><span data-stu-id="d76da-122">Accept the data</span></span>  
  
     <span data-ttu-id="d76da-123">Это применимо для приложений, в которых изменения данных, сделанные либо на издателе, либо на подписчике, необходимо просмотреть перед распространением.</span><span class="sxs-lookup"><span data-stu-id="d76da-123">This is useful for applications in which it is necessary to review data changes made at either the Publisher or Subscriber before allowing them to be propagated.</span></span> <span data-ttu-id="d76da-124">Например приложение промежуточного уровня может проверять новые заказы, поступающие из отрасли, и интегрировать их с рабочим процессом в промежуточном процессе обработки.</span><span class="sxs-lookup"><span data-stu-id="d76da-124">For example, a mid-tier application could examine new orders coming in from the field and integrate with a procurement workflow process in the mid-tier.</span></span>  
  
-   <span data-ttu-id="d76da-125">Применить пользовательские данные</span><span class="sxs-lookup"><span data-stu-id="d76da-125">Apply custom data</span></span>  
  
     <span data-ttu-id="d76da-126">Это применимо для приложений, которые нуждаются в переопределении конкретных значений данных или операций.</span><span class="sxs-lookup"><span data-stu-id="d76da-126">This is useful for applications that need to override specific data values or operations.</span></span> <span data-ttu-id="d76da-127">Например приложение может преобразовать строковое удаление в специальное обновление, которое устанавливает для столбца **status** в строке значение «удалено», и затем отслеживает идентификатор клиента, выполняющего удаление.</span><span class="sxs-lookup"><span data-stu-id="d76da-127">For example, an application could transform a row delete into a special update that sets a **status** column in the row to a value of "deleted" and then tracks the identity of the client performing the delete.</span></span> <span data-ttu-id="d76da-128">Это может оказаться удобным для проведения аудита или отслеживания рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="d76da-128">This might be useful for auditing or workflow purposes.</span></span>  
  
### <a name="custom-conflict-resolution"></a><span data-ttu-id="d76da-129">устранение пользовательских конфликтов;</span><span class="sxs-lookup"><span data-stu-id="d76da-129">Custom Conflict Resolution</span></span>  
 <span data-ttu-id="d76da-130">Репликация слиянием обеспечивает обнаружение и разрешение конфликтов, позволяет принять стратегию разрешений по умолчанию или выбрать пользовательское разрешение конфликтов.</span><span class="sxs-lookup"><span data-stu-id="d76da-130">Merge replication provides conflict detection and resolution, allowing you to accept a default resolution strategy or choose custom resolution for conflicts.</span></span> <span data-ttu-id="d76da-131">Дополнительные сведения см. в разделе [Advanced Merge Replication Conflict Detection and Resolution](advanced-merge-replication-conflict-detection-and-resolution.md).</span><span class="sxs-lookup"><span data-stu-id="d76da-131">For more information, see [Advanced Merge Replication Conflict Detection and Resolution](advanced-merge-replication-conflict-detection-and-resolution.md).</span></span> <span data-ttu-id="d76da-132">Обработчик бизнес-логики может вызываться в течение обработки конфликтующих изменений данных и может выполнять одно из двух действий:</span><span class="sxs-lookup"><span data-stu-id="d76da-132">The business logic handler can be invoked during the processing of conflicting data changes and can perform one of two actions:</span></span>  
  
-   <span data-ttu-id="d76da-133">Принять разрешение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="d76da-133">Accept default resolution</span></span>  
  
     <span data-ttu-id="d76da-134">Это действие может использоваться для приложений, нуждающихся в просмотре конфликта, выполнении дополнительных действий и, возможно, записи в журнал сообщения о пользовательском конфликте.</span><span class="sxs-lookup"><span data-stu-id="d76da-134">This is useful for applications that might need to review the conflict, perform additional actions, and possibly log a custom conflict log message.</span></span>  
  
-   <span data-ttu-id="d76da-135">Выполнить пользовательское разрешение</span><span class="sxs-lookup"><span data-stu-id="d76da-135">Perform custom resolution</span></span>  
  
     <span data-ttu-id="d76da-136">Это действие может понадобиться для приложений, которым нужно выбрать значения данных, относящиеся к их бизнес-логике, и обеспечить процесс синхронизации пользовательским набором данных.</span><span class="sxs-lookup"><span data-stu-id="d76da-136">This is useful for applications that might need to select data values that are specific to their business logic and supply the synchronization process with this custom dataset.</span></span> <span data-ttu-id="d76da-137">Например, приложение может предоставлять новую версию предпочтительной строки путем объединения значений из наборов данных издателя и подписчика.</span><span class="sxs-lookup"><span data-stu-id="d76da-137">For example, an application could provide a new version of the winning row by combining values from the Publisher and Subscriber data sets.</span></span>  
  
### <a name="custom-error-resolution"></a><span data-ttu-id="d76da-138">разрешение пользовательских ошибок.</span><span class="sxs-lookup"><span data-stu-id="d76da-138">Custom Error Resolution</span></span>  
 <span data-ttu-id="d76da-139">Пользовательская логика может вызываться во время распространения изменений, которые заканчиваются ошибками.</span><span class="sxs-lookup"><span data-stu-id="d76da-139">Custom logic can be invoked during the propagation of changes that result in errors.</span></span> <span data-ttu-id="d76da-140">Логика может выполнять одно из двух действий:</span><span class="sxs-lookup"><span data-stu-id="d76da-140">The logic can perform one of two actions:</span></span>  
  
-   <span data-ttu-id="d76da-141">Принять разрешение ошибок по умолчанию</span><span class="sxs-lookup"><span data-stu-id="d76da-141">Accept default error resolution</span></span>  
  
     <span data-ttu-id="d76da-142">Это действие применимо для приложений, которые могут нуждаться в просмотре ошибки, выполнении дополнительного действия и, возможно, записи в журнал сообщения о пользовательской ошибке.</span><span class="sxs-lookup"><span data-stu-id="d76da-142">This is useful for applications that might need to review the error and perform additional action and possibly log a custom error log message.</span></span>  
  
-   <span data-ttu-id="d76da-143">Принять пользовательское разрешение ошибок</span><span class="sxs-lookup"><span data-stu-id="d76da-143">Accept custom error resolution</span></span>  
  
     <span data-ttu-id="d76da-144">Это действие может понадобиться для приложений, которым нужно выбрать значения данных, относящиеся к их бизнес-логике, и обеспечить процесс синхронизации пользовательским набором данных.</span><span class="sxs-lookup"><span data-stu-id="d76da-144">This is useful for applications that might need to select data values that are specific to their business logic and supply the synchronization process with this custom dataset.</span></span> <span data-ttu-id="d76da-145">Например если процесс репликации обнаруживает нарушение повторяющихся ключей, обработчик бизнес-логики может предоставить новую версию изменений данных, в которой ключ не будет вступать в конфликт.</span><span class="sxs-lookup"><span data-stu-id="d76da-145">For example, if the replication process encounters a duplicate key violation, the business logic handler could provide a new version of the data change in which the key will no longer conflict.</span></span> <span data-ttu-id="d76da-146">Изменения, сделанные на издателе или подписчике, могут затем сохраняться в базе данных, и процессу репликации не нужно будет исправлять ошибочные вставки с помощью удаления.</span><span class="sxs-lookup"><span data-stu-id="d76da-146">Changes made at the Publisher and Subscriber can then persist in the database, and the replication process doesn't have to compensate for the failed insert with a delete.</span></span>  
  
## <a name="deployment-scenarios-for-business-logic-handlers"></a><span data-ttu-id="d76da-147">Сценарии развертывания для обработчиков бизнес-логики</span><span class="sxs-lookup"><span data-stu-id="d76da-147">Deployment Scenarios for Business Logic Handlers</span></span>  
 <span data-ttu-id="d76da-148">Обработчики бизнес-логики могут развертываться на:</span><span class="sxs-lookup"><span data-stu-id="d76da-148">Business logic handlers can be deployed at:</span></span>  
  
-   <span data-ttu-id="d76da-149">Распространитель.</span><span class="sxs-lookup"><span data-stu-id="d76da-149">The Distributor.</span></span> <span data-ttu-id="d76da-150">Используйте принудительную подписку с тем, чтобы бизнес-логика выполнялась на распространителе.</span><span class="sxs-lookup"><span data-stu-id="d76da-150">Use a push subscription so that business logic is executed at the Distributor.</span></span>  
  
-   <span data-ttu-id="d76da-151">Подписчик.</span><span class="sxs-lookup"><span data-stu-id="d76da-151">The Subscriber.</span></span> <span data-ttu-id="d76da-152">Используйте подписку по запросу с тем, чтобы бизнес-логика выполнялась на подписчике.</span><span class="sxs-lookup"><span data-stu-id="d76da-152">Use a pull subscription so that business logic is executed at the Subscriber.</span></span>  
  
-   <span data-ttu-id="d76da-153">Сервер служб Internet Information Services (IIS), если используется веб-синхронизация.</span><span class="sxs-lookup"><span data-stu-id="d76da-153">An Internet Information Services (IIS) server if Web synchronization is used.</span></span> <span data-ttu-id="d76da-154">Используйте подписку по запросу, синхронизированную с помощью веб-синхронизации, и обработчик бизнес-логики будет выполняться на сервере IIS.</span><span class="sxs-lookup"><span data-stu-id="d76da-154">Use a pull subscription synchronized with Web synchronization, and the business logic handler will execute at the IIS Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d76da-155">См. также:</span><span class="sxs-lookup"><span data-stu-id="d76da-155">See Also</span></span>  
 <span data-ttu-id="d76da-156">[Репликация слиянием](merge-replication.md) </span><span class="sxs-lookup"><span data-stu-id="d76da-156">[Merge Replication](merge-replication.md) </span></span>  
 <span data-ttu-id="d76da-157">[Subscribe to Publications](../subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="d76da-157">[Subscribe to Publications](../subscribe-to-publications.md) </span></span>  
 <span data-ttu-id="d76da-158">[Синхронизация данных](../synchronize-data.md) </span><span class="sxs-lookup"><span data-stu-id="d76da-158">[Synchronize Data](../synchronize-data.md) </span></span>  
 [<span data-ttu-id="d76da-159">Web Synchronization for Merge Replication</span><span class="sxs-lookup"><span data-stu-id="d76da-159">Web Synchronization for Merge Replication</span></span>](../web-synchronization-for-merge-replication.md)  
  
  

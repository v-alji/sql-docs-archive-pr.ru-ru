---
title: Параметры статьи для репликации транзакций | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- articles [SQL Server replication], transactional replication options
- transactional replication, article options
ms.assetid: 3469b185-0ea5-4690-a71c-717230d886b6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1cc13a3d11e35ed47eac4ff401fb8b7cb607b32b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664856"
---
# <a name="article-options-for-transactional-replication"></a><span data-ttu-id="726f4-102">Параметры статьи для репликации транзакций</span><span class="sxs-lookup"><span data-stu-id="726f4-102">Article Options for Transactional Replication</span></span>
  <span data-ttu-id="726f4-103">Для статей в публикациях транзакций существует несколько параметров.</span><span class="sxs-lookup"><span data-stu-id="726f4-103">There are a number of options for articles in transactional publications.</span></span> <span data-ttu-id="726f4-104">Репликация транзакций позволяет выполнять следующее:</span><span class="sxs-lookup"><span data-stu-id="726f4-104">With transactional replication, you can do the following:</span></span>  
  
-   <span data-ttu-id="726f4-105">Задавать способ передачи изменений от издателя подписчикам.</span><span class="sxs-lookup"><span data-stu-id="726f4-105">Specify how changes are propagated from the Publisher to Subscribers.</span></span> <span data-ttu-id="726f4-106">Дополнительные сведения см. в статье [Указание способа распространения изменений для статей транзакций](transactional-articles-specify-how-changes-are-propagated.md).</span><span class="sxs-lookup"><span data-stu-id="726f4-106">For more information, see [Specify How Changes Are Propagated for Transactional Articles](transactional-articles-specify-how-changes-are-propagated.md).</span></span>  
  
-   <span data-ttu-id="726f4-107">Указывать, что необходима репликация выполнения хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="726f4-107">Specify that the execution of a stored procedure be replicated.</span></span> <span data-ttu-id="726f4-108">Это полезно при репликации результатов хранимых процедур, связанных с обслуживанием и работающих с большими объемами данных.</span><span class="sxs-lookup"><span data-stu-id="726f4-108">This is useful in replicating the results of maintenance-oriented stored procedures that affect large amounts of data.</span></span> <span data-ttu-id="726f4-109">Дополнительные сведения см. в статье [Publishing Stored Procedure Execution in Transactional Replication](publishing-stored-procedure-execution-in-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="726f4-109">For more information, see [Publishing Stored Procedure Execution in Transactional Replication](publishing-stored-procedure-execution-in-transactional-replication.md).</span></span>  
  
-   <span data-ttu-id="726f4-110">Укажите параметры схемы, например копируются ли ограничения и триггеры на подписчик.</span><span class="sxs-lookup"><span data-stu-id="726f4-110">Specify schema options, such as whether constraints and triggers are copied to the Subscriber.</span></span> <span data-ttu-id="726f4-111">Дополнительные сведения см. в разделе [Указание параметров схемы](../publish/specify-schema-options.md).</span><span class="sxs-lookup"><span data-stu-id="726f4-111">For more information, see [Specify Schema Options](../publish/specify-schema-options.md).</span></span>  
  
-   <span data-ttu-id="726f4-112">Использовать фильтры строк и фильтры столбцов.</span><span class="sxs-lookup"><span data-stu-id="726f4-112">Use row filters and column filters.</span></span> <span data-ttu-id="726f4-113">Фильтрация статей таблиц позволяет создавать секции публикуемых данных.</span><span class="sxs-lookup"><span data-stu-id="726f4-113">Filtering table articles enables you to create partitions of data to be published.</span></span> <span data-ttu-id="726f4-114">Дополнительные сведения см. в статье [Фильтрация опубликованных данных](../publish/filter-published-data.md).</span><span class="sxs-lookup"><span data-stu-id="726f4-114">For more information, see [Filter Published Data](../publish/filter-published-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="726f4-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="726f4-115">See Also</span></span>  
 [<span data-ttu-id="726f4-116">Публикация данных и объектов базы данных</span><span class="sxs-lookup"><span data-stu-id="726f4-116">Publish Data and Database Objects</span></span>](../publish/publish-data-and-database-objects.md)  
  
  

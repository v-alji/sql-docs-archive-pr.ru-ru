---
title: Управление изменениями в представлениях источников данных и источниками данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- modifying data sources
- modifying data source views
- data source views [Analysis Services], schema updates
- data sources [Analysis Services], schema updates
ms.assetid: 928c9f63-365a-43fd-9bbd-78828cc7e54d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0f558ce6aaf9e57576d5773322352d33b81a3392
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730969"
---
# <a name="manage-changes-to-data-source-views-and-data-sources"></a><span data-ttu-id="1205c-102">Управление изменениями в источниках данных и представлениях источников данных</span><span class="sxs-lookup"><span data-stu-id="1205c-102">Manage Changes to Data Source Views and Data Sources</span></span>
  <span data-ttu-id="1205c-103">При повторном запуске мастера формирования схем он повторно использует тот же источник данных и представление источника данных, которые он использовал при первоначальном формировании.</span><span class="sxs-lookup"><span data-stu-id="1205c-103">When the Schema Generation Wizard is rerun, it reuses the same data source and data source view that it used for the original generation.</span></span> <span data-ttu-id="1205c-104">При добавлении источника данных или представления источников данных мастер не использует их.</span><span class="sxs-lookup"><span data-stu-id="1205c-104">If you add a data source or a data source view, the wizard does not use it.</span></span> <span data-ttu-id="1205c-105">При удалении оригинального источника данных или представления источников данных после первоначального формирования мастер необходимо запустить с самого начала.</span><span class="sxs-lookup"><span data-stu-id="1205c-105">If you delete the original data source or data source view after the initial generation, you must run the wizard from the beginning.</span></span> <span data-ttu-id="1205c-106">Все предыдущие настройки мастера также удаляются.</span><span class="sxs-lookup"><span data-stu-id="1205c-106">All previous settings in the wizard are also deleted.</span></span> <span data-ttu-id="1205c-107">Любые существующие объекты в основной базе данных, связанные с удаленным источником данных или представлением источника данных, при следующем запуске мастера формирования схем воспринимаются как объекты, созданные пользователем.</span><span class="sxs-lookup"><span data-stu-id="1205c-107">Any existing objects in an underlying database that were bound to a deleted data source or data source view are treated as user-created objects the next time you run the Schema Generation Wizard.</span></span>  
  
 <span data-ttu-id="1205c-108">Если во время формирования представление источника данных не отражает реального состояния основной базы данных, мастер формирования схем может обнаружить ошибки при формировании схемы для базы данных предметной области.</span><span class="sxs-lookup"><span data-stu-id="1205c-108">If the data source view does not reflect the actual state of the underlying database at the time of generation, the Schema Generation Wizard may encounter errors when it generates the schema for the subject area database.</span></span> <span data-ttu-id="1205c-109">Например, если представление источника данных указывает, что тип данных столбца **int**, но тип данных этого столбца на самом деле **string**, мастер формирования схем устанавливает тип данных для внешнего ключа в **INT** для совпадения с представлением источника данных, а затем выдает сбой при создании связи, поскольку реальный тип данных **string**.</span><span class="sxs-lookup"><span data-stu-id="1205c-109">For example, if the data source view specifies that the data type for a column is **int**, but data type for the column is actually **string**, the Schema Generation Wizard sets the data type for the foreign key to **INT** to match the data source view and then fails when it creates the relationship because the actual type is **string**.</span></span>  
  
 <span data-ttu-id="1205c-110">С другой стороны, при изменении строки соединения с источником данных на другую базу данных по сравнению с предыдущим формированием не возникает ошибки.</span><span class="sxs-lookup"><span data-stu-id="1205c-110">On the other hand, if you change the data source connection string to a different database from the previous generation, no error is generated.</span></span> <span data-ttu-id="1205c-111">Используется эта новая база данных, а в предыдущую базу данных не вносятся никакие изменения.</span><span class="sxs-lookup"><span data-stu-id="1205c-111">The new database is used, and no change is made to the previous database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1205c-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="1205c-112">See Also</span></span>  
 [<span data-ttu-id="1205c-113">Основные сведения о добавочном создании</span><span class="sxs-lookup"><span data-stu-id="1205c-113">Understanding Incremental Generation</span></span>](understanding-incremental-generation.md)  
  
  

---
title: Удаление таблицы (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: be4ed45f-fde3-466c-9869-49bd3ddb505e
author: minewiskan
ms.author: owend
ms.openlocfilehash: c72fa90426440c1be84318a15cf0d761ef16aca8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666735"
---
# <a name="delete-a-table-ssas-tabular"></a><span data-ttu-id="928f3-102">Удаление таблицы (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="928f3-102">Delete a Table (SSAS Tabular)</span></span>
  <span data-ttu-id="928f3-103">В конструкторе моделей разрешено удалять ненужные таблицы из базы данных рабочей области модели.</span><span class="sxs-lookup"><span data-stu-id="928f3-103">In the model designer, you can delete tables in your model workspace database that you no longer need.</span></span> <span data-ttu-id="928f3-104">Удаление таблицы не влияет на исходный источник данных. Удаление коснется только данных, которые были импортированы и над которыми велась работа.</span><span class="sxs-lookup"><span data-stu-id="928f3-104">Deleting a table does not affect the original source data, only the data that you imported and were working with.</span></span> <span data-ttu-id="928f3-105">Удаление таблицы отменить нельзя.</span><span class="sxs-lookup"><span data-stu-id="928f3-105">You cannot undo the deletion of a table.</span></span>  
  
### <a name="to-delete-a-table"></a><span data-ttu-id="928f3-106">для удаления таблицы.</span><span class="sxs-lookup"><span data-stu-id="928f3-106">To delete a table</span></span>  
  
-   <span data-ttu-id="928f3-107">Щелкните правой кнопкой мыши вкладку в нижней части конструктора моделей для таблицы, которую собираетесь удалить, и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="928f3-107">Right-click the tab at the bottom of the model designer for the table that you want to delete, and then click **Delete**.</span></span>  
  
## <a name="considerations-when-deleting-tables"></a><span data-ttu-id="928f3-108">Последствия удаления таблиц</span><span class="sxs-lookup"><span data-stu-id="928f3-108">Considerations when Deleting Tables</span></span>  
  
-   <span data-ttu-id="928f3-109">При удалении таблицы удаляется и вся вкладка, на которой размещалась эта таблица.</span><span class="sxs-lookup"><span data-stu-id="928f3-109">When you delete a table, the entire tab that the table was on is deleted.</span></span>  
  
-   <span data-ttu-id="928f3-110">Если с таблицей связаны какие-либо меры, то определения мер также будут удалены.</span><span class="sxs-lookup"><span data-stu-id="928f3-110">If any measures were associated with that table, the definition of the measure will also be deleted.</span></span>  
  
-   <span data-ttu-id="928f3-111">Если с помощью этой таблицы были созданы вычисляемые столбцы, столбцы в этой таблице все равно будут удалены, а все вычисляемые столбцы в другой таблице, использующие столбцы удаленной таблицы, отобразят ошибку.</span><span class="sxs-lookup"><span data-stu-id="928f3-111">If you created any calculated columns using that table, columns in that table are also deleted; any calculated columns in other tables that use columns from the deleted table will display an error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="928f3-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="928f3-112">See Also</span></span>  
 [<span data-ttu-id="928f3-113">Таблицы и столбцы (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="928f3-113">Tables and Columns &#40;SSAS Tabular&#41;</span></span>](tables-and-columns-ssas-tabular.md)  
  
  

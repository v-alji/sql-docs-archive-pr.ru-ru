---
title: Удаление столбца (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 703db83b-e554-450e-813e-23ad08c1cdad
author: minewiskan
ms.author: owend
ms.openlocfilehash: 06af0b7fd9879661db95bb2073cced545bb4eef5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665139"
---
# <a name="delete-a-column-ssas-tabular"></a><span data-ttu-id="c7850-102">Удаление столбца (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="c7850-102">Delete a Column (SSAS Tabular)</span></span>
  <span data-ttu-id="c7850-103">В этом разделе описано, как удалить столбец из таблицы в табличной модели.</span><span class="sxs-lookup"><span data-stu-id="c7850-103">This topic describes how to delete a column from a tabular model table.</span></span>  
  
## <a name="delete-a-model-table-column"></a><span data-ttu-id="c7850-104">Удаление столбца таблицы модели</span><span class="sxs-lookup"><span data-stu-id="c7850-104">Delete a Model Table Column</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c7850-105">При удалении столбца из таблицы модели этот столбец не удаляется из определения запроса секции.</span><span class="sxs-lookup"><span data-stu-id="c7850-105">Deleting a column from a model table does not delete the column from a partition query definition.</span></span> <span data-ttu-id="c7850-106">Если удаляемый столбец является частью секции, необходимо удалить его вручную из определения запроса секции.</span><span class="sxs-lookup"><span data-stu-id="c7850-106">If the column you are deleting is part of a partition, you must manually delete the column from the partition query definition.</span></span> <span data-ttu-id="c7850-107">Несоблюдение требования по удалению столбца из определения запроса секции приведет к тому, что запросы к этому столбцу и возврат данных будут выполняться, но столбец не будет заполняться в таблице модели во время операций обработки.</span><span class="sxs-lookup"><span data-stu-id="c7850-107">Failure to delete the column from the partition query definition will cause the column to be queried and data returned, but not populated to the model table, during processing operations.</span></span> <span data-ttu-id="c7850-108">Дополнительные сведения см. в разделе [Секции (табличные службы SSAS)](partitions-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="c7850-108">For more information, see [Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md).</span></span>  
  
#### <a name="to-delete-a-model-table-column"></a><span data-ttu-id="c7850-109">Удаление столбца таблицы модели</span><span class="sxs-lookup"><span data-stu-id="c7850-109">To delete a model table column</span></span>  
  
-   <span data-ttu-id="c7850-110">В конструкторе моделей в таблице, которая содержит удаляемый столбец, щелкните этот столбец правой кнопкой мыши и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="c7850-110">In the model designer, in the table that contains the column you want to delete, right-click on the column, and then click **Delete**.</span></span>  
  
#### <a name="to-delete-a-model-table-column-by-using-the-table-properties-dialog-box"></a><span data-ttu-id="c7850-111">Удаление столбца из таблицы модели с помощью диалогового окна «Свойства таблицы»</span><span class="sxs-lookup"><span data-stu-id="c7850-111">To delete a model table column by using the Table Properties dialog box</span></span>  
  
1.  <span data-ttu-id="c7850-112">В конструкторе моделей щелкните таблицу, которая содержит удаляемый столбец, затем откройте меню **Таблица** и выберите пункт  **Свойства таблицы**.</span><span class="sxs-lookup"><span data-stu-id="c7850-112">In the model designer, click on the table which contains the column you want to delete, then click the **Table** menu, and then click  **Table Properties**.</span></span>  
  
2.  <span data-ttu-id="c7850-113">В разделе **Имена столбцов из**выберите **Модель** (*чтобы использовать имена столбцов таблицы модели, если они отличаются от источника*).</span><span class="sxs-lookup"><span data-stu-id="c7850-113">In **Column names from**, select **Model** (*to use model table column names, if different from source*).</span></span>  
  
3.  <span data-ttu-id="c7850-114">В диалоговом окне **Изменение свойств таблицы** в окне предварительного просмотра таблицы снимите флажок, соответствующий удаляемому столбцу, после чего нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c7850-114">In the **Edit Table Properties** dialog box, in the table preview window, uncheck the column you want to delete, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7850-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="c7850-115">See Also</span></span>  
 <span data-ttu-id="c7850-116">[Добавление столбцов в таблицу &#40;табличных&#41;SSAS](add-columns-to-a-table-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="c7850-116">[Add Columns to a Table &#40;SSAS Tabular&#41;](add-columns-to-a-table-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="c7850-117">Секции (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="c7850-117">Partitions &#40;SSAS Tabular&#41;</span></span>](partitions-ssas-tabular.md)  
  
  

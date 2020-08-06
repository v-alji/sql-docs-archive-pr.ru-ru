---
title: Добавление таблицы (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d713c432-db99-4983-acc1-52b0fdd58bd6
author: minewiskan
ms.author: owend
ms.openlocfilehash: a80c22c992a89ed2cb3db84809b47a7cd08cb514
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666748"
---
# <a name="add-a-table-ssas-tabular"></a><span data-ttu-id="bfad3-102">Добавление таблицы (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="bfad3-102">Add a Table (SSAS Tabular)</span></span>
  <span data-ttu-id="bfad3-103">В этом разделе описывается добавление таблицы из источника данных, из которого ранее выполнялся импорт данных в модель.</span><span class="sxs-lookup"><span data-stu-id="bfad3-103">This topic describes how to add a table from a data source from which you have previously imported data into your model.</span></span> <span data-ttu-id="bfad3-104">Чтобы добавить таблицу из того же источника данных, можно использовать существующее соединение с источником данных.</span><span class="sxs-lookup"><span data-stu-id="bfad3-104">To add a table from the same data source, you can use the existing data source connection.</span></span> <span data-ttu-id="bfad3-105">Рекомендуется всегда использовать одно соединение для импорта любого количества таблиц из одного источника данных.</span><span class="sxs-lookup"><span data-stu-id="bfad3-105">It is recommended you always use a single connection when importing any number of tables from a single data source.</span></span>  
  
### <a name="to-add-a-table-from-an-existing-data-source"></a><span data-ttu-id="bfad3-106">Добавление таблицы из существующего источника данных</span><span class="sxs-lookup"><span data-stu-id="bfad3-106">To add a table from an existing data source</span></span>  
  
1.  <span data-ttu-id="bfad3-107">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]в меню **Модель** выберите пункт **Существующие соединения**.</span><span class="sxs-lookup"><span data-stu-id="bfad3-107">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click the **Model** menu, and then click **Existing Connections**.</span></span>  
  
2.  <span data-ttu-id="bfad3-108">На странице **Существующие соединения** выберите соединение с источником данных, содержащем добавляемую таблицу, и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="bfad3-108">On the **Existing Connections** page, select the connection to the data source that has the table you want to add, and then click **Open**.</span></span>  
  
3.  <span data-ttu-id="bfad3-109">На странице **Выбор таблиц и представлений** выберите из источника данных таблицу, которую нужно добавить в модель.</span><span class="sxs-lookup"><span data-stu-id="bfad3-109">On the **Select Tables and Views** page, select the table from the data source you want to add to your model.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bfad3-110">На странице **Выбор таблиц и представлений** ранее импортированные таблицы не будут отмечены.</span><span class="sxs-lookup"><span data-stu-id="bfad3-110">The **Select Tables and Views** page will not show tables that were previously imported as checked.</span></span>  <span data-ttu-id="bfad3-111">Если выбрать таблицу, которая уже импортировалась по этому соединению, и не дать ей новое понятное имя, то к понятному имени будет добавлена цифра 1.</span><span class="sxs-lookup"><span data-stu-id="bfad3-111">If you select a table that was previously imported using this connection, and you did not give the table a different friendly name, a 1 will be appended to the friendly name.</span></span> <span data-ttu-id="bfad3-112">Не нужно повторно выбирать таблицы, ранее импортированные по этому соединению.</span><span class="sxs-lookup"><span data-stu-id="bfad3-112">You do not need to re-select any tables that were previously imported by using this connection.</span></span>  
  
4.  <span data-ttu-id="bfad3-113">При необходимости используйте функцию **Просмотр и фильтрация**, чтобы выделить нужные столбцы или применить фильтры к импортируемым данным.</span><span class="sxs-lookup"><span data-stu-id="bfad3-113">If necessary, use **Preview & Filter** to select only certain columns or apply filters to the data to be imported.</span></span>  
  
5.  <span data-ttu-id="bfad3-114">Нажмите кнопку **Готово** , чтобы импортировать новую таблицу.</span><span class="sxs-lookup"><span data-stu-id="bfad3-114">Click **Finish** to import the new table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bfad3-115">Если из одного источника данных одновременно импортируется несколько таблиц, то в модели будут автоматически созданы все связи, существующие между этими таблицами в источнике.</span><span class="sxs-lookup"><span data-stu-id="bfad3-115">When importing multiple tables at the same time from a single data source, any relationships between those tables at the source will automatically be created in the model.</span></span> <span data-ttu-id="bfad3-116">Однако если таблица добавляется позже, то может понадобиться вручную создать в модели связи между новыми таблицами и ранее импортированными таблицами.</span><span class="sxs-lookup"><span data-stu-id="bfad3-116">When adding a table later; however, you may need to manually create relationships in the model between newly added tables and the tables that were previously imported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfad3-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="bfad3-117">See Also</span></span>  
 <span data-ttu-id="bfad3-118">[Импорт данных &#40;табличные&#41;SSAS](../import-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="bfad3-118">[Import Data &#40;SSAS Tabular&#41;](../import-data-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="bfad3-119">Удаление таблицы (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="bfad3-119">Delete a Table &#40;SSAS Tabular&#41;</span></span>](delete-a-table-ssas-tabular.md)  
  
  

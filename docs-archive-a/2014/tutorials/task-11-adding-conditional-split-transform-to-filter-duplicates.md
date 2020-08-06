---
title: Задача 11. Добавление преобразования "Условное разбиение" для фильтрации дубликатов | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 3094bd57-5cf4-4860-bf51-fadd1b309f94
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: e8370563c4275df0d0513d5434a8b16efba728d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751584"
---
# <a name="task-11-adding-conditional-split-transform-to-filter-duplicates"></a><span data-ttu-id="e48ad-102">Задача 11. Добавление преобразования "Условное разбиение" для фильтрации повторов</span><span class="sxs-lookup"><span data-stu-id="e48ad-102">Task 11: Adding Conditional Split Transform to Filter Duplicates</span></span>
  <span data-ttu-id="e48ad-103">В этой задаче в поток данных добавляется преобразование «Условное разбиение».</span><span class="sxs-lookup"><span data-stu-id="e48ad-103">In this task, you add the Conditional Split Transform to the data flow.</span></span> <span data-ttu-id="e48ad-104">Это преобразование позволяет фильтровать повторения из входящего набора записей.</span><span class="sxs-lookup"><span data-stu-id="e48ad-104">This transform helps you filter duplicates from the incoming record set.</span></span> <span data-ttu-id="e48ad-105">Преобразование «Нечеткое группирование» группирует записи, которые оно распознает как совпадающие, и выбирает одну из записей в качестве сводной записи.</span><span class="sxs-lookup"><span data-stu-id="e48ad-105">The Fuzzy Group transform groups the records that it finds to be matches and picks one of the records as a pivot record.</span></span> <span data-ttu-id="e48ad-106">Все записи в группе имеют одинаковое значение _key_out.</span><span class="sxs-lookup"><span data-stu-id="e48ad-106">All the records in a group have the same _key_out value.</span></span> <span data-ttu-id="e48ad-107">Сводная запись имеет то же значение _key_in, что и значение _key_out.</span><span class="sxs-lookup"><span data-stu-id="e48ad-107">The pivot record in the group has _key_in same as the _key_out value.</span></span> <span data-ttu-id="e48ad-108">Другие записи в группе имеют различные значения _key_in и _key_out.</span><span class="sxs-lookup"><span data-stu-id="e48ad-108">The other records in the group have different values for _key_in and _key_out.</span></span> <span data-ttu-id="e48ad-109">Поэтому при фильтрации с помощью условия _key_in==_key_out будет получена только сводная строка в группе.</span><span class="sxs-lookup"><span data-stu-id="e48ad-109">Therefore, when you filter using the condition _key_in==_key_out, you only get the pivot row in the group.</span></span>  
  
1.  <span data-ttu-id="e48ad-110">Перетащите преобразование **Условное разбиение** из раздела **Общие** в **области элементов служб SSIS** на вкладку **поток данных** .</span><span class="sxs-lookup"><span data-stu-id="e48ad-110">Drag-drop **Conditional Split** Transform from **Common** section in the **SSIS Toolbox** to the **Data Flow** tab.</span></span>  
  
2.  <span data-ttu-id="e48ad-111">Щелкните правой кнопкой мыши **Преобразование «Условное разбиение** » на вкладке « **поток данных** » и выберите команду **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="e48ad-111">Right-click **Conditional Split Transform** in the **Data Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="e48ad-112">Введите " **Фильтровать дубликаты** " и нажмите клавишу **Ввод**.</span><span class="sxs-lookup"><span data-stu-id="e48ad-112">Type **Filter Duplicates** and press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="e48ad-113">Подключите **поставщиков групп с соответствующими идентификаторами** , чтобы **отфильтровать дубликаты**.</span><span class="sxs-lookup"><span data-stu-id="e48ad-113">Connect **Group Suppliers with Matching IDs** to **Filter Duplicates**.</span></span>  
  
4.  <span data-ttu-id="e48ad-114">Дважды щелкните элемент **Фильтровать дубликаты** , чтобы открыть диалоговое окно **Редактор преобразования "Условное разбиение** ".</span><span class="sxs-lookup"><span data-stu-id="e48ad-114">Double-click **Filter Duplicates** to launch the **Conditional Split Transform Editor** dialog box.</span></span>  
  
5.  <span data-ttu-id="e48ad-115">Разверните **столбцы** в левой верхней области.</span><span class="sxs-lookup"><span data-stu-id="e48ad-115">Expand **Columns** in the top-left pane.</span></span>  
  
6.  <span data-ttu-id="e48ad-116">Перетащите **_key_in** в столбец **условие** .</span><span class="sxs-lookup"><span data-stu-id="e48ad-116">Drag-drop **_key_in** to the **Condition** column.</span></span>  
  
7.  <span data-ttu-id="e48ad-117">Введите = = (равно) рядом с **_key_in** и перетащите **_key_out**перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="e48ad-117">Type == (equals to) next to **_key_in** and drag-drop **_key_out**.</span></span>  
  
8.  <span data-ttu-id="e48ad-118">Щелкните **вариант 1** в столбце **имя выхода** , введите **уникальные записи**и нажмите клавишу **Ввод**.</span><span class="sxs-lookup"><span data-stu-id="e48ad-118">Click **Case 1** in the **Output Name** column, type **Unique Records**, and press **ENTER**.</span></span>  
  
     <span data-ttu-id="e48ad-119">![редактор преобразования «Условное разбиение»](../../2014/tutorials/media/et-addingconditionalsplittransformtofilterduplicates.jpg "редактор преобразования «Условное разбиение»")</span><span class="sxs-lookup"><span data-stu-id="e48ad-119">![Conditional Split Transformation Editor](../../2014/tutorials/media/et-addingconditionalsplittransformtofilterduplicates.jpg "Conditional Split Transformation Editor")</span></span>  
  
9. <span data-ttu-id="e48ad-120">Нажмите кнопку **ОК** , чтобы закрыть диалоговое окно **Редактор преобразования «Условное разбиение** ».</span><span class="sxs-lookup"><span data-stu-id="e48ad-120">Click **OK** to close the **Conditional Split Transformation Editor** dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="e48ad-121">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="e48ad-121">Next Step</span></span>  
 [<span data-ttu-id="e48ad-122">Задача 12. Добавление преобразования "Производный столбец" для добавления требуемых столбцов MDS</span><span class="sxs-lookup"><span data-stu-id="e48ad-122">Task 12: Adding Derived Column Transform to Add Columns Required by MDS</span></span>](../../2014/tutorials/task-12-adding-derived-column-transform-to-add-columns-required-by-mds.md)  
  
  

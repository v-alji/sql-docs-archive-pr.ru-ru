---
title: Скрытие или закрепление столбцов (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.hideunhidecolumnsdb.f1
ms.assetid: 5407aee5-6a07-4559-a2ba-2ca00a242f02
author: minewiskan
ms.author: owend
ms.openlocfilehash: 71398eecbc342b4e3f9c2445fef3023132266dac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728834"
---
# <a name="hide-or-freeze-columns-ssas-tabular"></a><span data-ttu-id="448c3-102">Скрытие или закрепление столбцов (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="448c3-102">Hide or Freeze Columns (SSAS Tabular)</span></span>
  <span data-ttu-id="448c3-103">Если в конструкторе моделей некоторые столбцы не нужно отображать в таблице, то их можно временно скрыть.</span><span class="sxs-lookup"><span data-stu-id="448c3-103">In the model designer, if there are columns that you don't want to display in a table, you can temporarily hide them.</span></span> <span data-ttu-id="448c3-104">Скрытый столбец освобождает пространство на экране, позволяя добавлять новые столбцы или работать только с необходимыми столбцами данных.</span><span class="sxs-lookup"><span data-stu-id="448c3-104">Hiding a column gives you more room on the screen to add new columns or to work with only relevant columns of data.</span></span> <span data-ttu-id="448c3-105">Скрыть или отобразить столбцы можно через меню **Столбец** в конструкторе моделей или через меню заголовка столбца, которое вызывается нажатием правой кнопкой мыши.</span><span class="sxs-lookup"><span data-stu-id="448c3-105">You can hide and unhide columns from the **Column** menu in the model designer, and from the right-click menu available from each column header.</span></span> <span data-ttu-id="448c3-106">Чтобы область модели оставалась видимой при переходе в другую область при прокрутке, можно закрепить определенные столбцы в одной области.</span><span class="sxs-lookup"><span data-stu-id="448c3-106">To keep an area of a model visible while you scroll to another area of the model, you can lock specific columns in one area by freezing them.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="448c3-107">Возможность скрытия столбцов предусмотрена не для защиты данных, а только для упрощения и уменьшения списка столбцов, видимых в конструкторе моделей или отчетах.</span><span class="sxs-lookup"><span data-stu-id="448c3-107">The ability to hide columns is not intended to be used for data security, only to simplify and shorten the list of columns visible in the model designer or reports.</span></span> <span data-ttu-id="448c3-108">Для защиты данных можно задать роли безопасности.</span><span class="sxs-lookup"><span data-stu-id="448c3-108">To secure data, you can define security roles.</span></span> <span data-ttu-id="448c3-109">Роли дают возможность сделать метаданные и данные видимыми только для тех объектов, которые определены в роли.</span><span class="sxs-lookup"><span data-stu-id="448c3-109">Roles can limit viewable metadata and data to only those objects defined in the role.</span></span> <span data-ttu-id="448c3-110">Дополнительные сведения см. в разделе [Роли (табличные службы SSAS)](roles-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="448c3-110">For more information, see [Roles &#40;SSAS Tabular&#41;](roles-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="448c3-111">Можно выбрать скрытие столбца во время работы в конструкторе моделей или в отчетах.</span><span class="sxs-lookup"><span data-stu-id="448c3-111">When you hide a column, you have the option to hide the column while you are working in the model designer or in reports.</span></span> <span data-ttu-id="448c3-112">Если скрыть все столбцы, то вся таблица в конструкторе моделей будет выглядеть пустой.</span><span class="sxs-lookup"><span data-stu-id="448c3-112">If you hide all columns, the entire table appears blank in the model designer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="448c3-113">Если необходимо скрыть много столбцов, то вместо этого можно создать перспективу.</span><span class="sxs-lookup"><span data-stu-id="448c3-113">If you have many columns to hide, you can create a perspective instead of hiding and unhiding columns.</span></span> <span data-ttu-id="448c3-114">Перспектива — это пользовательское представление данных, упрощающее работу с подмножествами взаимосвязанных данных.</span><span class="sxs-lookup"><span data-stu-id="448c3-114">A perspective is a custom view of the data that makes it easier to work with subset of related data.</span></span> <span data-ttu-id="448c3-115">Дополнительные сведения см. в разделе [Создание перспектив и управление ими (табличные службы SSAS)](perspectives-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="448c3-115">For more information, see [Create and Manage Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md)</span></span>  
  
### <a name="to-hide-an-individual-column"></a><span data-ttu-id="448c3-116">Скрытие отдельного столбца</span><span class="sxs-lookup"><span data-stu-id="448c3-116">To hide an individual column</span></span>  
  
1.  <span data-ttu-id="448c3-117">В конструкторе моделей выберите таблицу со столбцом, который необходимо скрыть.</span><span class="sxs-lookup"><span data-stu-id="448c3-117">In the model designer, select the table that contains the column that you want to hide.</span></span>  
  
2.  <span data-ttu-id="448c3-118">Щелкните столбец правой кнопкой мыши, выберите команду **Скрыть столбцы**, а затем выберите **Из конструктора и отчетов**, **Из отчетов**или **Из конструктора**.</span><span class="sxs-lookup"><span data-stu-id="448c3-118">Right-click the column, then click **Hide Columns**, and then click **From Designer and Reports**, **From Reports**, or **From Designer**.</span></span>  
  
### <a name="to-hide-multiple-columns"></a><span data-ttu-id="448c3-119">Скрытие нескольких столбцов</span><span class="sxs-lookup"><span data-stu-id="448c3-119">To hide multiple columns</span></span>  
  
1.  <span data-ttu-id="448c3-120">В конструкторе моделей выберите таблицу со столбцом, который необходимо скрыть.</span><span class="sxs-lookup"><span data-stu-id="448c3-120">In the model designer, select the table that contains the columns that you want to hide.</span></span>  
  
2.  <span data-ttu-id="448c3-121">В меню **Столбец** выберите пункт **Скрыть и показать**.</span><span class="sxs-lookup"><span data-stu-id="448c3-121">Click on the **Columns** menu, and then click **Hide and Unhide**.</span></span>  
  
3.  <span data-ttu-id="448c3-122">В диалоговом окне **Скрытие и отображение столбцов** найдите столбцы, которые нужно скрыть, и снимите для них флажки **В конструкторе** , **В отчетах**либо оба флажка.</span><span class="sxs-lookup"><span data-stu-id="448c3-122">In the **Hide and Unhide Columns** dialog box, locate each column that you want to hide, and then deselect one or both of **In Designer** and **In Reports**.</span></span>  
  
4.  <span data-ttu-id="448c3-123">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="448c3-123">Click **OK**.</span></span>  
  
### <a name="to-freeze-columns"></a><span data-ttu-id="448c3-124">Закрепление столбцов</span><span class="sxs-lookup"><span data-stu-id="448c3-124">To freeze columns</span></span>  
  
1.  <span data-ttu-id="448c3-125">В конструкторе моделей выберите таблицу со столбцом, который нужно закрепить.</span><span class="sxs-lookup"><span data-stu-id="448c3-125">In the model designer, select the table that contains the columns that you want to freeze.</span></span>  
  
2.  <span data-ttu-id="448c3-126">Выберите один или несколько столбцов для закрепления.</span><span class="sxs-lookup"><span data-stu-id="448c3-126">Select one or more columns to freeze.</span></span>  
  
3.  <span data-ttu-id="448c3-127">В меню **Столбцы** выберите пункт **Закрепить**.</span><span class="sxs-lookup"><span data-stu-id="448c3-127">Click on the **Columns** menu, and then click **Freeze**..</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="448c3-128">При закреплении столбцов они перемещаются влево или в начало таблицы в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="448c3-128">When a column(s) is frozen, it is moved to left (or front) of the table in the designer.</span></span> <span data-ttu-id="448c3-129">При освобождении столбца он не возвращается в исходное местоположение.</span><span class="sxs-lookup"><span data-stu-id="448c3-129">Unfreezing the column does not move it back to its original location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="448c3-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="448c3-130">See Also</span></span>  
 <span data-ttu-id="448c3-131">[Таблицы и столбцы &#40;табличные&#41;SSAS](tables-and-columns-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="448c3-131">[Tables and Columns &#40;SSAS Tabular&#41;](tables-and-columns-ssas-tabular.md) </span></span>  
 <span data-ttu-id="448c3-132">[Перспективы &#40;табличные&#41;SSAS](perspectives-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="448c3-132">[Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="448c3-133">Роли (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="448c3-133">Roles &#40;SSAS Tabular&#41;</span></span>](roles-ssas-tabular.md)  
  
  

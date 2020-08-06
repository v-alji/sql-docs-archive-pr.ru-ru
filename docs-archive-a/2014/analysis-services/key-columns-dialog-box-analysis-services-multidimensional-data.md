---
title: Диалоговое окно «Ключевые столбцы» (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql.asvs.dimensiondesigner.dbv.dataitemCollection.f1
helpviewer_keywords:
- DataItem Collection dialog box
ms.assetid: 585f27f2-d5eb-4516-b29a-2084010b7d51
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8a72a9e137700ddee822e68901bfde971637d07f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656668"
---
# <a name="key-columns-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="da538-102">Диалоговое окно «Ключевые столбцы» (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="da538-102">Key Columns Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="da538-103">Используйте диалоговое окно **Ключевые столбцы** , чтобы изменить свойство **KeyColumns** атрибута.</span><span class="sxs-lookup"><span data-stu-id="da538-103">Use the **Key Columns** dialog box to change the **KeyColumns** property of an attribute.</span></span> <span data-ttu-id="da538-104">Дополнительные сведения см. в разделе [Изменение свойства KeyColumn атрибута](multidimensional-models/attribute-properties-modify-the-keycolumn-property.md).</span><span class="sxs-lookup"><span data-stu-id="da538-104">For more information, see [Modify the KeyColumn Property of an Attribute](multidimensional-models/attribute-properties-modify-the-keycolumn-property.md).</span></span>  
  
 <span data-ttu-id="da538-105">**Отображение диалогового окна «Ключевые столбцы»**</span><span class="sxs-lookup"><span data-stu-id="da538-105">**To display the Key Columns dialog box**</span></span>  
  
-   <span data-ttu-id="da538-106">В среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] или [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]выберите атрибут, а затем в окне **Свойства** нажмите кнопку с многоточием (**...**), связанную со свойством **KeyColumns** этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="da538-106">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], select an attribute, and in the **Properties** window, click the ellipsis button (**...**) associated with the **KeyColumns** property of that attribute.</span></span>  
  
## <a name="options"></a><span data-ttu-id="da538-107">Варианты</span><span class="sxs-lookup"><span data-stu-id="da538-107">Options</span></span>  
 <span data-ttu-id="da538-108">**Исходная таблица**</span><span class="sxs-lookup"><span data-stu-id="da538-108">**Source table**</span></span>  
 <span data-ttu-id="da538-109">Выберите исходную таблицу, для которой нужно выбрать ключевые столбцы.</span><span class="sxs-lookup"><span data-stu-id="da538-109">Select the source table for which you want to select its key columns.</span></span> <span data-ttu-id="da538-110">Можно выбрать исходную таблицу из списка всех таблиц в представлении источника данных.</span><span class="sxs-lookup"><span data-stu-id="da538-110">You can select the source table from a list of all tables in the Data Source View.</span></span>  
  
 <span data-ttu-id="da538-111">**Доступные столбцы**</span><span class="sxs-lookup"><span data-stu-id="da538-111">**Available Columns**</span></span>  
 <span data-ttu-id="da538-112">Выберите столбцы, которые нужно использовать как ключевые столбцы.</span><span class="sxs-lookup"><span data-stu-id="da538-112">Select the columns that you want to use as key columns.</span></span> <span data-ttu-id="da538-113">Можно выбрать столбцы из списка столбцов указанной **Исходной таблицы** , которые еще не были выбраны как ключевые.</span><span class="sxs-lookup"><span data-stu-id="da538-113">You can select the columns from a list of columns in the specified **Source table** that have not yet been selected as key columns.</span></span>  
  
 <span data-ttu-id="da538-114">Чтобы добавить выбранные столбцы к списку **Ключевые столбцы** , нажмите кнопку **>** .</span><span class="sxs-lookup"><span data-stu-id="da538-114">To add the selected columns to the **Key Columns** list, click the **>** button.</span></span>  
  
 <span data-ttu-id="da538-115">**Ключевые столбцы**</span><span class="sxs-lookup"><span data-stu-id="da538-115">**Key Columns**</span></span>  
 <span data-ttu-id="da538-116">Определите порядок выбранных ключевых столбцов.</span><span class="sxs-lookup"><span data-stu-id="da538-116">Define the order of the selected key columns.</span></span> <span data-ttu-id="da538-117">Порядок ключевых столбцов важен при определении правильного составного ключа.</span><span class="sxs-lookup"><span data-stu-id="da538-117">The order of the key columns is important in defining the correct composite key.</span></span> <span data-ttu-id="da538-118">Чтобы упорядочить или переупорядочить список ключевых столбцов, выберите столбцы, а затем нажмите кнопки **Вверх** или **Вниз** .</span><span class="sxs-lookup"><span data-stu-id="da538-118">To order or reorder the list of key columns, select a column, and then click the **Up** or **Down** buttons.</span></span>  
  
 <span data-ttu-id="da538-119">Чтобы удалить столбец из списка **Ключевые столбцы** , выберите столбец и нажмите кнопку **\<** .</span><span class="sxs-lookup"><span data-stu-id="da538-119">To remove a column from the **Key Columns** list, select the column and click the **\<** button.</span></span>  
  
 <span data-ttu-id="da538-120">**Крывающемся**</span><span class="sxs-lookup"><span data-stu-id="da538-120">**Up**</span></span>  
 <span data-ttu-id="da538-121">Нажмите, чтобы переместить столбец, выбранный в списке **Ключевые столбцы** , на одну позицию вверх.</span><span class="sxs-lookup"><span data-stu-id="da538-121">Click to move the column selected in **Key Columns** up one position.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="da538-122">Этот параметр доступен, только если список содержит более одного столбца и выбран какой-либо столбец.</span><span class="sxs-lookup"><span data-stu-id="da538-122">This option is enabled only if the list contains more than one column and a column is selected.</span></span>  
  
 <span data-ttu-id="da538-123">**Down**</span><span class="sxs-lookup"><span data-stu-id="da538-123">**Down**</span></span>  
 <span data-ttu-id="da538-124">Нажмите, чтобы переместить столбец, выбранный в списке **Ключевые столбцы** , на одну позицию вниз.</span><span class="sxs-lookup"><span data-stu-id="da538-124">Click to move the column selected in **Key Columns** down one position.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="da538-125">Этот параметр доступен, только если список содержит более одного столбца и выбран какой-либо столбец.</span><span class="sxs-lookup"><span data-stu-id="da538-125">This option is enabled only if the list contains more than one column and a column is selected.</span></span>  
  
 **>**  
 <span data-ttu-id="da538-126">Нажмите, чтобы добавить новый столбец в конец списка **Ключевые столбцы**.</span><span class="sxs-lookup"><span data-stu-id="da538-126">Click to add a new column to the end of the columns listed in **Key Columns**.</span></span>  
  
 **<**  
 <span data-ttu-id="da538-127">Нажмите, чтобы удалить выбранный столбец из списка **Ключевые столбцы**.</span><span class="sxs-lookup"><span data-stu-id="da538-127">Click to remove the selected column from the columns listed in **Key Columns**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da538-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="da538-128">See Also</span></span>  
 [<span data-ttu-id="da538-129">Analysis Services конструкторов и диалоговых окон &#40;многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="da538-129">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  

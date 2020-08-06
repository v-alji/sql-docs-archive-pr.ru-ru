---
title: Изменение свойства KeyColumn атрибута | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- binding attributes [Analysis Services]
- attributes [Analysis Services], binding
- key columns [Analysis Services]
ms.assetid: a2643be4-8123-4cc3-baf9-e5ec54a1669d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3367a7aec84ba59efd118a56745bb76fc5266061
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750331"
---
# <a name="modify-the-keycolumn-property-of-an-attribute"></a><span data-ttu-id="9e10b-102">Изменение свойства KeyColumn атрибута</span><span class="sxs-lookup"><span data-stu-id="9e10b-102">Modify the KeyColumn Property of an Attribute</span></span>
  <span data-ttu-id="9e10b-103">Свойство **KeyColumns** атрибута можно изменить.</span><span class="sxs-lookup"><span data-stu-id="9e10b-103">You can modify the **KeyColumns** property of an attribute.</span></span> <span data-ttu-id="9e10b-104">Например, в качестве ключа атрибута может потребоваться не одиночный ключ, а составной.</span><span class="sxs-lookup"><span data-stu-id="9e10b-104">For example, you might want to specify a composite key instead of a single key as the key for the attribute.</span></span>  
  
### <a name="to-modify-the-keycolumns-property-of-an-attribute"></a><span data-ttu-id="9e10b-105">Изменение свойства KeyColumns атрибута</span><span class="sxs-lookup"><span data-stu-id="9e10b-105">To modify the KeyColumns property of an attribute</span></span>  
  
1.  <span data-ttu-id="9e10b-106">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте проект, в котором необходимо изменить свойство **KeyColumns** .</span><span class="sxs-lookup"><span data-stu-id="9e10b-106">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project in which you want to modify the **KeyColumns** property.</span></span>  
  
2.  <span data-ttu-id="9e10b-107">Откройте конструктор измерений одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="9e10b-107">Open Dimension Designer by doing one of the following procedures:</span></span>  
  
    -   <span data-ttu-id="9e10b-108">В **обозревателе решений**правой кнопкой мыши щелкните папку **Измерения** , а затем выберите либо **Открыть** , либо **Конструктор представлений**.</span><span class="sxs-lookup"><span data-stu-id="9e10b-108">In **Solution Explorer**, right-click the dimension in the **Dimensions** folder, and then either click **Open** or **View Designer**.</span></span>  
  
         <span data-ttu-id="9e10b-109">-или-</span><span class="sxs-lookup"><span data-stu-id="9e10b-109">-or-</span></span>  
  
    -   <span data-ttu-id="9e10b-110">В конструкторе кубов на вкладке **Структура куба** разверните измерение куба на панели **измерения** и нажмите кнопку \*\* \<dimension> изменить \*\*.</span><span class="sxs-lookup"><span data-stu-id="9e10b-110">In Cube Designer, on the **Cube Structure** tab, expand the cube dimension in the **Dimensions** pane and click **Edit \<dimension>**.</span></span>  
  
3.  <span data-ttu-id="9e10b-111">На вкладке **Структура измерения** , на панели **Атрибуты** , щелкните атрибут, для которого нужно изменить свойство **KeyColumns** .</span><span class="sxs-lookup"><span data-stu-id="9e10b-111">On the **Dimension Structure** tab, in the **Attributes** pane, click the attribute whose **KeyColumns** property you want to modify.</span></span>  
  
4.  <span data-ttu-id="9e10b-112">В окне **Свойства** щелкните значение для свойства **KeyColumns** .</span><span class="sxs-lookup"><span data-stu-id="9e10b-112">In the **Properties** window, click the value for the **KeyColumns** property.</span></span>  
  
5.  <span data-ttu-id="9e10b-113">Нажмите кнопку обзора **(...)** , отображающуюся в ячейке значения поля свойства.</span><span class="sxs-lookup"><span data-stu-id="9e10b-113">Click the browse **(...)** button that appears in the value cell of the property box.</span></span>  
  
     <span data-ttu-id="9e10b-114">Откроется диалоговое окно **Ключевые столбцы** .</span><span class="sxs-lookup"><span data-stu-id="9e10b-114">The **Key Columns** dialog box opens.</span></span>  
  
6.  <span data-ttu-id="9e10b-115">Для удаления существующего ключевого столбца выберите его в списке **Ключевые столбцы** и нажмите кнопку **\<** .</span><span class="sxs-lookup"><span data-stu-id="9e10b-115">To remove an existing key column, in the **Key Columns** list, select the column, and then click the **\<** button.</span></span>  
  
7.  <span data-ttu-id="9e10b-116">Для добавления ключевого столбца выберите его в списке **Доступные столбцы** и нажмите кнопку **>** .</span><span class="sxs-lookup"><span data-stu-id="9e10b-116">To add a key column, in the **Available Columns** list, select the column, and then click the **>** button.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9e10b-117">Если задано несколько ключевых столбцов, они отображаются в том же порядке, что и в списке **Ключевые столбцы** .</span><span class="sxs-lookup"><span data-stu-id="9e10b-117">If you define multiple key columns, the order in which those columns appear in the **Key Columns** list affects the display order.</span></span> <span data-ttu-id="9e10b-118">Например, у атрибута «месяц» два ключевых столбца: месяц и год.</span><span class="sxs-lookup"><span data-stu-id="9e10b-118">For example, a month attribute has two key columns: month and year.</span></span> <span data-ttu-id="9e10b-119">Если столбец «год» появится в списке раньше столбца «месяц», службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] будут выполнять сортировку по годам, а затем по месяцам.</span><span class="sxs-lookup"><span data-stu-id="9e10b-119">If the year column appears in the list before the month column, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will sort by year and then by month.</span></span> <span data-ttu-id="9e10b-120">Если столбец «месяц» будет в списке раньше столбца «год», службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] будут выполнять сортировку по месяцам, а затем по годам.</span><span class="sxs-lookup"><span data-stu-id="9e10b-120">If the month column appears before the year column, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will sort by month and then by year.</span></span>  
  
8.  <span data-ttu-id="9e10b-121">Чтобы изменить порядок ключевых столбцов, выберите столбец и нажмите кнопку **Вверх** или кнопку **Вниз** .</span><span class="sxs-lookup"><span data-stu-id="9e10b-121">To change the order of key columns, select a column, and then click the **Up** or **Down** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e10b-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="9e10b-122">See Also</span></span>  
 [<span data-ttu-id="9e10b-123">Справочник по свойствам атрибута измерения</span><span class="sxs-lookup"><span data-stu-id="9e10b-123">Dimension Attribute Properties Reference</span></span>](dimension-attribute-properties-reference.md)  
  
  

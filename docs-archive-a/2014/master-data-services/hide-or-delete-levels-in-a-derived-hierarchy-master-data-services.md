---
title: Скрытие или удаление уровней в производной иерархии (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- derived hierarchies, hiding levels
- derived hierarchies, deleting levels
ms.assetid: e00582b9-9415-4b66-b4a7-9f590d83875f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 039b05633bcd1fdc69d226e565b3dc5211e9734f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665402"
---
# <a name="hide-or-delete-levels-in-a-derived-hierarchy-master-data-services"></a><span data-ttu-id="15d8e-102">Скрытие или удаление уровней в производной иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="15d8e-102">Hide or Delete Levels in a Derived Hierarchy (Master Data Services)</span></span>
  <span data-ttu-id="15d8e-103">В службах [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]можно скрыть уровень в производной иерархии, если он необходим для группирования, но отображать этот уровень нежелательно.</span><span class="sxs-lookup"><span data-stu-id="15d8e-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], hide a level in a derived hierarchy when you require the level for grouping but you do not need to show the level.</span></span> <span data-ttu-id="15d8e-104">Если этот уровень не нужен для группирования, то можно удалить его.</span><span class="sxs-lookup"><span data-stu-id="15d8e-104">Delete a level when you do not want to use it for grouping.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="15d8e-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="15d8e-105">Prerequisites</span></span>  
 <span data-ttu-id="15d8e-106">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="15d8e-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="15d8e-107">Необходимо иметь разрешение на доступ к функциональной области **Администрирование системы** .</span><span class="sxs-lookup"><span data-stu-id="15d8e-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="15d8e-108">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="15d8e-108">You must be a model administrator.</span></span> <span data-ttu-id="15d8e-109">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="15d8e-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-hide-or-delete-levels-in-a-derived-hierarchy"></a><span data-ttu-id="15d8e-110">Скрытие и удаление уровней в производной иерархии</span><span class="sxs-lookup"><span data-stu-id="15d8e-110">To hide or delete levels in a derived hierarchy</span></span>  
  
1.  <span data-ttu-id="15d8e-111">В [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Администрирование системы**.</span><span class="sxs-lookup"><span data-stu-id="15d8e-111">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="15d8e-112">На странице **представление модели** в строке меню наведите указатель мыши на пункт **Управление** и щелкните **производные иерархии**.</span><span class="sxs-lookup"><span data-stu-id="15d8e-112">On the **Model View** page, from the menu bar, point to **Manage** and click **Derived Hierarchies**.</span></span>  
  
3.  <span data-ttu-id="15d8e-113">На странице **Обслуживание производной иерархии** выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="15d8e-113">On the **Derived Hierarchy Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="15d8e-114">Выберите строку для производной иерархии, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="15d8e-114">Select the row for the derived hierarchy you want to edit.</span></span>  
  
5.  <span data-ttu-id="15d8e-115">Щелкните **изменить выбранную производную иерархию**.</span><span class="sxs-lookup"><span data-stu-id="15d8e-115">Click **Edit selected derived hierarchy**.</span></span>  
  
6.  <span data-ttu-id="15d8e-116">На панели **Текущие уровни** :</span><span class="sxs-lookup"><span data-stu-id="15d8e-116">In the **Current Levels** pane:</span></span>  
  
    -   <span data-ttu-id="15d8e-117">Чтобы скрыть уровень, щелкните любой уровень (кроме верхнего и нижнего).</span><span class="sxs-lookup"><span data-stu-id="15d8e-117">To hide a level, click a level other than the top or bottom.</span></span> <span data-ttu-id="15d8e-118">В списке **Видимый** выберите **Нет**.</span><span class="sxs-lookup"><span data-stu-id="15d8e-118">From the **Visible** list, select **No**.</span></span> <span data-ttu-id="15d8e-119">Затем щелкните **Сохранить выбранный элемент иерархии**.</span><span class="sxs-lookup"><span data-stu-id="15d8e-119">Then click **Save selected hierarchy item**.</span></span>  
  
    -   <span data-ttu-id="15d8e-120">Чтобы удалить верхний уровень, щелкните **Удалить выбранный элемент иерархии**.</span><span class="sxs-lookup"><span data-stu-id="15d8e-120">To delete the top level, click **Delete selected hierarchy item**.</span></span> <span data-ttu-id="15d8e-121">В диалоговом окне подтверждения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="15d8e-121">In the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="15d8e-122">Можно удалить только верхний уровень.</span><span class="sxs-lookup"><span data-stu-id="15d8e-122">You can delete the top level only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15d8e-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="15d8e-123">See Also</span></span>  
 <span data-ttu-id="15d8e-124">[Перемещение элементов в иерархии &#40;Master Data Services&#41;](../../2014/master-data-services/move-members-within-a-hierarchy-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="15d8e-124">[Move Members within a Hierarchy &#40;Master Data Services&#41;](../../2014/master-data-services/move-members-within-a-hierarchy-master-data-services.md) </span></span>  
 [<span data-ttu-id="15d8e-125">Производные иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="15d8e-125">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-master-data-services.md)  
  
  

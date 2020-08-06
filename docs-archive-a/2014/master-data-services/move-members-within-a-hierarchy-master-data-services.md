---
title: Перемещение элементов в иерархии (Master Data Services) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- hierarchies [Master Data Services], moving members
- explicit hierarchies, moving members
- derived hierarchies, moving members
- members [Master Data Services], moving
ms.assetid: 049c9a15-89c1-478c-8438-028fffc9e187
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 37167f76b965197dbf8e37e365778395ec640d38
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658303"
---
# <a name="move-members-within-a-hierarchy-master-data-services"></a><span data-ttu-id="5c64e-102">Перемещение элементов в иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="5c64e-102">Move Members within a Hierarchy (Master Data Services)</span></span>
  <span data-ttu-id="5c64e-103">В службах [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] перемещение элементов в иерархии требуется для того, чтобы изменить местоположение элементов или родительский элемент.</span><span class="sxs-lookup"><span data-stu-id="5c64e-103">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], move members within a hierarchy to change their location or parent assignment.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5c64e-104">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="5c64e-104">Prerequisites</span></span>  
 <span data-ttu-id="5c64e-105">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="5c64e-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="5c64e-106">Необходимо иметь разрешение на доступ к функциональной области **Обозреватель** .</span><span class="sxs-lookup"><span data-stu-id="5c64e-106">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="5c64e-107">Для явных иерархий необходимо иметь как минимум разрешение **Обновление** для сущности.</span><span class="sxs-lookup"><span data-stu-id="5c64e-107">For explicit hierarchies, you must have a minimum of **Update** permission to the entity.</span></span>  
  
-   <span data-ttu-id="5c64e-108">Для производных иерархий необходимо иметь как минимум одно **Обновление** модели и всех атрибутов на основе домена, используемых в иерархии.</span><span class="sxs-lookup"><span data-stu-id="5c64e-108">For derived hierarchies, you must have a minimum of **Update** to the model and to any domain-based attributes used in the hierarchy.</span></span>  
  
### <a name="to-move-members-within-a-hierarchy"></a><span data-ttu-id="5c64e-109">Перемещение элементов в иерархии</span><span class="sxs-lookup"><span data-stu-id="5c64e-109">To move members within a hierarchy</span></span>  
  
1.  <span data-ttu-id="5c64e-110">На домашней странице [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] выберите модель в списке **Модель** .</span><span class="sxs-lookup"><span data-stu-id="5c64e-110">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="5c64e-111">Выберите версию из списка **Версия** .</span><span class="sxs-lookup"><span data-stu-id="5c64e-111">From the **Version** list, select a version.</span></span>  
  
3.  <span data-ttu-id="5c64e-112">Нажмите кнопку **Браузер**.</span><span class="sxs-lookup"><span data-stu-id="5c64e-112">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="5c64e-113">В строке меню наведите указатель мыши на **иерархии** и щелкните *hierarchy_name*.</span><span class="sxs-lookup"><span data-stu-id="5c64e-113">From the menu bar, point to **Hierarchies** and click *hierarchy_name*.</span></span>  
  
5.  <span data-ttu-id="5c64e-114">В области **Иерархия** , где иерархия отображается в древовидной структуре, установите флажок для каждого элемента, который требуется переместить.</span><span class="sxs-lookup"><span data-stu-id="5c64e-114">In the **Hierarchy** pane, where the hierarchy is displayed in a tree structure, click the check box for each member you want to move.</span></span>  
  
6.  <span data-ttu-id="5c64e-115">В верхней части панели **Иерархия** нажмите кнопку **Вырезать**.</span><span class="sxs-lookup"><span data-stu-id="5c64e-115">At the top of the **Hierarchy** pane, click **Cut**.</span></span>  
  
7.  <span data-ttu-id="5c64e-116">На панели **Иерархия** установите флажок для элемента, в который нужно переместить элементы.</span><span class="sxs-lookup"><span data-stu-id="5c64e-116">In the **Hierarchy** pane, click the check box for the member you want to move the members to.</span></span>  
  
8.  <span data-ttu-id="5c64e-117">Нажмите кнопку **Вставить**.</span><span class="sxs-lookup"><span data-stu-id="5c64e-117">Click **Paste**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5c64e-118">В производных иерархиях элементы можно перемещать только на том же уровне.</span><span class="sxs-lookup"><span data-stu-id="5c64e-118">In derived hierarchies, you can move members to the same level only.</span></span> <span data-ttu-id="5c64e-119">Кроме того, нельзя изменить порядок сортировки элементов.</span><span class="sxs-lookup"><span data-stu-id="5c64e-119">Also, you cannot change the sort order of members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c64e-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="5c64e-120">See Also</span></span>  
 <span data-ttu-id="5c64e-121">[Перемещение элементов явной иерархии с помощью промежуточного процесса &#40;Master Data Services&#41;](add-update-and-delete-data-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5c64e-121">[Move Explicit Hierarchy Members by Using the Staging Process &#40;Master Data Services&#41;](add-update-and-delete-data-master-data-services.md) </span></span>  
 <span data-ttu-id="5c64e-122">[Производные иерархии &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5c64e-122">[Derived Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-master-data-services.md) </span></span>  
 [<span data-ttu-id="5c64e-123">Явные иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="5c64e-123">Explicit Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)  
  
  

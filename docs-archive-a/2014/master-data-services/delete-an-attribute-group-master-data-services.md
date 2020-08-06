---
title: Удаление группы атрибутов (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deleting attribute groups [Master Data Services]
- attribute groups [Master Data Services], deleting
ms.assetid: f915e89b-629d-4725-aea6-a7f051978244
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 833c5cf327034b25d68af123a1fc134372bd6f10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668404"
---
# <a name="delete-an-attribute-group-master-data-services"></a><span data-ttu-id="c9bd0-102">Удаление группы атрибутов (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="c9bd0-102">Delete an Attribute Group (Master Data Services)</span></span>
  <span data-ttu-id="c9bd0-103">В службах [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]можно удалить группу атрибутов, если больше не нужна вкладка для отображения в функциональной области **Обозреватель** в среде [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9bd0-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete an attribute group when you no longer need the tab to display in the **Explorer** functional area of [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
-   <span data-ttu-id="c9bd0-104">**Примечание.** Если группы атрибутов существуют, то атрибуты, не принадлежащие ни к одной группе, не отображаются в окне **Обозреватель**.</span><span class="sxs-lookup"><span data-stu-id="c9bd0-104">**Note** When attribute groups exist, attributes that do not belong to an attribute group are not displayed in **Explorer**.</span></span> <span data-ttu-id="c9bd0-105">Если групп атрибутов не существует, то отображаются все атрибуты.</span><span class="sxs-lookup"><span data-stu-id="c9bd0-105">When no attribute groups exist, all attributes are displayed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c9bd0-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="c9bd0-106">Prerequisites</span></span>  
 <span data-ttu-id="c9bd0-107">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="c9bd0-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="c9bd0-108">Необходимо иметь разрешение на доступ к функциональной области **Администрирование системы** .</span><span class="sxs-lookup"><span data-stu-id="c9bd0-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="c9bd0-109">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="c9bd0-109">You must be a model administrator.</span></span> <span data-ttu-id="c9bd0-110">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c9bd0-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-an-attribute-group"></a><span data-ttu-id="c9bd0-111">Удаление группы атрибутов</span><span class="sxs-lookup"><span data-stu-id="c9bd0-111">To delete an attribute group</span></span>  
  
1.  <span data-ttu-id="c9bd0-112">В [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Администрирование системы**.</span><span class="sxs-lookup"><span data-stu-id="c9bd0-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="c9bd0-113">На странице **представление модели** в строке меню наведите указатель мыши на пункт **Управление** и щелкните **группы атрибутов**.</span><span class="sxs-lookup"><span data-stu-id="c9bd0-113">On the **Model View** page, from the menu bar, point to **Manage** and click **Attribute Groups**.</span></span>  
  
3.  <span data-ttu-id="c9bd0-114">Выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="c9bd0-114">From the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="c9bd0-115">Выберите сущность из списка **Сущность** .</span><span class="sxs-lookup"><span data-stu-id="c9bd0-115">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="c9bd0-116">Щелкните знак «плюс», чтобы развернуть **конечные группы**, **Объединенные группы**или **группы коллекций**в зависимости от типа группы, которую необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="c9bd0-116">Click the plus sign to expand **Leaf Groups**, **Consolidated Groups**, or **Collection Groups**, depending on the type of group you want to delete.</span></span>  
  
6.  <span data-ttu-id="c9bd0-117">Щелкните группу атрибутов, которую необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="c9bd0-117">Click the attribute group you want to delete.</span></span>  
  
7.  <span data-ttu-id="c9bd0-118">Нажмите кнопку **Удалить выбранную группу**.</span><span class="sxs-lookup"><span data-stu-id="c9bd0-118">Click **Delete selected group**.</span></span>  
  
8.  <span data-ttu-id="c9bd0-119">В диалоговом окне подтверждения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c9bd0-119">In the confirmation dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="c9bd0-120">В дополнительном диалоговом окне подтверждения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c9bd0-120">In the additional confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9bd0-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="c9bd0-121">See Also</span></span>  
 <span data-ttu-id="c9bd0-122">[Группы атрибутов &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="c9bd0-122">[Attribute Groups &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span></span>  
 [<span data-ttu-id="c9bd0-123">Создание группы атрибутов (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="c9bd0-123">Create an Attribute Group &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-attribute-group-master-data-services.md)  
  
  

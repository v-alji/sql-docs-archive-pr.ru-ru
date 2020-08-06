---
title: Изменение имени группы атрибутов (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attribute groups [Master Data Services], changing name
ms.assetid: 79510fcf-4c83-4426-bdd4-15b4170ecfbd
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 99278302ddda4b05a302b6edd5d724ab49ca5c0d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734230"
---
# <a name="change-an-attribute-group-name-master-data-services"></a><span data-ttu-id="3d600-102">Изменение имени группы атрибутов (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="3d600-102">Change an Attribute Group Name (Master Data Services)</span></span>
  <span data-ttu-id="3d600-103">В среде [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]можно изменить имя группы атрибутов.</span><span class="sxs-lookup"><span data-stu-id="3d600-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can change the name of an attribute group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3d600-104">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="3d600-104">Prerequisites</span></span>  
 <span data-ttu-id="3d600-105">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="3d600-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="3d600-106">Необходимо иметь разрешение на доступ к функциональной области **Администрирование системы** .</span><span class="sxs-lookup"><span data-stu-id="3d600-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="3d600-107">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="3d600-107">You must be a model administrator.</span></span> <span data-ttu-id="3d600-108">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3d600-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-change-an-attribute-group-name"></a><span data-ttu-id="3d600-109">Изменение имени группы атрибутов</span><span class="sxs-lookup"><span data-stu-id="3d600-109">To change an attribute group name</span></span>  
  
1.  <span data-ttu-id="3d600-110">В [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Администрирование системы**.</span><span class="sxs-lookup"><span data-stu-id="3d600-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="3d600-111">На странице **представление модели** в строке меню наведите указатель мыши на пункт **Управление** и щелкните **группы атрибутов**.</span><span class="sxs-lookup"><span data-stu-id="3d600-111">On the **Model View** page, from the menu bar, point to **Manage** and click **Attribute Groups**.</span></span>  
  
3.  <span data-ttu-id="3d600-112">Выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="3d600-112">From the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="3d600-113">Выберите сущность из списка **Сущность** .</span><span class="sxs-lookup"><span data-stu-id="3d600-113">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="3d600-114">Щелкните знак «плюс», чтобы развернуть **конечные группы**, **Объединенные группы**или **группы коллекций**в зависимости от типа группы, которую требуется обновить.</span><span class="sxs-lookup"><span data-stu-id="3d600-114">Click the plus sign to expand **Leaf Groups**, **Consolidated Groups**, or **Collection Groups**, depending on the type of group you want to update.</span></span>  
  
6.  <span data-ttu-id="3d600-115">Щелкните имя группы атрибутов, которое требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="3d600-115">Click the name of the attribute group with the name you want to change.</span></span>  
  
7.  <span data-ttu-id="3d600-116">Нажмите кнопку **изменить выбранный элемент**.</span><span class="sxs-lookup"><span data-stu-id="3d600-116">Click **Edit selected item**.</span></span>  
  
8.  <span data-ttu-id="3d600-117">В поле имя **конечной группы** , поле **имя консолидированной группы** или **имя группы коллекции** введите обновленное имя группы атрибутов.</span><span class="sxs-lookup"><span data-stu-id="3d600-117">In the **Leaf group name** box, **Consolidated group name** box, or **Collection group name** box, type the updated name of the attribute group.</span></span>  
  
9. <span data-ttu-id="3d600-118">Нажмите кнопку **Сохранить группу**.</span><span class="sxs-lookup"><span data-stu-id="3d600-118">Click **Save group**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d600-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="3d600-119">See Also</span></span>  
 <span data-ttu-id="3d600-120">[Группы атрибутов &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="3d600-120">[Attribute Groups &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span></span>  
 <span data-ttu-id="3d600-121">[Создание группы атрибутов &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-attribute-group-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="3d600-121">[Create an Attribute Group &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-attribute-group-master-data-services.md) </span></span>  
 [<span data-ttu-id="3d600-122">Удаление группы атрибутов (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="3d600-122">Delete an Attribute Group &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-an-attribute-group-master-data-services.md)  
  
  

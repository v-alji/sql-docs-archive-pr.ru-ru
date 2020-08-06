---
title: Превращение группы атрибутов в видимую для пользователей (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: b2f6cc27-dbc9-4f3f-961e-e81e76375248
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 309ad0392cd717d4a8a11470621144ef9e604fd9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654389"
---
# <a name="make-an-attribute-group-visible-to-users-master-data-services"></a><span data-ttu-id="9dd83-102">Превращение группы атрибутов в видимую для пользователей (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="9dd83-102">Make an Attribute Group Visible to Users (Master Data Services)</span></span>
  <span data-ttu-id="9dd83-103">В [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]сделайте группу атрибутов видимой для пользователей или групп, если необходимо, чтобы у пользователей присутствовали вкладки над сеткой в функциональной области **Обозреватель** .</span><span class="sxs-lookup"><span data-stu-id="9dd83-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], make an attribute group visible to users or groups when you want users to have tabs above the grid in the **Explorer** functional area.</span></span>  
  
 <span data-ttu-id="9dd83-104">При создании группы атрибутов она автоматически скрыта от всех пользователей, кроме того, кто ее создал.</span><span class="sxs-lookup"><span data-stu-id="9dd83-104">When you create an attribute group, it is automatically hidden from all users except the one who created it.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9dd83-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="9dd83-105">Prerequisites</span></span>  
 <span data-ttu-id="9dd83-106">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="9dd83-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="9dd83-107">Необходимо иметь разрешение на доступ к функциональной области **Администрирование системы** .</span><span class="sxs-lookup"><span data-stu-id="9dd83-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="9dd83-108">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="9dd83-108">You must be a model administrator.</span></span> <span data-ttu-id="9dd83-109">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9dd83-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="9dd83-110">Должна существовать хотя бы одна группа атрибутов.</span><span class="sxs-lookup"><span data-stu-id="9dd83-110">At least one attribute group must exist.</span></span> <span data-ttu-id="9dd83-111">Дополнительные сведения см. в статье [Создание группы атрибутов (службы Master Data Services)](../../2014/master-data-services/create-an-attribute-group-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9dd83-111">For more information, see [Create an Attribute Group &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-attribute-group-master-data-services.md).</span></span>  
  
### <a name="to-make-an-attribute-group-visible-to-users"></a><span data-ttu-id="9dd83-112">Превращение группы атрибутов в видимую для пользователей</span><span class="sxs-lookup"><span data-stu-id="9dd83-112">To make an attribute group visible to users</span></span>  
  
1.  <span data-ttu-id="9dd83-113">В [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Администрирование системы**.</span><span class="sxs-lookup"><span data-stu-id="9dd83-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="9dd83-114">На странице **представление модели** в строке меню наведите указатель мыши на пункт **Управление** и щелкните **группы атрибутов**.</span><span class="sxs-lookup"><span data-stu-id="9dd83-114">On the **Model View** page, from the menu bar, point to **Manage** and click **Attribute Groups**.</span></span>  
  
3.  <span data-ttu-id="9dd83-115">Выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="9dd83-115">From the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="9dd83-116">Выберите сущность из списка **Сущность** .</span><span class="sxs-lookup"><span data-stu-id="9dd83-116">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="9dd83-117">Щелкните знак «плюс», чтобы развернуть **конечные группы**, **Объединенные группы**или **группы коллекций**в зависимости от типа группы, которую необходимо сделать видимой.</span><span class="sxs-lookup"><span data-stu-id="9dd83-117">Click the plus sign to expand **Leaf Groups**, **Consolidated Groups**, or **Collection Groups**, depending on the type of group you want to make visible.</span></span>  
  
6.  <span data-ttu-id="9dd83-118">Щелкните значок «плюс», чтобы развернуть группу, которую нужно сделать видимой.</span><span class="sxs-lookup"><span data-stu-id="9dd83-118">Click the plus sign to expand the group you want to make visible.</span></span>  
  
7.  <span data-ttu-id="9dd83-119">Щелкните **Пользователи** или **группы**в зависимости от того, становится ли группа видимой для пользователя или группы.</span><span class="sxs-lookup"><span data-stu-id="9dd83-119">Click either **Users** or **Groups**, depending on whether you are making the group visible to a user or a group.</span></span>  
  
8.  <span data-ttu-id="9dd83-120">Нажмите кнопку **изменить выбранный элемент**.</span><span class="sxs-lookup"><span data-stu-id="9dd83-120">Click **Edit selected item**.</span></span>  
  
9. <span data-ttu-id="9dd83-121">Щелкните Пользователи или группы в поле **доступно** и щелкните стрелку **Добавить** .</span><span class="sxs-lookup"><span data-stu-id="9dd83-121">Click users or groups in the **Available** box and click the **Add** arrow.</span></span> <span data-ttu-id="9dd83-122">Чтобы добавить все, щелкните стрелку **Добавить все** .</span><span class="sxs-lookup"><span data-stu-id="9dd83-122">To add all, click the **Add All** arrow.</span></span>  
  
10. <span data-ttu-id="9dd83-123">Выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9dd83-123">Click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dd83-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="9dd83-124">See Also</span></span>  
 <span data-ttu-id="9dd83-125">[Группы атрибутов &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="9dd83-125">[Attribute Groups &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span></span>  
 [<span data-ttu-id="9dd83-126">Создание группы атрибутов (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="9dd83-126">Create an Attribute Group &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-attribute-group-master-data-services.md)  
  
  

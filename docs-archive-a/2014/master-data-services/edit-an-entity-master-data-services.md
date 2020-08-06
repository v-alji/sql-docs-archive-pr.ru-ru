---
title: Изменение имени сущности (Master Data Services) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- entities [Master Data Services], changing name
ms.assetid: 6a5b9f14-6dfc-49d7-a771-e96461d4feae
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9690fde44b0d56d790f4340779167fb55b400223
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728402"
---
# <a name="change-an-entity-name-master-data-services"></a><span data-ttu-id="df691-102">Изменение имени сущности (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="df691-102">Change an Entity Name (Master Data Services)</span></span>
  <span data-ttu-id="df691-103">В [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] имя сущности можно изменять.</span><span class="sxs-lookup"><span data-stu-id="df691-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can change the name of an entity.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="df691-104">Имена связанных промежуточных таблиц не будут обновлены.</span><span class="sxs-lookup"><span data-stu-id="df691-104">The names of the associated staging tables will not be updated.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="df691-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="df691-105">Prerequisites</span></span>  
 <span data-ttu-id="df691-106">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="df691-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="df691-107">Необходимо иметь разрешение на доступ к функциональной области **Администрирование системы** .</span><span class="sxs-lookup"><span data-stu-id="df691-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="df691-108">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="df691-108">You must be a model administrator.</span></span> <span data-ttu-id="df691-109">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="df691-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-change-an-entity-name"></a><span data-ttu-id="df691-110">Изменение имени сущности</span><span class="sxs-lookup"><span data-stu-id="df691-110">To change an entity name</span></span>  
  
1.  <span data-ttu-id="df691-111">В [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Администрирование системы**.</span><span class="sxs-lookup"><span data-stu-id="df691-111">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="df691-112">На странице **Представление модели** в строке меню наведите курсор на **Управление** и щелкните **Сущности**.</span><span class="sxs-lookup"><span data-stu-id="df691-112">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="df691-113">На странице **Обслуживание сущности** выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="df691-113">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="df691-114">Выберите строку, где указано имя сущности, которое требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="df691-114">Click the row for the entity with the name you want to change.</span></span>  
  
5.  <span data-ttu-id="df691-115">Щелкните **Изменить выбранную сущность**.</span><span class="sxs-lookup"><span data-stu-id="df691-115">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="df691-116">В поле **имя сущности** введите обновленное имя сущности.</span><span class="sxs-lookup"><span data-stu-id="df691-116">In the **Entity name** box, type the updated name of the entity.</span></span>  
  
7.  <span data-ttu-id="df691-117">Нажмите кнопку **Сохранить сущность**.</span><span class="sxs-lookup"><span data-stu-id="df691-117">Click **Save entity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df691-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="df691-118">See Also</span></span>  
 <span data-ttu-id="df691-119">[Создание сущности &#40;Master Data Services&#41;](create-an-entity-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="df691-119">[Create an Entity &#40;Master Data Services&#41;](create-an-entity-master-data-services.md) </span></span>  
 <span data-ttu-id="df691-120">[Удаление сущности &#40;Master Data Services&#41;](delete-an-entity-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="df691-120">[Delete an Entity &#40;Master Data Services&#41;](delete-an-entity-master-data-services.md) </span></span>  
 [<span data-ttu-id="df691-121">Сущности (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="df691-121">Entities &#40;Master Data Services&#41;</span></span>](entities-master-data-services.md)  
  
  

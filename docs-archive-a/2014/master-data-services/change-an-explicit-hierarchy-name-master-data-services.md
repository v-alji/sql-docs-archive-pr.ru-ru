---
title: Изменение имени явной иерархии (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- explicit hierarchies, changing name
ms.assetid: 12991603-474e-4042-b160-b1f7979694b1
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3cb8d1108650395ebd970edbb2ea31f5daebbd27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736479"
---
# <a name="change-an-explicit-hierarchy-name-master-data-services"></a><span data-ttu-id="3bff1-102">Изменение имени явной иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="3bff1-102">Change an Explicit Hierarchy Name (Master Data Services)</span></span>
  <span data-ttu-id="3bff1-103">В службах [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]можно изменить имя явной иерархии.</span><span class="sxs-lookup"><span data-stu-id="3bff1-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can change the name of an explicit hierarchy.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3bff1-104">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="3bff1-104">Prerequisites</span></span>  
 <span data-ttu-id="3bff1-105">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="3bff1-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="3bff1-106">Необходимо иметь разрешение на доступ к функциональной области **Администрирование системы** .</span><span class="sxs-lookup"><span data-stu-id="3bff1-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="3bff1-107">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="3bff1-107">You must be a model administrator.</span></span> <span data-ttu-id="3bff1-108">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3bff1-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-change-the-name-of-an-explicit-hierarchy"></a><span data-ttu-id="3bff1-109">Изменение имени явной иерархии</span><span class="sxs-lookup"><span data-stu-id="3bff1-109">To change the name of an explicit hierarchy</span></span>  
  
1.  <span data-ttu-id="3bff1-110">В [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Администрирование системы**.</span><span class="sxs-lookup"><span data-stu-id="3bff1-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="3bff1-111">На странице **Представление модели** в строке меню наведите курсор на **Управление** и щелкните **Сущности**.</span><span class="sxs-lookup"><span data-stu-id="3bff1-111">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="3bff1-112">На странице **Обслуживание сущности** выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="3bff1-112">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="3bff1-113">Выберите строку сущности, содержащей явную иерархию, которую необходимо переименовать.</span><span class="sxs-lookup"><span data-stu-id="3bff1-113">Select the row for the entity that contains the explicit hierarchy you want to rename.</span></span>  
  
5.  <span data-ttu-id="3bff1-114">Щелкните **Изменить выбранную сущность**.</span><span class="sxs-lookup"><span data-stu-id="3bff1-114">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="3bff1-115">На странице **Изменение сущности** щелкните явную иерархию, которую нужно переименовать.</span><span class="sxs-lookup"><span data-stu-id="3bff1-115">On the **Edit Entity** page, click the explicit hierarchy you want to rename.</span></span>  
  
7.  <span data-ttu-id="3bff1-116">Нажмите кнопку **изменить выбранную иерархию**.</span><span class="sxs-lookup"><span data-stu-id="3bff1-116">Click **Edit selected hierarchy**.</span></span>  
  
8.  <span data-ttu-id="3bff1-117">В поле **имя явной иерархии** введите новое имя иерархии.</span><span class="sxs-lookup"><span data-stu-id="3bff1-117">In the **Explicit hierarchy name** box, type the updated name of the hierarchy.</span></span>  
  
9. <span data-ttu-id="3bff1-118">Нажмите кнопку **Сохранить иерархию**.</span><span class="sxs-lookup"><span data-stu-id="3bff1-118">Click **Save hierarchy**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bff1-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="3bff1-119">See Also</span></span>  
 <span data-ttu-id="3bff1-120">[Явные иерархии &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="3bff1-120">[Explicit Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span></span>  
 <span data-ttu-id="3bff1-121">[Создание явной иерархии &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="3bff1-121">[Create an Explicit Hierarchy &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md) </span></span>  
 [<span data-ttu-id="3bff1-122">Удаление явной иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="3bff1-122">Delete an Explicit Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-an-explicit-hierarchy-master-data-services.md)  
  
  

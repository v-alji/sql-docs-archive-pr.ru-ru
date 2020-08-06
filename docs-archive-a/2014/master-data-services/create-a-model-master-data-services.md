---
title: Создание модели (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- models [Master Data Services], creating models
- creating models [Master Data Services]
ms.assetid: 9bb3b3b3-bde8-44aa-ad62-eaae21188141
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 07b2f44798a689a7ceca7ec39a2ffc95f015d9b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666112"
---
# <a name="create-a-model-master-data-services"></a><span data-ttu-id="7b9ee-102">Создание модели (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="7b9ee-102">Create a Model (Master Data Services)</span></span>
  <span data-ttu-id="7b9ee-103">В среде [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]модель создается для того, чтобы содержать объекты.</span><span class="sxs-lookup"><span data-stu-id="7b9ee-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a model to contain model objects.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7b9ee-104">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="7b9ee-104">Prerequisites</span></span>  
 <span data-ttu-id="7b9ee-105">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="7b9ee-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="7b9ee-106">Необходимо иметь разрешение на доступ к функциональной области **Администрирование системы** .</span><span class="sxs-lookup"><span data-stu-id="7b9ee-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
### <a name="to-create-a-model"></a><span data-ttu-id="7b9ee-107">Создание модели</span><span class="sxs-lookup"><span data-stu-id="7b9ee-107">To create a model</span></span>  
  
1.  <span data-ttu-id="7b9ee-108">В [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Администрирование системы**.</span><span class="sxs-lookup"><span data-stu-id="7b9ee-108">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="7b9ee-109">На странице **Представление модели** в строке меню наведите указатель мыши на **Управление** и щелкните **Модели**.</span><span class="sxs-lookup"><span data-stu-id="7b9ee-109">On the **Model View** page, from the menu bar, point to **Manage** and click **Models**.</span></span>  
  
3.  <span data-ttu-id="7b9ee-110">На странице **Обслуживание модели** нажмите кнопку **Добавить модель**.</span><span class="sxs-lookup"><span data-stu-id="7b9ee-110">On the **Model Maintenance** page, click **Add model**.</span></span>  
  
4.  <span data-ttu-id="7b9ee-111">В поле **имя модели** введите имя модели.</span><span class="sxs-lookup"><span data-stu-id="7b9ee-111">In the **Model name** box, type the name of the model.</span></span>  
  
5.  <span data-ttu-id="7b9ee-112">По желанию выберите параметр **Создать сущность с именем модели** для создания сущности с тем же именем, что и у модели.</span><span class="sxs-lookup"><span data-stu-id="7b9ee-112">Optionally, select **Create entity with same name as model** to create an entity with the same name as the model.</span></span>  
  
6.  <span data-ttu-id="7b9ee-113">При необходимости выберите **создать явную иерархию с тем же именем, что и модель** , чтобы создать явную иерархию с тем же именем, что и у модели.</span><span class="sxs-lookup"><span data-stu-id="7b9ee-113">Optionally, select **Create explicit hierarchy with same name as model** to create an explicit hierarchy with the same name as the model.</span></span> <span data-ttu-id="7b9ee-114">Этот параметр также активирует сущность для коллекций.</span><span class="sxs-lookup"><span data-stu-id="7b9ee-114">This option also enables the entity for collections.</span></span>  
  
7.  <span data-ttu-id="7b9ee-115">При необходимости выберите **обязательная иерархия (все конечные элементы будут включены** для создания явной иерархии в качестве обязательной иерархии).</span><span class="sxs-lookup"><span data-stu-id="7b9ee-115">Optionally, select **Mandatory hierarchy (all leaf members are included** to create the explicit hierarchy as a mandatory hierarchy.</span></span>  
  
8.  <span data-ttu-id="7b9ee-116">Нажмите **Сохранить модель**.</span><span class="sxs-lookup"><span data-stu-id="7b9ee-116">Click **Save model**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7b9ee-117">Next Steps</span><span class="sxs-lookup"><span data-stu-id="7b9ee-117">Next Steps</span></span>  
  
-   [<span data-ttu-id="7b9ee-118">Создание сущности (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="7b9ee-118">Create an Entity &#40;Master Data Services&#41;</span></span>](create-an-entity-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="7b9ee-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="7b9ee-119">See Also</span></span>  
 <span data-ttu-id="7b9ee-120">[Модели &#40;Master Data Services&#41;](../../2014/master-data-services/models-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="7b9ee-120">[Models &#40;Master Data Services&#41;](../../2014/master-data-services/models-master-data-services.md) </span></span>  
 <span data-ttu-id="7b9ee-121">[Сущности &#40;Master Data Services&#41;](../../2014/master-data-services/entities-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="7b9ee-121">[Entities &#40;Master Data Services&#41;](../../2014/master-data-services/entities-master-data-services.md) </span></span>  
 <span data-ttu-id="7b9ee-122">[Удаление &#40;модели Master Data Services&#41;](../../2014/master-data-services/delete-a-model-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="7b9ee-122">[Delete a Model &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-model-master-data-services.md) </span></span>  
 [<span data-ttu-id="7b9ee-123">Измените имя модели &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7b9ee-123">Change a Model Name &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/change-a-model-name-master-data-services.md)  
  
  

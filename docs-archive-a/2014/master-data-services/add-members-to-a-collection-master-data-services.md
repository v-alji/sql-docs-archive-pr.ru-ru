---
title: Добавление элементов в коллекцию (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- collections [Master Data Services], adding members
ms.assetid: 1a7155e6-2d4a-4ed1-a72c-edb37fa1a46b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ce2038f3bc90a2f17506b0aadaaf9707fa911896
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668413"
---
# <a name="add-members-to-a-collection-master-data-services"></a><span data-ttu-id="58509-102">Добавление элементов в коллекцию (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="58509-102">Add Members to a Collection (Master Data Services)</span></span>
  <span data-ttu-id="58509-103">В [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]в коллекцию можно добавлять конечные и консолидированные элементы.</span><span class="sxs-lookup"><span data-stu-id="58509-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can add leaf and consolidated members to a collection.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="58509-104">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="58509-104">Prerequisites</span></span>  
 <span data-ttu-id="58509-105">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="58509-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="58509-106">Необходимо иметь разрешение на доступ к функциональной области **Обозреватель** .</span><span class="sxs-lookup"><span data-stu-id="58509-106">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="58509-107">как минимум необходимо разрешение **Обновление** на объект модели коллекции, к которому нужно добавить элементы;</span><span class="sxs-lookup"><span data-stu-id="58509-107">You must have a minimum of **Update** permission to the collection model object that you are adding members to.</span></span>  
  
-   <span data-ttu-id="58509-108">коллекция должна существовать.</span><span class="sxs-lookup"><span data-stu-id="58509-108">A collection must exist.</span></span> <span data-ttu-id="58509-109">Дополнительные сведения см. в разделе [Создание коллекции (службы Master Data Services)](create-a-collection-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="58509-109">For more information, see [Create a Collection &#40;Master Data Services&#41;](create-a-collection-master-data-services.md).</span></span>  
  
### <a name="to-add-members-to-a-collection"></a><span data-ttu-id="58509-110">Добавление элементов в коллекцию</span><span class="sxs-lookup"><span data-stu-id="58509-110">To add members to a collection</span></span>  
  
1.  <span data-ttu-id="58509-111">На домашней странице [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] выберите модель в списке **Модель** .</span><span class="sxs-lookup"><span data-stu-id="58509-111">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="58509-112">Выберите версию из списка **Версия** .</span><span class="sxs-lookup"><span data-stu-id="58509-112">From the **Version** list, select a version.</span></span>  
  
3.  <span data-ttu-id="58509-113">Нажмите кнопку **Браузер**.</span><span class="sxs-lookup"><span data-stu-id="58509-113">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="58509-114">В строке меню наведите указатель на меню **Коллекции** и выберите пункт *entity_name*.</span><span class="sxs-lookup"><span data-stu-id="58509-114">From the menu bar, point to **Collections** and click *entity_name*.</span></span>  
  
5.  <span data-ttu-id="58509-115">В сетке щелкните строку коллекции, в которую необходимо добавить элементы.</span><span class="sxs-lookup"><span data-stu-id="58509-115">In the grid, click the row for the collection you want to add members to.</span></span>  
  
6.  <span data-ttu-id="58509-116">Перейдите на вкладку **Членство в коллекциях** .</span><span class="sxs-lookup"><span data-stu-id="58509-116">Click the **Collection Members** tab.</span></span>  
  
7.  <span data-ttu-id="58509-117">Нажмите кнопку **Изменить элементы**.</span><span class="sxs-lookup"><span data-stu-id="58509-117">Click **Edit Members**.</span></span>  
  
8.  <span data-ttu-id="58509-118">Для фильтрации списка доступных элементов осуществите выбор в списке слева.</span><span class="sxs-lookup"><span data-stu-id="58509-118">To filter the list of available members, select from the list on the left.</span></span>  
  
9. <span data-ttu-id="58509-119">Выберите строку с элементом, который требуется добавить, и нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="58509-119">Click the row with the member you want to add and click **Add**.</span></span>  
  
10. <span data-ttu-id="58509-120">При необходимости можно изменить расположение элементов коллекции с помощью кнопок **Вверх** или **Вниз**.</span><span class="sxs-lookup"><span data-stu-id="58509-120">Optionally, rearrange collection members by clicking **Up** or **Down**.</span></span>  
  
11. <span data-ttu-id="58509-121">При необходимости установите взвешенные значения, щелкнув значение в столбце **Вес** .</span><span class="sxs-lookup"><span data-stu-id="58509-121">Optionally, set weight values by clicking the value in the **Weight** column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58509-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="58509-122">See Also</span></span>  
 [<span data-ttu-id="58509-123">Коллекции (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="58509-123">Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collections-master-data-services.md)  
  
  

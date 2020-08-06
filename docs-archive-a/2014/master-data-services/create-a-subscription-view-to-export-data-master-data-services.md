---
title: Создание представления подписки (Master Data Services) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- subscription views [Master Data Services], creating
- creating subscription views [Master Data Services]
ms.assetid: a5e28961-af16-414a-9845-d2e06aac5214
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: e5e2b901e56d75e97a444fd2858ef95872f3b766
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666110"
---
# <a name="create-a-subscription-view-master-data-services"></a><span data-ttu-id="ade57-102">Создание представления подписки (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="ade57-102">Create a Subscription View (Master Data Services)</span></span>
  <span data-ttu-id="ade57-103">Создайте представление подписки, если необходимо создать представление данных в [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] базе данных для использования в системах-подписчиках.</span><span class="sxs-lookup"><span data-stu-id="ade57-103">Create a subscription view when you want to create a view of your data in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database for use by subscribing systems.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ade57-104">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="ade57-104">Prerequisites</span></span>  
 <span data-ttu-id="ade57-105">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="ade57-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="ade57-106">необходимо разрешение на доступ к функциональной области **Управление интеграцией** ;</span><span class="sxs-lookup"><span data-stu-id="ade57-106">You must have permission to access the **Integration Management** functional area.</span></span>  
  
-   <span data-ttu-id="ade57-107">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="ade57-107">You must be a model administrator.</span></span> <span data-ttu-id="ade57-108">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ade57-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-create-a-subscription-view"></a><span data-ttu-id="ade57-109">Создание представления подписки</span><span class="sxs-lookup"><span data-stu-id="ade57-109">To create a subscription view</span></span>  
  
1.  <span data-ttu-id="ade57-110">В [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Управление интеграцией**.</span><span class="sxs-lookup"><span data-stu-id="ade57-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **Integration Management**.</span></span>  
  
2.  <span data-ttu-id="ade57-111">В строке меню щелкните **Создание представлений**.</span><span class="sxs-lookup"><span data-stu-id="ade57-111">From the menu bar, click **Create Views**.</span></span>  
  
3.  <span data-ttu-id="ade57-112">На странице **представления подписки** щелкните **Добавить представление подписки**.</span><span class="sxs-lookup"><span data-stu-id="ade57-112">On the **Subscription Views** page, click **Add subscription view**.</span></span>  
  
4.  <span data-ttu-id="ade57-113">В области **Создание представления подписки** в поле **имя представления подписки** введите имя представления.</span><span class="sxs-lookup"><span data-stu-id="ade57-113">In the **Create Subscription View** pane, in the **Subscription view name** box, type a name for the view.</span></span>  
  
5.  <span data-ttu-id="ade57-114">Выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="ade57-114">From the **Model** list, select a model.</span></span>  
  
6.  <span data-ttu-id="ade57-115">Выберите параметр **версия** или **флаг версии** , а затем выберите из соответствующего списка.</span><span class="sxs-lookup"><span data-stu-id="ade57-115">Select either the **Version** or **Version Flag** option, and then select from the corresponding list.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="ade57-116">Создайте представление подписки на основе флага версии.</span><span class="sxs-lookup"><span data-stu-id="ade57-116">Create a subscription view based on a version flag.</span></span> <span data-ttu-id="ade57-117">При блокировании версии флаг можно переприсвоить открытой версии, не обновляя представления подписки.</span><span class="sxs-lookup"><span data-stu-id="ade57-117">When you lock a version, you can reassign the flag to an open version without updating the subscription view.</span></span>  
  
7.  <span data-ttu-id="ade57-118">Выберите параметр **сущность** или **производная иерархия** , а затем выберите из соответствующего списка.</span><span class="sxs-lookup"><span data-stu-id="ade57-118">Select either the **Entity** or **Derived hierarchy** option, and then select from the corresponding list.</span></span>  
  
8.  <span data-ttu-id="ade57-119">Выберите формат представления подписки из списка **Формат** .</span><span class="sxs-lookup"><span data-stu-id="ade57-119">From the **Format** list, select a subscription view format.</span></span>  
  
9. <span data-ttu-id="ade57-120">Если выбрано значение из списка **Формат\*\*\*\*Явные уровни** или **Производные уровни** , то введите число уровней в иерархии для включения в представление.</span><span class="sxs-lookup"><span data-stu-id="ade57-120">If you chose **Explicit levels** or **Derived levels** from the **Format** list, type the number of levels in the hierarchy to include in the view.</span></span>  
  
10. <span data-ttu-id="ade57-121">Выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ade57-121">Click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ade57-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="ade57-122">See Also</span></span>  
 <span data-ttu-id="ade57-123">[Экспорт Master Data Services &#40;данных&#41;](overview-exporting-data-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="ade57-123">[Exporting Data &#40;Master Data Services&#41;](overview-exporting-data-master-data-services.md) </span></span>  
 <span data-ttu-id="ade57-124">[Удаление представления подписки &#40;Master Data Services&#41;](delete-a-subscription-view-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="ade57-124">[Delete a Subscription View &#40;Master Data Services&#41;](delete-a-subscription-view-master-data-services.md) </span></span>  
 [<span data-ttu-id="ade57-125">Создание флага версии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="ade57-125">Create a Version Flag &#40;Master Data Services&#41;</span></span>](create-a-version-flag-master-data-services.md)  
  
  

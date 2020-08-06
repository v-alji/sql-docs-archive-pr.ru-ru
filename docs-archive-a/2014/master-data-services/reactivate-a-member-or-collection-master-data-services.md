---
title: Повторная активация элемента или коллекции (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- collections [Master Data Services], reactivating
- consolidated members [Master Data Services], reactivating
- reactivating members [Master Data Services]
- members [Master Data Services], reactivating
- reactivating collections [Master Data Services]
- leaf members [Master Data Services], reactivating
ms.assetid: bb4884c0-3658-4763-92d1-636804278b1c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c449a5a277128bbca6ae24e848bcf12cb0881968
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666712"
---
# <a name="reactivate-a-member-or-collection-master-data-services"></a><span data-ttu-id="40af9-102">Повторная активация элемента или коллекции (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="40af9-102">Reactivate a Member or Collection (Master Data Services)</span></span>
  <span data-ttu-id="40af9-103">В [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]можно повторно активировать элемент, который был:</span><span class="sxs-lookup"><span data-stu-id="40af9-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can reactivate a member that was either:</span></span>  
  
-   <span data-ttu-id="40af9-104">деактивирован в промежуточном процессе;</span><span class="sxs-lookup"><span data-stu-id="40af9-104">Deactivated by the staging process.</span></span>  
  
-   <span data-ttu-id="40af9-105">удален в MDS [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)];</span><span class="sxs-lookup"><span data-stu-id="40af9-105">Deleted in the MDS [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)].</span></span>  
  
-   <span data-ttu-id="40af9-106">удален в веб-приложении [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="40af9-106">Deleted in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application.</span></span>  
  
 <span data-ttu-id="40af9-107">При повторной активации элемента восстанавливаются его атрибуты и членство в иерархиях и коллекциях.</span><span class="sxs-lookup"><span data-stu-id="40af9-107">When you reactivate a member, its attributes and its membership in hierarchies and collections are restored.</span></span>  
  
 <span data-ttu-id="40af9-108">Также можно повторно активировать коллекции.</span><span class="sxs-lookup"><span data-stu-id="40af9-108">You can also reactivate collections.</span></span> <span data-ttu-id="40af9-109">При этом восстанавливаются атрибуты коллекции и принадлежащие к ней элементы.</span><span class="sxs-lookup"><span data-stu-id="40af9-109">When you do, the collection's attributes and the members that belong to the collection are restored.</span></span>  
  
 <span data-ttu-id="40af9-110">При повторной активации коллекции или элемента восстанавливаются все предыдущие транзакции.</span><span class="sxs-lookup"><span data-stu-id="40af9-110">When either a collection or member is reactivated, all previous transactions are restored.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="40af9-111">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="40af9-111">Prerequisites</span></span>  
 <span data-ttu-id="40af9-112">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="40af9-112">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="40af9-113">В [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]необходимо иметь разрешение на доступ к функциональной области **Управление версиями** .</span><span class="sxs-lookup"><span data-stu-id="40af9-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], you must have permission to the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="40af9-114">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="40af9-114">You must be a model administrator.</span></span> <span data-ttu-id="40af9-115">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="40af9-115">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-reactivate-a-member-or-collection"></a><span data-ttu-id="40af9-116">Повторная активация элемента или коллекции</span><span class="sxs-lookup"><span data-stu-id="40af9-116">To reactivate a member or collection</span></span>  
  
1.  <span data-ttu-id="40af9-117">На домашней странице [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] нажмите **Управление версиями**.</span><span class="sxs-lookup"><span data-stu-id="40af9-117">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="40af9-118">В строке меню выберите пункт **Транзакции**.</span><span class="sxs-lookup"><span data-stu-id="40af9-118">On the menu bar, click **Transactions**.</span></span>  
  
3.  <span data-ttu-id="40af9-119">На странице **Транзакции** выберите модель в списке **Модель** .</span><span class="sxs-lookup"><span data-stu-id="40af9-119">On the **Transactions** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="40af9-120">Выберите версию из списка **Версия** .</span><span class="sxs-lookup"><span data-stu-id="40af9-120">From the **Version** list, select a version.</span></span>  
  
5.  <span data-ttu-id="40af9-121">На панели **Транзакции** щелкните строку элемента или коллекции, которые необходимо повторно активировать.</span><span class="sxs-lookup"><span data-stu-id="40af9-121">In the **Transactions** pane, click the row for the member or collection you want to reactivate.</span></span> <span data-ttu-id="40af9-122">Эта строка должна иметь состояние **Активный** в столбце **Прежнее значение** и **Выключен** в столбце **Новое значение** .</span><span class="sxs-lookup"><span data-stu-id="40af9-122">This row should have **Active** displayed in the **Prior Value** column and **De-Activated** in the **New Value** column.</span></span>  
  
6.  <span data-ttu-id="40af9-123">Нажмите кнопку **Отменить транзакцию**.</span><span class="sxs-lookup"><span data-stu-id="40af9-123">Click **Reverse Transaction**.</span></span>  
  
7.  <span data-ttu-id="40af9-124">В диалоговом окне подтверждения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="40af9-124">On the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="40af9-125">Будет добавлена новая транзакция со значением **Активный** в столбце **Новое значение** .</span><span class="sxs-lookup"><span data-stu-id="40af9-125">A new transaction is added, showing **Active** in the **New Value** column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40af9-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="40af9-126">See Also</span></span>  
 <span data-ttu-id="40af9-127">[Отключение или удаление членов с помощью промежуточного процесса &#40;Master Data Services&#41;](add-update-and-delete-data-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="40af9-127">[Deactivate or Delete Members by Using the Staging Process &#40;Master Data Services&#41;](add-update-and-delete-data-master-data-services.md) </span></span>  
 <span data-ttu-id="40af9-128">[Удаление элемента или коллекции &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="40af9-128">[Delete a Member or Collection &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md) </span></span>  
 <span data-ttu-id="40af9-129">[Master Data Services &#40;членов&#41;](../../2014/master-data-services/members-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="40af9-129">[Members &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span></span>  
 [<span data-ttu-id="40af9-130">Коллекции (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="40af9-130">Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collections-master-data-services.md)  
  
  

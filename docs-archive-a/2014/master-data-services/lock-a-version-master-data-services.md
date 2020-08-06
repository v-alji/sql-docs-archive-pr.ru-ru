---
title: Блокировка версии (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- versions [Master Data Services], locking
- locking versions [Master Data Services]
ms.assetid: 7bb62a84-12d8-4b29-9b6e-6aa25410618e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 68ef979b14d9bd228c7ca89a260b31b2fc6efccd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738459"
---
# <a name="lock-a-version-master-data-services"></a><span data-ttu-id="61100-102">Блокировка версии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="61100-102">Lock a Version (Master Data Services)</span></span>
  <span data-ttu-id="61100-103">В среде [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]блокировка версии модели препятствует изменениям элементов модели и их атрибутов.</span><span class="sxs-lookup"><span data-stu-id="61100-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], lock a version of a model to prevent changes to the model's members and their attributes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="61100-104">Если версия заблокирована, администраторы модели могут по-прежнему добавлять, изменять и удалять элементы.</span><span class="sxs-lookup"><span data-stu-id="61100-104">When a version is locked, model administrators can continue to add, edit, and remove members.</span></span> <span data-ttu-id="61100-105">Другие пользователи с разрешениями для модели могут только просматривать элементы.</span><span class="sxs-lookup"><span data-stu-id="61100-105">Other users with permission to the model can view members only.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="61100-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="61100-106">Prerequisites</span></span>  
 <span data-ttu-id="61100-107">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="61100-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="61100-108">необходимо иметь разрешение на доступ к функциональной области **Управление версиями** ;</span><span class="sxs-lookup"><span data-stu-id="61100-108">You must have permission to access the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="61100-109">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="61100-109">You must be a model administrator.</span></span> <span data-ttu-id="61100-110">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="61100-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="61100-111">Версия должна быть в состоянии **Открыта**.</span><span class="sxs-lookup"><span data-stu-id="61100-111">The version's status must be **Open**.</span></span>  
  
### <a name="to-lock-a-version"></a><span data-ttu-id="61100-112">Блокировка версии</span><span class="sxs-lookup"><span data-stu-id="61100-112">To lock a version</span></span>  
  
1.  <span data-ttu-id="61100-113">В среде [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Управление версиями**.</span><span class="sxs-lookup"><span data-stu-id="61100-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="61100-114">На странице **Управление версиями** выберите строки для версии, которую необходимо заблокировать.</span><span class="sxs-lookup"><span data-stu-id="61100-114">On the **Manage Versions** page, select the row for the version that you want to lock.</span></span>  
  
3.  <span data-ttu-id="61100-115">Выберите пункт **Блокировка**.</span><span class="sxs-lookup"><span data-stu-id="61100-115">Click **Lock**.</span></span>  
  
4.  <span data-ttu-id="61100-116">В диалоговом окне подтверждения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="61100-116">In the confirmation dialog box, click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="61100-117">Next Steps</span><span class="sxs-lookup"><span data-stu-id="61100-117">Next Steps</span></span>  
  
-   [<span data-ttu-id="61100-118">Подтверждение исправления проблемы, обнаруженной при проверке на соответствие бизнес-правилам (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="61100-118">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
-   [<span data-ttu-id="61100-119">Фиксация версии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="61100-119">Commit a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/commit-a-version-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="61100-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="61100-120">See Also</span></span>  
 <span data-ttu-id="61100-121">[Версии &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="61100-121">[Versions &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span></span>  
 [<span data-ttu-id="61100-122">Разблокировка версии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="61100-122">Unlock a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/unlock-a-version-master-data-services.md)  
  
  

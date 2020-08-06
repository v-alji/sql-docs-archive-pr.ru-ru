---
title: Назначение флага версии (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- version flags [Master Data Services], assigning flags
- versions [Master Data Services], assigning flags
ms.assetid: 6629ec7e-32e7-4a1e-8b31-eb43c5923766
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 2de0d0d8d8ea96814e13b9123fe4fcd4782d6bef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668410"
---
# <a name="assign-a-flag-to-a-version-master-data-services"></a><span data-ttu-id="ccfc1-102">Назначение флага версии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="ccfc1-102">Assign a Flag to a Version (Master Data Services)</span></span>
  <span data-ttu-id="ccfc1-103">В среде [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]назначается флаг версии, чтобы указать версию, которую следует использовать пользователям или системам-подписчикам.</span><span class="sxs-lookup"><span data-stu-id="ccfc1-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], assign a flag to a version to indicate the version that users or subscribing systems should use.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ccfc1-104">Флаг можно назначить только одной версии в каждый момент времени.</span><span class="sxs-lookup"><span data-stu-id="ccfc1-104">Version flags can be assigned to only one version at a time.</span></span> <span data-ttu-id="ccfc1-105">Если назначить флаг, уже назначенный другой версии, то он переместится к выбранной версии.</span><span class="sxs-lookup"><span data-stu-id="ccfc1-105">If you assign a flag that is already assigned to another version, the flag is moved to the version you selected.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ccfc1-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="ccfc1-106">Prerequisites</span></span>  
 <span data-ttu-id="ccfc1-107">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="ccfc1-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="ccfc1-108">необходимо иметь разрешение на доступ к функциональной области **Управление версиями** ;</span><span class="sxs-lookup"><span data-stu-id="ccfc1-108">You must have permission to access the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="ccfc1-109">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="ccfc1-109">You must be a model administrator.</span></span> <span data-ttu-id="ccfc1-110">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ccfc1-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="ccfc1-111">Нужно создать флаг версии для назначения.</span><span class="sxs-lookup"><span data-stu-id="ccfc1-111">You must have created a version flag to assign.</span></span> <span data-ttu-id="ccfc1-112">Дополнительные сведения см. в статье [Создание флага версии (службы Master Data Services)](../../2014/master-data-services/create-a-version-flag-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ccfc1-112">For more information, see [Create a Version Flag &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-version-flag-master-data-services.md).</span></span>  
  
### <a name="to-assign-a-flag-to-a-version"></a><span data-ttu-id="ccfc1-113">Назначение флага версии</span><span class="sxs-lookup"><span data-stu-id="ccfc1-113">To assign a flag to a version</span></span>  
  
1.  <span data-ttu-id="ccfc1-114">В среде [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Управление версиями**.</span><span class="sxs-lookup"><span data-stu-id="ccfc1-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="ccfc1-115">На странице **Управление версиями** в строке версии, которой необходимо назначить флаг, дважды щелкните ячейку в столбце **Флаг** .</span><span class="sxs-lookup"><span data-stu-id="ccfc1-115">On the **Manage Versions** page, in the row for the version to which you want to assign a flag, double-click the cell in the **Flag** column.</span></span>  
  
3.  <span data-ttu-id="ccfc1-116">Выберите из списка флаг, который нужно назначить.</span><span class="sxs-lookup"><span data-stu-id="ccfc1-116">From the list, select the flag you want to assign.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ccfc1-117">Если нужный флаг недоступен, то, возможно, он доступен только для **зафиксированных** версий.</span><span class="sxs-lookup"><span data-stu-id="ccfc1-117">If the flag you want is not available, the flag might be available for **Committed** versions only.</span></span> <span data-ttu-id="ccfc1-118">Чтобы удостовериться в этом, перейдите на страницу **Управление флагами версии** и просмотрите поле **Только зафиксированные версии** флага.</span><span class="sxs-lookup"><span data-stu-id="ccfc1-118">To confirm, go to the **Manage Version Flags** page and view the **Committed Versions Only** field for the flag.</span></span>  
  
4.  <span data-ttu-id="ccfc1-119">Нажмите клавишу ВВОД, чтобы сохранить изменение.</span><span class="sxs-lookup"><span data-stu-id="ccfc1-119">Press ENTER to save the change.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccfc1-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="ccfc1-120">See Also</span></span>  
 <span data-ttu-id="ccfc1-121">[Создание флага версии &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-version-flag-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="ccfc1-121">[Create a Version Flag &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-version-flag-master-data-services.md) </span></span>  
 [<span data-ttu-id="ccfc1-122">Версии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="ccfc1-122">Versions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/versions-master-data-services.md)  
  
  

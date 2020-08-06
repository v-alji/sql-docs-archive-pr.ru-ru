---
title: Подтверждение версии, обнаруженной при проверке на соответствие бизнес-правилам (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- validating versions [Master Data Services]
- validating versions [Master Data Services], about validating versions
- versions [Master Data Services], validating
- business rules [Master Data Services], applying to all members
ms.assetid: 5aee7901-6d05-41d4-8bbb-c6f26791d1df
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 085fa071ca511c9d838c140547419bf87fb857bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658872"
---
# <a name="validate-a-version-against-business-rules-master-data-services"></a><span data-ttu-id="a0580-102">Подтверждение исправления проблемы, обнаруженной при проверке на соответствие бизнес-правилам (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="a0580-102">Validate a Version against Business Rules (Master Data Services)</span></span>
  <span data-ttu-id="a0580-103">В среде [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]проверьте версию на применение бизнес-правил ко всем элементам версии модели.</span><span class="sxs-lookup"><span data-stu-id="a0580-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], validate a version to apply business rules to all members in the model version.</span></span>  
  
 <span data-ttu-id="a0580-104">В этой процедуре объясняется, как использовать веб-приложение [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] для проверки данных.</span><span class="sxs-lookup"><span data-stu-id="a0580-104">This procedure explains how to use the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application to validate data.</span></span> <span data-ttu-id="a0580-105">Если имеется разрешение в базе данных MDS, вместо этого можно использовать хранимую процедуру.</span><span class="sxs-lookup"><span data-stu-id="a0580-105">If you have permission in the MDS database, you can use a stored procedure instead.</span></span> <span data-ttu-id="a0580-106">Дополнительные сведения см. в разделе [Проверка хранимых процедур (службы Master Data Services)](validation-stored-procedure-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="a0580-106">For more information, see [Validation Stored Procedure &#40;Master Data Services&#41;](validation-stored-procedure-master-data-services.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a0580-107">Чтобы версию можно было зафиксировать, все элементы должны успешно пройти проверку.</span><span class="sxs-lookup"><span data-stu-id="a0580-107">All members must pass validation before a version can be committed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a0580-108">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="a0580-108">Prerequisites</span></span>  
 <span data-ttu-id="a0580-109">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="a0580-109">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="a0580-110">необходимо иметь разрешение на доступ к функциональной области **Управление версиями** ;</span><span class="sxs-lookup"><span data-stu-id="a0580-110">You must have permission to access the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="a0580-111">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="a0580-111">You must be a model administrator.</span></span> <span data-ttu-id="a0580-112">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="a0580-112">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="a0580-113">Версия должна быть в состоянии **Открыта** или **Заблокирована**.</span><span class="sxs-lookup"><span data-stu-id="a0580-113">The version's status must be **Open** or **Locked**.</span></span>  
  
-   <span data-ttu-id="a0580-114">На странице **Проверка версий** должны существовать элементы, состояние которых отличается от **Проверка успешно пройдена**.</span><span class="sxs-lookup"><span data-stu-id="a0580-114">On the **Validate Versions** page, members must exist with a status other than **Validation succeeded**.</span></span>  
  
### <a name="to-validate-a-version"></a><span data-ttu-id="a0580-115">Проверка версии</span><span class="sxs-lookup"><span data-stu-id="a0580-115">To validate a version</span></span>  
  
1.  <span data-ttu-id="a0580-116">В среде [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Управление версиями**.</span><span class="sxs-lookup"><span data-stu-id="a0580-116">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="a0580-117">На странице **Управление версиями** в строке меню щелкните **Проверить версию**.</span><span class="sxs-lookup"><span data-stu-id="a0580-117">On the **Manage Versions** page, from the menu bar, click **Validate Version**.</span></span>  
  
3.  <span data-ttu-id="a0580-118">На странице **Проверка версий** выберите модель и версию, которые необходимо проверить.</span><span class="sxs-lookup"><span data-stu-id="a0580-118">On the **Validate Versions** page, select the model and version you want to validate.</span></span>  
  
4.  <span data-ttu-id="a0580-119">Нажмите кнопку **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="a0580-119">Click **Validate**.</span></span>  
  
5.  <span data-ttu-id="a0580-120">В диалоговом окне подтверждения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a0580-120">In the confirmation dialog box, click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a0580-121">Когда исчезнет индикатор выполнения, проверка версии будет закончена.</span><span class="sxs-lookup"><span data-stu-id="a0580-121">When the progress indicator is no longer displayed, the version has finished validation.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a0580-122">Next Steps</span><span class="sxs-lookup"><span data-stu-id="a0580-122">Next Steps</span></span>  
  
-   [<span data-ttu-id="a0580-123">Блокировка версии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="a0580-123">Lock a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/lock-a-version-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="a0580-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="a0580-124">See Also</span></span>  
 <span data-ttu-id="a0580-125">[Состояния проверки &#40;Master Data Services&#41;](../../2014/master-data-services/validation-statuses-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="a0580-125">[Validation Statuses &#40;Master Data Services&#41;](../../2014/master-data-services/validation-statuses-master-data-services.md) </span></span>  
 <span data-ttu-id="a0580-126">[Master Data Services &#40;хранимой процедуры проверки&#41;](validation-stored-procedure-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="a0580-126">[Validation Stored Procedure &#40;Master Data Services&#41;](validation-stored-procedure-master-data-services.md) </span></span>  
 <span data-ttu-id="a0580-127">[Версии &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="a0580-127">[Versions &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span></span>  
 <span data-ttu-id="a0580-128">[Бизнес-правила &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="a0580-128">[Business Rules &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span></span>  
 [<span data-ttu-id="a0580-129">Подтверждение конкретных членов, обнаруженных при проверке на соответствие бизнес-правилам (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="a0580-129">Validate Specific Members against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
  

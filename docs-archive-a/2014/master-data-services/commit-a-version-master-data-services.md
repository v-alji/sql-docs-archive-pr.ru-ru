---
title: Фиксация версии (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- committing versions [Master Data Services]
- versions [Master Data Services], committing
ms.assetid: 6b967a39-b333-4b84-9e5f-4fb07e156826
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: cec3244d4ddaa78d9168e3ede503fa16756633a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731858"
---
# <a name="commit-a-version-master-data-services"></a><span data-ttu-id="f8b11-102">Фиксация версии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="f8b11-102">Commit a Version (Master Data Services)</span></span>
  <span data-ttu-id="f8b11-103">В среде [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]фиксация версии модели препятствует изменениям элементов модели и их атрибутов.</span><span class="sxs-lookup"><span data-stu-id="f8b11-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], commit a version of a model to prevent changes to the model's members and their attributes.</span></span> <span data-ttu-id="f8b11-104">Открыть зафиксированную версию нельзя.</span><span class="sxs-lookup"><span data-stu-id="f8b11-104">Committed versions cannot be unlocked.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f8b11-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="f8b11-105">Prerequisites</span></span>  
 <span data-ttu-id="f8b11-106">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="f8b11-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="f8b11-107">необходимо иметь разрешение на доступ к функциональной области **Управление версиями** ;</span><span class="sxs-lookup"><span data-stu-id="f8b11-107">You must have permission to access the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="f8b11-108">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="f8b11-108">You must be a model administrator.</span></span> <span data-ttu-id="f8b11-109">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f8b11-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="f8b11-110">Версия должна иметь состояние **Заблокирована**.</span><span class="sxs-lookup"><span data-stu-id="f8b11-110">The version's status must be **Locked**.</span></span> <span data-ttu-id="f8b11-111">Дополнительные сведения см. в статье [Блокировка версии (службы Master Data Services)](../../2014/master-data-services/lock-a-version-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f8b11-111">For more information, see [Lock a Version &#40;Master Data Services&#41;](../../2014/master-data-services/lock-a-version-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="f8b11-112">Все элементы должны пройти проверку.</span><span class="sxs-lookup"><span data-stu-id="f8b11-112">All members must have validated successfully.</span></span>  
  
### <a name="to-commit-a-version"></a><span data-ttu-id="f8b11-113">Фиксация версии</span><span class="sxs-lookup"><span data-stu-id="f8b11-113">To commit a version</span></span>  
  
1.  <span data-ttu-id="f8b11-114">В среде [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Управление версиями**.</span><span class="sxs-lookup"><span data-stu-id="f8b11-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="f8b11-115">На странице **Управление версиями** в строке меню щелкните **Проверить версию**.</span><span class="sxs-lookup"><span data-stu-id="f8b11-115">On the **Manage Versions** page, on the menu bar, click **Validate Version**.</span></span>  
  
3.  <span data-ttu-id="f8b11-116">На странице **Проверка версии** выберите модель и версию, которые необходимо зафиксировать.</span><span class="sxs-lookup"><span data-stu-id="f8b11-116">On the **Validate Version** page, select the model and version you want to commit.</span></span>  
  
4.  <span data-ttu-id="f8b11-117">Нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="f8b11-117">Click **Commit**.</span></span>  
  
5.  <span data-ttu-id="f8b11-118">В диалоговом окне подтверждения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f8b11-118">In the confirmation dialog box, click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f8b11-119">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="f8b11-119">Next Steps</span></span>  
  
-   [<span data-ttu-id="f8b11-120">Создание флага версии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="f8b11-120">Create a Version Flag &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-version-flag-master-data-services.md)  
  
-   [<span data-ttu-id="f8b11-121">Назначение флага версии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="f8b11-121">Assign a Flag to a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/assign-a-flag-to-a-version-master-data-services.md)  
  
-   [<span data-ttu-id="f8b11-122">Копирование версии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="f8b11-122">Copy a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/copy-a-version-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="f8b11-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="f8b11-123">See Also</span></span>  
 [<span data-ttu-id="f8b11-124">Версии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="f8b11-124">Versions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/versions-master-data-services.md)  
  
  

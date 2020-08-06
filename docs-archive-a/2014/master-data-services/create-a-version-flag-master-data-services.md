---
title: Создание флага версии (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- creating version flags [Master Data Services]
- version flags [Master Data Services], creating
- versions [Master Data Services], creating flags
ms.assetid: 3067e1e3-05b7-4f11-9206-c612ef4e7e42
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f04c93f8315ccd5b53e07db169783da53afe0156
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666107"
---
# <a name="create-a-version-flag-master-data-services"></a><span data-ttu-id="2277c-102">Создание флага версии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="2277c-102">Create a Version Flag (Master Data Services)</span></span>
  <span data-ttu-id="2277c-103">В среде [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]флаг версии создается, чтобы назначить версию.</span><span class="sxs-lookup"><span data-stu-id="2277c-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a version flag to assign to a version.</span></span> <span data-ttu-id="2277c-104">Флаг может указывать на то, какую версию следует использовать пользователям или системам-подписчикам.</span><span class="sxs-lookup"><span data-stu-id="2277c-104">The flag can indicate the version that users or subscribing systems should use.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2277c-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="2277c-105">Prerequisites</span></span>  
 <span data-ttu-id="2277c-106">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="2277c-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="2277c-107">необходимо иметь разрешение на доступ к функциональной области **Управление версиями** ;</span><span class="sxs-lookup"><span data-stu-id="2277c-107">You must have permission to access the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="2277c-108">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="2277c-108">You must be a model administrator.</span></span> <span data-ttu-id="2277c-109">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2277c-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-create-a-version-flag"></a><span data-ttu-id="2277c-110">Создание флага версии</span><span class="sxs-lookup"><span data-stu-id="2277c-110">To create a version flag</span></span>  
  
1.  <span data-ttu-id="2277c-111">В среде [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Управление версиями**.</span><span class="sxs-lookup"><span data-stu-id="2277c-111">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="2277c-112">На панели меню страницы **Управление версиями** наведите курсор на **Управление** и выберите **Флаги**.</span><span class="sxs-lookup"><span data-stu-id="2277c-112">On the **Manage Versions** page, from the menu bar, point to **Manage** and then click **Flags**.</span></span>  
  
3.  <span data-ttu-id="2277c-113">На странице **Управление флагами версий** выберите модель в поле **Модель** , для которой нужно создать флаг.</span><span class="sxs-lookup"><span data-stu-id="2277c-113">On the **Manage Version Flags** page, from the **Model** field, select the model for which you want to create a flag.</span></span>  
  
4.  <span data-ttu-id="2277c-114">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="2277c-114">Click **Add**.</span></span>  
  
5.  <span data-ttu-id="2277c-115">В поле **Имя** введите имя.</span><span class="sxs-lookup"><span data-stu-id="2277c-115">In the **Name** box, type a name.</span></span>  
  
6.  <span data-ttu-id="2277c-116">В поле **Описание** введите описание.</span><span class="sxs-lookup"><span data-stu-id="2277c-116">In the **Description** box, type a description.</span></span>  
  
7.  <span data-ttu-id="2277c-117">В поле **Только зафиксированные версии** выберите **True** , чтобы указать, что флаг может назначаться только версиям со статусом **Зафиксированная** .</span><span class="sxs-lookup"><span data-stu-id="2277c-117">In the **Committed Versions Only** field, select **True** to indicate that the flag can be assigned to versions with a status of **Committed** only.</span></span> <span data-ttu-id="2277c-118">Выберите **False** , чтобы указать, что флаг может назначаться версиям с любым состоянием.</span><span class="sxs-lookup"><span data-stu-id="2277c-118">Select **False** to indicate that the flag can be assigned to versions with any status.</span></span>  
  
8.  <span data-ttu-id="2277c-119">Выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2277c-119">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="2277c-120">Next Steps</span><span class="sxs-lookup"><span data-stu-id="2277c-120">Next Steps</span></span>  
  
-   [<span data-ttu-id="2277c-121">Назначение флага версии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="2277c-121">Assign a Flag to a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/assign-a-flag-to-a-version-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="2277c-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="2277c-122">See Also</span></span>  
 <span data-ttu-id="2277c-123">[Версии &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="2277c-123">[Versions &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span></span>  
 [<span data-ttu-id="2277c-124">Изменение имени флага версии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="2277c-124">Change a Version Flag Name &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/change-a-version-flag-name-master-data-services.md)  
  
  

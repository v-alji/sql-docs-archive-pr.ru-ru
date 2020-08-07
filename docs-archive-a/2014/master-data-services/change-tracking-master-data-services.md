---
title: Отслеживание изменений (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- change tracking [SQL Server]
ms.assetid: 5e879c65-0d38-454f-9a20-62a6e72c89f7
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 2d3b69057b02884f41a43aa9a009ab3db937ed25
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732729"
---
# <a name="change-tracking-master-data-services"></a><span data-ttu-id="db8ff-102">Отслеживание изменений (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="db8ff-102">Change Tracking (Master Data Services)</span></span>
  <span data-ttu-id="db8ff-103">В среде [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]можно использовать группы отслеживания изменений для выполнения действий при изменении значения атрибутов.</span><span class="sxs-lookup"><span data-stu-id="db8ff-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can use change tracking groups to take action when an attribute value changes.</span></span> <span data-ttu-id="db8ff-104">Используйте отслеживание изменений, если неизвестно, каким будет новое значение, но необходимо узнать, произошло ли какое-либо изменение.</span><span class="sxs-lookup"><span data-stu-id="db8ff-104">Use change tracking when you don't know what the new value will be, but instead want to know if any change occurred.</span></span>  
  
## <a name="configuring-change-tracking"></a><span data-ttu-id="db8ff-105">Настройка отслеживания изменений</span><span class="sxs-lookup"><span data-stu-id="db8ff-105">Configuring Change Tracking</span></span>  
 <span data-ttu-id="db8ff-106">Для настройки отслеживания изменений добавьте атрибут в группу отслеживания изменений.</span><span class="sxs-lookup"><span data-stu-id="db8ff-106">To configure change tracking, you add an attribute to a change tracking group.</span></span> <span data-ttu-id="db8ff-107">Группа может содержать один или несколько атрибутов.</span><span class="sxs-lookup"><span data-stu-id="db8ff-107">The group can contain one or many attributes.</span></span> <span data-ttu-id="db8ff-108">Далее создайте бизнес-правило, определяющее, какое действие будет предпринято в случае, если атрибуты в группе изменяются.</span><span class="sxs-lookup"><span data-stu-id="db8ff-108">Then, you create a business rule to define the action that is taken when any of the attributes in the group change.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="db8ff-109">Бизнес-правила, отслеживающие изменения, считают промежуточные (импортированные) данные, измененными.</span><span class="sxs-lookup"><span data-stu-id="db8ff-109">Change tracking business rules consider staged (imported) data to be changed.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="db8ff-110">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="db8ff-110">Related Tasks</span></span>  
  
|<span data-ttu-id="db8ff-111">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="db8ff-111">Task Description</span></span>|<span data-ttu-id="db8ff-112">Раздел</span><span class="sxs-lookup"><span data-stu-id="db8ff-112">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="db8ff-113">Добавление атрибутов в группу отслеживания изменений.</span><span class="sxs-lookup"><span data-stu-id="db8ff-113">Add attributes to a change tracking group.</span></span>|[<span data-ttu-id="db8ff-114">Добавление атрибутов в группу отслеживания изменений (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="db8ff-114">Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;</span></span>](add-attributes-to-a-change-tracking-group-master-data-services.md)|  
|<span data-ttu-id="db8ff-115">Создание бизнес-правила для инициации действий на основе изменений атрибута.</span><span class="sxs-lookup"><span data-stu-id="db8ff-115">Create a business rule that initiates actions based on attribute changes.</span></span>|[<span data-ttu-id="db8ff-116">Инициирование действия на основе значения атрибута (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="db8ff-116">Initiate Actions Based on Attribute Value Changes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/initiate-actions-based-on-attribute-value-changes-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="db8ff-117">См. также</span><span class="sxs-lookup"><span data-stu-id="db8ff-117">Related Content</span></span>  
  
-   [<span data-ttu-id="db8ff-118">Проверка (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="db8ff-118">Validation &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validation-master-data-services.md)  
  
-   [<span data-ttu-id="db8ff-119">Бизнес-правила (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="db8ff-119">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
-   [<span data-ttu-id="db8ff-120">Атрибуты (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="db8ff-120">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)  
  
  

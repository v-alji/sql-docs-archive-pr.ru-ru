---
title: Подтверждение конкретных элементов, обнаруженных при проверке на соответствие бизнес-правилам (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- applying business rules [Master Data Services]
- business rules [Master Data Services], applying to select members
ms.assetid: 2288ef43-5392-47ea-b651-ec25e5692a14
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 18af83146679eb77638dfbc98b31f198dc8e07b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658871"
---
# <a name="validate-specific-members-against-business-rules-master-data-services"></a><span data-ttu-id="0a4c7-102">Подтверждение конкретных членов, обнаруженных при проверке на соответствие бизнес-правилам (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="0a4c7-102">Validate Specific Members against Business Rules (Master Data Services)</span></span>
  <span data-ttu-id="0a4c7-103">В среде [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]бизнес-правила можно применять выборочно, если требуется обновить или проверить подмножество элементов с использованием бизнес-правил.</span><span class="sxs-lookup"><span data-stu-id="0a4c7-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], apply business rules selectively when you want to update or validate subsets of members against business rules.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0a4c7-104">Инструкции о том, как применить бизнес-правила ко всем элементам в версии модели, см. в разделе [Подтверждение исправления проблемы, обнаруженной при проверке на соответствие бизнес-правилам (службы Master Data Services)](validate-a-version-against-business-rules-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0a4c7-104">If you want to apply business rules to all members in a version of a model, see [Validate a Version against Business Rules &#40;Master Data Services&#41;](validate-a-version-against-business-rules-master-data-services.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0a4c7-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="0a4c7-105">Prerequisites</span></span>  
 <span data-ttu-id="0a4c7-106">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="0a4c7-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="0a4c7-107">Необходимо иметь разрешение на доступ к функциональной области **Обозреватель** .</span><span class="sxs-lookup"><span data-stu-id="0a4c7-107">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="0a4c7-108">как минимум требуется разрешение **Обновление** на объект модели, к которому применяются бизнес-правила.</span><span class="sxs-lookup"><span data-stu-id="0a4c7-108">You must have a minimum of **Update** permission to the model object you are applying business rules to.</span></span>  
  
### <a name="to-apply-business-rules-selectively"></a><span data-ttu-id="0a4c7-109">Выборочное применение бизнес-правил</span><span class="sxs-lookup"><span data-stu-id="0a4c7-109">To apply business rules selectively</span></span>  
  
1.  <span data-ttu-id="0a4c7-110">На домашней странице [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] выберите модель в списке **Модель** .</span><span class="sxs-lookup"><span data-stu-id="0a4c7-110">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="0a4c7-111">Выберите версию из списка **Версия** .</span><span class="sxs-lookup"><span data-stu-id="0a4c7-111">From the **Version** list, select a version.</span></span>  
  
3.  <span data-ttu-id="0a4c7-112">Нажмите кнопку **Браузер**.</span><span class="sxs-lookup"><span data-stu-id="0a4c7-112">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="0a4c7-113">На панели меню наведите курсор на пункт **Сущности** и щелкните имя сущности, содержащей элементы, к которым требуется применить правила.</span><span class="sxs-lookup"><span data-stu-id="0a4c7-113">From the menu bar, point to **Entities** and click the name of the entity that contains members you want to apply rules to.</span></span>  
  
5.  <span data-ttu-id="0a4c7-114">Нажмите кнопку **Применить бизнес-правила**.</span><span class="sxs-lookup"><span data-stu-id="0a4c7-114">Click **Apply business rules**.</span></span> <span data-ttu-id="0a4c7-115">Бизнес-правила применяются только к элементам, отображенным в сетке.</span><span class="sxs-lookup"><span data-stu-id="0a4c7-115">Business rules are applied only to the members displayed in the grid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a4c7-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="0a4c7-116">See Also</span></span>  
 <span data-ttu-id="0a4c7-117">[Проверка версии на соответствие бизнес-правилам &#40;Master Data Services&#41;](validate-a-version-against-business-rules-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="0a4c7-117">[Validate a Version against Business Rules &#40;Master Data Services&#41;](validate-a-version-against-business-rules-master-data-services.md) </span></span>  
 [<span data-ttu-id="0a4c7-118">Бизнес-правила (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="0a4c7-118">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
  

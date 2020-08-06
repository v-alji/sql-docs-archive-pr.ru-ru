---
title: Задание порядка атрибутов (мастер бизнес-аналитики) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.specifyordering.setordering.f1
ms.assetid: fc0678fc-e188-4d13-8deb-9daa1281b734
author: minewiskan
ms.author: owend
ms.openlocfilehash: b6a361aa4ef69d83e321de90f316eab4e5659a61
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736842"
---
# <a name="specify-attribute-ordering-business-intelligence-wizard"></a><span data-ttu-id="a4ddf-102">Задание порядка атрибутов (мастер бизнес-аналитики)</span><span class="sxs-lookup"><span data-stu-id="a4ddf-102">Specify Attribute Ordering (Business Intelligence Wizard)</span></span>
  <span data-ttu-id="a4ddf-103">Используйте страницу **Определение порядка атрибутов** для определения порядка расположения атрибутов и критериев их сортировки в выбранном измерении.</span><span class="sxs-lookup"><span data-stu-id="a4ddf-103">Use the **Specify Attribute Ordering** page to specify the ordering attributes and ordering criteria for attributes in the selected dimension.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a4ddf-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="a4ddf-104">Options</span></span>  
 <span data-ttu-id="a4ddf-105">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="a4ddf-105">**Attribute**</span></span>  
 <span data-ttu-id="a4ddf-106">Отображает доступные для измерения атрибуты.</span><span class="sxs-lookup"><span data-stu-id="a4ddf-106">Displays the attributes available for the dimension.</span></span>  
  
 <span data-ttu-id="a4ddf-107">**Атрибут сортировки**</span><span class="sxs-lookup"><span data-stu-id="a4ddf-107">**Ordering Attribute**</span></span>  
 <span data-ttu-id="a4ddf-108">Выберите атрибут, по которому сортируется соответствующий **Атрибут**.</span><span class="sxs-lookup"><span data-stu-id="a4ddf-108">Select the attribute with which to order the corresponding **Attribute**.</span></span> <span data-ttu-id="a4ddf-109">Можно назначить тот же самый атрибут.</span><span class="sxs-lookup"><span data-stu-id="a4ddf-109">You can specify the same attribute.</span></span>  
  
 <span data-ttu-id="a4ddf-110">Чтобы создать новый атрибут упорядочения, выберите **\<New attribute>** и в диалоговом окне **Выбор столбца** выберите столбец, на котором должен быть основан новый атрибут.</span><span class="sxs-lookup"><span data-stu-id="a4ddf-110">To create a new ordering attribute, select **\<New attribute>**, and in the **Select a Column** dialog box, select the column on which the new attribute is to be based.</span></span>  
  
 <span data-ttu-id="a4ddf-111">**Критерии**</span><span class="sxs-lookup"><span data-stu-id="a4ddf-111">**Criteria**</span></span>  
 <span data-ttu-id="a4ddf-112">Определите критерии из поля **Атрибут сортировки** , которые будут использоваться для сортировки элементов соответствующего **атрибута**.</span><span class="sxs-lookup"><span data-stu-id="a4ddf-112">Specify the criteria from the **Ordering Attribute** to use to order the members in the corresponding **Attribute**.</span></span> <span data-ttu-id="a4ddf-113">В следующей таблице приводятся возможные критерии.</span><span class="sxs-lookup"><span data-stu-id="a4ddf-113">The following table lists the available criteria.</span></span>  
  
|<span data-ttu-id="a4ddf-114">Значение</span><span class="sxs-lookup"><span data-stu-id="a4ddf-114">Value</span></span>|<span data-ttu-id="a4ddf-115">Описание</span><span class="sxs-lookup"><span data-stu-id="a4ddf-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a4ddf-116">**имя**;</span><span class="sxs-lookup"><span data-stu-id="a4ddf-116">**Name**</span></span>|<span data-ttu-id="a4ddf-117">Сортирует **Атрибут** по именам элементов атрибута, выбранного в поле **Атрибут сортировки**.</span><span class="sxs-lookup"><span data-stu-id="a4ddf-117">Sort **Attribute** by the member names of the attribute in **Ordering Attribute**.</span></span>|  
|<span data-ttu-id="a4ddf-118">**Key**</span><span class="sxs-lookup"><span data-stu-id="a4ddf-118">**Key**</span></span>|<span data-ttu-id="a4ddf-119">Сортирует **Атрибут** по ключам элементов атрибута, выбранного в поле **Атрибут сортировки**.</span><span class="sxs-lookup"><span data-stu-id="a4ddf-119">Sort **Attribute** by the member keys of the attribute in **Ordering Attribute**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a4ddf-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="a4ddf-120">See Also</span></span>  
 <span data-ttu-id="a4ddf-121">[Справка F1 мастера бизнес-аналитики](business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="a4ddf-121">[Business Intelligence Wizard F1 Help](business-intelligence-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="a4ddf-122">[Конструктор кубов &#40;Analysis Services многомерных данных&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="a4ddf-122">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="a4ddf-123">Конструктор измерений &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="a4ddf-123">Dimension Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimension-designer-analysis-services-multidimensional-data.md)  
  
  

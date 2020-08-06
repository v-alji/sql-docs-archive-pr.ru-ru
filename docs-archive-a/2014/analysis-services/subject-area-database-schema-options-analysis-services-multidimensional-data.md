---
title: Параметры схемы базы данных предметной области (мастер формирования схем) (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.schemagenwizard.subjectareaschemaopts.f1
ms.assetid: 4c109bb8-e19d-412b-908f-bfdd7f872439
author: minewiskan
ms.author: owend
ms.openlocfilehash: 98460332478d02de823addcd113fb9c1e87d6958
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658430"
---
# <a name="subject-area-database-schema-options-schema-generation-wizard-analysis-services---multidimensional-data"></a><span data-ttu-id="d2fc2-102">Параметры схемы базы данных предметной области (мастер формирования схем) (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="d2fc2-102">Subject Area Database Schema Options (Schema Generation Wizard) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="d2fc2-103">Используйте страницу **Параметры схемы базы данных предметной области** для управления формированием схемы, а также для определения типа сохранения данных.</span><span class="sxs-lookup"><span data-stu-id="d2fc2-103">Use the **Subject Area Database Schema Options** page to control how the schema is generated, as well as to define how data is preserved.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d2fc2-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="d2fc2-104">Options</span></span>  
 <span data-ttu-id="d2fc2-105">**Схема-владелец**</span><span class="sxs-lookup"><span data-stu-id="d2fc2-105">**Owning schema**</span></span>  
 <span data-ttu-id="d2fc2-106">Задает имя схемы в новой предметной области базы данных.</span><span class="sxs-lookup"><span data-stu-id="d2fc2-106">Specifies the name of the schema within the new subject area database.</span></span>  
  
 <span data-ttu-id="d2fc2-107">**Создать первичные ключи в таблицах измерений**</span><span class="sxs-lookup"><span data-stu-id="d2fc2-107">**Create primary keys on dimension tables**</span></span>  
 <span data-ttu-id="d2fc2-108">Позволяет создать первичные ключи в таблицах измерений в сформированной схеме.</span><span class="sxs-lookup"><span data-stu-id="d2fc2-108">Creates primary keys on the dimension tables in the generated schema.</span></span> <span data-ttu-id="d2fc2-109">Если не установлен флажок создания индекса, то индекс не создается.</span><span class="sxs-lookup"><span data-stu-id="d2fc2-109">No index is generated if you do not select this option.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d2fc2-110">Если этот флажок не установлен, применяется ссылочная целостность.</span><span class="sxs-lookup"><span data-stu-id="d2fc2-110">If you do not select this option, referential integrity is enforced.</span></span>  
  
 <span data-ttu-id="d2fc2-111">**Создать индексы**</span><span class="sxs-lookup"><span data-stu-id="d2fc2-111">**Create indexes**</span></span>  
 <span data-ttu-id="d2fc2-112">Позволяет создать индексы во внешних ключевых столбцах в сформированной схеме.</span><span class="sxs-lookup"><span data-stu-id="d2fc2-112">Creates indexes on foreign key columns in the generated schema.</span></span>  
  
 <span data-ttu-id="d2fc2-113">**Обязательная целостность ссылок**</span><span class="sxs-lookup"><span data-stu-id="d2fc2-113">**Enforce referential integrity**</span></span>  
 <span data-ttu-id="d2fc2-114">Позволяет задать целостность ссылок в сформированной схеме.</span><span class="sxs-lookup"><span data-stu-id="d2fc2-114">Enforces referential integrity within the generated schema.</span></span> <span data-ttu-id="d2fc2-115">Если этот флажок не установлен, связи создаются, но не задаются.</span><span class="sxs-lookup"><span data-stu-id="d2fc2-115">If you do not select this option, relationships are created but not enforced.</span></span>  
  
 <span data-ttu-id="d2fc2-116">**Сохранить данные при повторном формировании**</span><span class="sxs-lookup"><span data-stu-id="d2fc2-116">**Preserve data on regeneration**</span></span>  
 <span data-ttu-id="d2fc2-117">Позволяет сохранить данные в предметной области базы данных после завершения работы мастера.</span><span class="sxs-lookup"><span data-stu-id="d2fc2-117">Retains data in the subject area database when the wizard finishes.</span></span> <span data-ttu-id="d2fc2-118">Если этот флажок не установлен, все данные в предметной области базы данных могут быть удалены без выдачи предупреждения.</span><span class="sxs-lookup"><span data-stu-id="d2fc2-118">If you do not select this option, all the data in the subject area database may be erased without warning.</span></span>  
  
 <span data-ttu-id="d2fc2-119">**Заполнить таблицы времени**</span><span class="sxs-lookup"><span data-stu-id="d2fc2-119">**Populate time table(s)**</span></span>  
 <span data-ttu-id="d2fc2-120">Позволяет указать, как мастер заполняет расписания.</span><span class="sxs-lookup"><span data-stu-id="d2fc2-120">Specifies how the wizard populates the time tables.</span></span> <span data-ttu-id="d2fc2-121">В следующей таблице показаны возможные значения для данного параметра.</span><span class="sxs-lookup"><span data-stu-id="d2fc2-121">The following table describes the possible values for this option.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d2fc2-122">Этот параметр доступен, если мастер формирования схем вызван из проекта служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] с помощью среды [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] в режиме проекта.</span><span class="sxs-lookup"><span data-stu-id="d2fc2-122">This option is enabled only if Schema Generation Wizard is called from an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, using [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] in project mode.</span></span>  
  
|<span data-ttu-id="d2fc2-123">Значение</span><span class="sxs-lookup"><span data-stu-id="d2fc2-123">Value</span></span>|<span data-ttu-id="d2fc2-124">Описание</span><span class="sxs-lookup"><span data-stu-id="d2fc2-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d2fc2-125">Заполнить</span><span class="sxs-lookup"><span data-stu-id="d2fc2-125">Populate</span></span>|<span data-ttu-id="d2fc2-126">Заполнение предметной области расписаний.</span><span class="sxs-lookup"><span data-stu-id="d2fc2-126">The subject area time tables are populated.</span></span>|  
|<span data-ttu-id="d2fc2-127">Не заполнять</span><span class="sxs-lookup"><span data-stu-id="d2fc2-127">Do not populate</span></span>|<span data-ttu-id="d2fc2-128">Предметная область расписаний не заполняется.</span><span class="sxs-lookup"><span data-stu-id="d2fc2-128">The subject area time tables are not populated.</span></span>|  
|<span data-ttu-id="d2fc2-129">Заполнить, если пуста</span><span class="sxs-lookup"><span data-stu-id="d2fc2-129">Populate only if empty</span></span>|<span data-ttu-id="d2fc2-130">Предметная область расписаний заполняется, если она пуста.</span><span class="sxs-lookup"><span data-stu-id="d2fc2-130">The subject area time tables are populated only if they are empty.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d2fc2-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="d2fc2-131">See Also</span></span>  
 [<span data-ttu-id="d2fc2-132">Справка F1 мастера формирования схем &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="d2fc2-132">Schema Generation Wizard F1 Help &#40;Analysis Services - Multidimensional Data&#41;</span></span>](schema-generation-wizard-f1-help-analysis-services-multidimensional-data.md)  
  
  

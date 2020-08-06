---
title: Перемещение объектов интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], models
- data mining editor [Analysis Services]
- mining models [Analysis Services], managing
- Data Mining Designer
- mining models [Analysis Services], modifying
ms.assetid: bc108407-2603-4387-b930-b5bb9df78069
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2b10be3a79487376b173eab87059404b7f7a618e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728966"
---
# <a name="moving-data-mining-objects"></a><span data-ttu-id="4fb2d-102">Перемещение объектов интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="4fb2d-102">Moving Data Mining Objects</span></span>
  <span data-ttu-id="4fb2d-103">Самым распространенным случаем перемещения объектов интеллектуального анализа данных является развертывание модели из тестовой среды или среды анализа в рабочей среде или обеспечение общего доступа к моделям для других пользователей.</span><span class="sxs-lookup"><span data-stu-id="4fb2d-103">The most common scenarios for moving data mining objects are to deploy a model from a testing or analysis environment to a production environment, or to share models with other users.</span></span>  
  
 <span data-ttu-id="4fb2d-104">В данном разделе описывается использование средств и языков скриптов [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]для перемещения объектов интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="4fb2d-104">This topic describes how you can use the tools and scripting languages provided by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], for moving data mining objects.</span></span>  
  
## <a name="moving-data-mining-objects-between-databases-or-servers"></a><span data-ttu-id="4fb2d-105">Перемещение объектов интеллектуального анализа данных между базами данных или серверами</span><span class="sxs-lookup"><span data-stu-id="4fb2d-105">Moving Data Mining Objects between Databases or Servers</span></span>  
 <span data-ttu-id="4fb2d-106">Объекты интеллектуального анализа данных можно перемещать между базами данных [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] или экземплярами служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] следующими способами:</span><span class="sxs-lookup"><span data-stu-id="4fb2d-106">You can move data mining objects between [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] databases or between instances of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in the following ways:</span></span>  
  
-   <span data-ttu-id="4fb2d-107">Повторное развертывание решения в другой базе данных.</span><span class="sxs-lookup"><span data-stu-id="4fb2d-107">Re-deploying the solution to a different database.</span></span>  
  
-   <span data-ttu-id="4fb2d-108">Создание скриптов для отдельных объектов.</span><span class="sxs-lookup"><span data-stu-id="4fb2d-108">Scripting individual objects.</span></span>  
  
-   <span data-ttu-id="4fb2d-109">Резервное копирование и восстановление копии базы данных.</span><span class="sxs-lookup"><span data-stu-id="4fb2d-109">Backing up and then restoring a copy of the database.</span></span>  
  
-   <span data-ttu-id="4fb2d-110">Экспорт и импорт структур и моделей.</span><span class="sxs-lookup"><span data-stu-id="4fb2d-110">Exporting and importing structures and models.</span></span>  
  
 <span data-ttu-id="4fb2d-111">В следующем разделе данные методы обсуждаются более подробно.</span><span class="sxs-lookup"><span data-stu-id="4fb2d-111">The following section explains these options in more detail.</span></span>  
  
### <a name="deploying"></a><span data-ttu-id="4fb2d-112">Развертывание</span><span class="sxs-lookup"><span data-stu-id="4fb2d-112">Deploying</span></span>  
 <span data-ttu-id="4fb2d-113">Для развертывания решения на другом сервере или в другой базе данных необходимо иметь файл решения, созданный в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4fb2d-113">Deploying the solution to a different server or database requires that you have the solution file that was created by using [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="4fb2d-114">Дополнительные сведения о развертывании решений служб Analysis Services см. в разделе [Развертывание проектов служб Analysis Services (среда SSDT)](../multidimensional-models/deploy-analysis-services-projects-ssdt.md).</span><span class="sxs-lookup"><span data-stu-id="4fb2d-114">For more information about deploying Analysis Services solutions, see [Deploy Analysis Services Projects &#40;SSDT&#41;](../multidimensional-models/deploy-analysis-services-projects-ssdt.md).</span></span>  
  
### <a name="scripting"></a><span data-ttu-id="4fb2d-115">Скрипты</span><span class="sxs-lookup"><span data-stu-id="4fb2d-115">Scripting</span></span>  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="4fb2d-116">предоставляет несколько языков, с помощью которых можно создавать скрипты для работы с объектами.</span><span class="sxs-lookup"><span data-stu-id="4fb2d-116">provides several languages that you can use to script objects.</span></span>  
  
-   <span data-ttu-id="4fb2d-117">**XML для аналитики**: можно создать скрипт для работы с объектами с помощью XMLA, щелкнув правой кнопкой мыши соответствующие объекты в [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4fb2d-117">**XMLA**: You can script objects using XMLA by right-clicking objects in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="4fb2d-118">Для выполнения скрипта откройте его в окне **Запрос XMLA** на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="4fb2d-118">To execute the script, open it in an **XMLA Query** window on the target server.</span></span>  
  
-   <span data-ttu-id="4fb2d-119">**Расширения интеллектуального анализа данных**: создать скрипты можно с помощью шаблонов или одного из построителей запросов, предоставляемых в [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] и [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4fb2d-119">**DMX**: You can create scripts by using templates or one of the query builders provided in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] and [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="4fb2d-120">Однако следует иметь в виду, что наборы задач, которые можно решать с помощью разных языков скриптов, различаются.</span><span class="sxs-lookup"><span data-stu-id="4fb2d-120">Note, however, that there are differences in the tasks that you can perform with each scripting language:</span></span>  
  
-   <span data-ttu-id="4fb2d-121">Такие свойства, как описание объекта и привязки данных, можно создавать или изменять только с помощью DDL-языков [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , но не с помощью расширения интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="4fb2d-121">Properties such as the object description and data bindings can only by created or changed by using [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] DDL languages, not by using DMX.</span></span>  
  
-   <span data-ttu-id="4fb2d-122">Импорт и экспорт объектов интеллектуального анализа данных поддерживается только в расширении интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="4fb2d-122">Only DMX supports the import and export of mining objects.</span></span>  
  
-   <span data-ttu-id="4fb2d-123">Создание PMML и импорт определений моделей из PMML поддерживается только в расширении интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="4fb2d-123">Only DMX supports generating PMML or importing model definitions from PMML.</span></span>  
  
-   <span data-ttu-id="4fb2d-124">Обучение модели с использованием данных приложения поддерживается только в расширении интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="4fb2d-124">Only DMX supports training a model with application data.</span></span> <span data-ttu-id="4fb2d-125">Более того, инструкция расширения интеллектуального анализа данных  INSERT INTO позволяет проводить обучение модели, не предоставляя значений для ключевого столбца.</span><span class="sxs-lookup"><span data-stu-id="4fb2d-125">Moreover, the DMX INSERT INTO statement supports training a model without providing values for a key column.</span></span>  
  
 <span data-ttu-id="4fb2d-126">Дополнительные сведения см. в разделе [Разработка на языке ASSL (язык ASSL)](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).</span><span class="sxs-lookup"><span data-stu-id="4fb2d-126">For more information, see [Developing with Analysis Services Scripting Language &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).</span></span>  
  
### <a name="backup-and-restore"></a><span data-ttu-id="4fb2d-127">Резервное копирование и восстановление</span><span class="sxs-lookup"><span data-stu-id="4fb2d-127">Backup and Restore</span></span>  
 <span data-ttu-id="4fb2d-128">Резервное копирование и восстановление из копии всей базы данных служб Analysis Services является лучшим методом, если решение интеллектуального анализа данных зависит от объектов OLAP.</span><span class="sxs-lookup"><span data-stu-id="4fb2d-128">Backup and restore of an entire Analysis Services database is the method of choice if your data mining solution relies on OLAP objects.</span></span> [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="4fb2d-129">предоставляет функции резервного копирования и восстановления, ускоряющие и облегчающие резервное копирование баз данных.</span><span class="sxs-lookup"><span data-stu-id="4fb2d-129">provides backup and restore functionality that makes database backups faster and easier.</span></span>  
  
 <span data-ttu-id="4fb2d-130">Дополнительные сведения о резервном копировании см. в разделе [Создание и восстановление резервных копий баз данных служб Analysis Services](../multidimensional-models/backup-and-restore-of-analysis-services-databases.md).</span><span class="sxs-lookup"><span data-stu-id="4fb2d-130">For more information about backup, see [Backup and Restore of Analysis Services Databases](../multidimensional-models/backup-and-restore-of-analysis-services-databases.md).</span></span>  
  
### <a name="exporting-and-importing"></a><span data-ttu-id="4fb2d-131">Импорт и экспорт</span><span class="sxs-lookup"><span data-stu-id="4fb2d-131">Exporting and Importing</span></span>  
 <span data-ttu-id="4fb2d-132">Экспорт и последующий импорт моделей и структур интеллектуального анализа данных с помощью инструкций DMX — лучший способ перемещения или создания резервных копий отдельных реляционных объектов интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="4fb2d-132">Exporting and then re-importing mining models and structures by using DMX statements is the easiest way to move or back up individual relational data mining objects.</span></span> <span data-ttu-id="4fb2d-133">Дополнительные сведения о синтаксисе расширения интеллектуального анализа данных для этих операций см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="4fb2d-133">For more information about the DMX syntax for these operations, see the following topics:</span></span>  
  
-   [<span data-ttu-id="4fb2d-134">EXPORT (расширения интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="4fb2d-134">EXPORT &#40;DMX&#41;</span></span>](/sql/dmx/export-dmx)  
  
-   [<span data-ttu-id="4fb2d-135">IMPORT (расширения интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="4fb2d-135">IMPORT &#40;DMX&#41;</span></span>](/sql/dmx/import-dmx)  
  
 <span data-ttu-id="4fb2d-136">Если указывается параметр INCLUDE DEPENDENCIES, службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] также экспортируют определения всех соответствующих представлений источников данных, а при импорте модели или структуры они повторно создают представление источника данных на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="4fb2d-136">If you specify the INCLUDE DEPENDENCIES option, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will also export the definition of any required data source views, and when you import the model or structure, it will re-create the data source view on the target server.</span></span> <span data-ttu-id="4fb2d-137">После завершения импорта модели убедитесь, что в объекте установлены все необходимые разрешения интеллектуального анализа.</span><span class="sxs-lookup"><span data-stu-id="4fb2d-137">After you have finished importing the model, make sure to set the necessary mining permissions on the object.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4fb2d-138">С помощью инструкций DMX нельзя экспортировать и импортировать модели OLAP.</span><span class="sxs-lookup"><span data-stu-id="4fb2d-138">You cannot export and import OLAP models by using DMX.</span></span> <span data-ttu-id="4fb2d-139">Если модель интеллектуального анализа данных основана на кубе OLAP, для резервного копирования и восстановления всей базы данных необходимо воспользоваться функциями служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] либо выполнить повторное развертывание куба и его моделей.</span><span class="sxs-lookup"><span data-stu-id="4fb2d-139">If your mining model is based on an OLAP cube, you must use the functionality provided by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] for backing up and restoring an entire database, or redeploy the cube and its models.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fb2d-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="4fb2d-140">See Also</span></span>  
 [<span data-ttu-id="4fb2d-141">Управление решениями и объектами интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="4fb2d-141">Management of Data Mining Solutions and Objects</span></span>](management-of-data-mining-solutions-and-objects.md)  
  
  

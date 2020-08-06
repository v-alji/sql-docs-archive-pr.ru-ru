---
title: Редактор циклов по каждому элементу (страница «сопоставления переменных») | Документация Майкрософт
ms.custom: ''
ms.date: 08/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.foreachloopcontainer.mapping.f1
ms.assetid: aa847b87-f391-48a5-9849-eeda2d6b00b9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cd37c8c6c00f18d8b5493a058239cc880ecc1f5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752276"
---
# <a name="foreach-loop-editor-variable-mappings-page"></a><span data-ttu-id="35a04-102">Редактор циклов по каждому элементу (страница «Сопоставления переменных»)</span><span class="sxs-lookup"><span data-stu-id="35a04-102">Foreach Loop Editor (Variable Mappings Page)</span></span>
  <span data-ttu-id="35a04-103">Страница **Сопоставления переменных** диалогового окна **Редактор циклов по каждому элементу** используется для сопоставления переменных со значениями коллекции.</span><span class="sxs-lookup"><span data-stu-id="35a04-103">Use the **Variables Mappings** page of the **Foreach Loop Editor** dialog box to map variables to the collection value.</span></span> <span data-ttu-id="35a04-104">Значение переменной обновляется значениями из коллекции при каждом повторе цикла.</span><span class="sxs-lookup"><span data-stu-id="35a04-104">The value of the variable is updated with the collection values on each iteration of the loop.</span></span>  
  
 <span data-ttu-id="35a04-105">Сведения об использовании контейнера «цикл по каждому элементу» в пакете служб Integration Services см. в разделе [Foreach Loop Container](control-flow/foreach-loop-container.md) .</span><span class="sxs-lookup"><span data-stu-id="35a04-105">To learn about how to use the Foreach Loop container in an Integration Services package,  see [Foreach Loop Container](control-flow/foreach-loop-container.md) .</span></span> <span data-ttu-id="35a04-106">Сведения о его настройке см. в разделе [Настройка контейнера "цикл по каждому элементу"](../../2014/integration-services/configure-a-foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="35a04-106">To learn about how to configure it, see [Configure a Foreach Loop Container](../../2014/integration-services/configure-a-foreach-loop-container.md).</span></span>  
  
 <span data-ttu-id="35a04-107">Учебник по службам [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] "Создание простого учебного пакета ETL" содержит занятие, посвященное добавлению и настройке "цикла по каждому элементу".</span><span class="sxs-lookup"><span data-stu-id="35a04-107">The [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] tutorial, Creating a Simple ETL Package Tutorial, includes a lesson that teaches you to add and configure a Foreach Loop.</span></span>  
  
## <a name="options"></a><span data-ttu-id="35a04-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="35a04-108">Options</span></span>  
 <span data-ttu-id="35a04-109">**Переменная**</span><span class="sxs-lookup"><span data-stu-id="35a04-109">**Variable**</span></span>  
 <span data-ttu-id="35a04-110">Выберите существующую переменную или щелкните \<**New variable...**>, чтобы создать новую.</span><span class="sxs-lookup"><span data-stu-id="35a04-110">Select an existing variable, or click \<**New variable...**> to create a new variable.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="35a04-111">После установки сопоставления переменной новая строка автоматически добавится к списку **Переменная**.</span><span class="sxs-lookup"><span data-stu-id="35a04-111">After you map a variable, a new row is automatically added to the **Variable** list.</span></span>  
  
 <span data-ttu-id="35a04-112">**См. также**: подробные сведения о [переменных в службах Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md) и о [добавлении переменной](../../2014/integration-services/add-variable.md).</span><span class="sxs-lookup"><span data-stu-id="35a04-112">**Related Topics**: [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
 <span data-ttu-id="35a04-113">**Index**</span><span class="sxs-lookup"><span data-stu-id="35a04-113">**Index**</span></span>  
 <span data-ttu-id="35a04-114">При использовании перечислителя по каждому элементу задайте индекс столбца в значении коллекции, чтобы установить сопоставление переменных.</span><span class="sxs-lookup"><span data-stu-id="35a04-114">If using the Foreach Item enumerator, specify the index of the column in the collection value to map to the variable.</span></span> <span data-ttu-id="35a04-115">Для других типов перечислителей индекс доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="35a04-115">For other enumerator types, the index is read-only.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="35a04-116">Индекс отсчитывается от 0.</span><span class="sxs-lookup"><span data-stu-id="35a04-116">The index is 0-based.</span></span>  
  
 <span data-ttu-id="35a04-117">**См. также:**[Просмотр файлов и таблиц Excel с помощью контейнера "цикл по каждому элементу"](control-flow/loop-through-excel-files-and-tables-by-using-a-foreach-loop-container.md)</span><span class="sxs-lookup"><span data-stu-id="35a04-117">**Related Topics**: [Loop through Excel Files and Tables by Using a Foreach Loop Container](control-flow/loop-through-excel-files-and-tables-by-using-a-foreach-loop-container.md)</span></span>  
  
 <span data-ttu-id="35a04-118">**Удаление**</span><span class="sxs-lookup"><span data-stu-id="35a04-118">**Delete**</span></span>  
 <span data-ttu-id="35a04-119">Выберите переменную и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="35a04-119">Select a variable, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35a04-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="35a04-120">See Also</span></span>  
 <span data-ttu-id="35a04-121">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="35a04-121">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="35a04-122">[Редактор циклов по каждому элементу &#40;страница "Общие"&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="35a04-122">[Foreach Loop Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="35a04-123">[Редактор циклов по каждому элементу &#40;страница коллекции&#41;](../../2014/integration-services/foreach-loop-editor-collection-page.md) </span><span class="sxs-lookup"><span data-stu-id="35a04-123">[Foreach Loop Editor &#40;Collection Page&#41;](../../2014/integration-services/foreach-loop-editor-collection-page.md) </span></span>  
 <span data-ttu-id="35a04-124">[Страница «Выражения»](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="35a04-124">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="35a04-125">Контейнер «цикл по элементам»</span><span class="sxs-lookup"><span data-stu-id="35a04-125">For Loop Container</span></span>](control-flow/for-loop-container.md)  
  
  

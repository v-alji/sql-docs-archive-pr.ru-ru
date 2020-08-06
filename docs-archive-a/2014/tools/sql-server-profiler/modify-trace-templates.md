---
title: Изменение шаблонов трассировки | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- templates [SQL Server], SQL Server Profiler
- Profiler [SQL Server Profiler], templates
- trace templates [SQL Server]
- modifying trace templates
- SQL Server Profiler, templates
ms.assetid: 75b62a54-8d16-4599-bd2d-c42cfcc209f4
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4a26d0a70f65b6ff60dcf42ffb98e67dc0d2b52d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655494"
---
# <a name="modify-trace-templates"></a><span data-ttu-id="31ad1-102">Изменение шаблонов трассировки</span><span class="sxs-lookup"><span data-stu-id="31ad1-102">Modify Trace Templates</span></span>
  <span data-ttu-id="31ad1-103">Можно изменить шаблоны, сохраняемые в файле на локальном компьютере, на котором выполняется [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="31ad1-103">You can modify templates that are saved in a file on the local computer on which [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] is running.</span></span> <span data-ttu-id="31ad1-104">Можно также изменить шаблоны, производные от этих файлов.</span><span class="sxs-lookup"><span data-stu-id="31ad1-104">You can also modify templates derived from those files.</span></span> <span data-ttu-id="31ad1-105">При изменении существующих шаблонов выполняется редактирование таких свойств шаблонов, как классы событий и столбцы данных в том же порядке, в котором эти свойства были установлены первоначально, на вкладке **Выбор событий** диалогового окна **Свойства трассировки** .</span><span class="sxs-lookup"><span data-stu-id="31ad1-105">When you modify existing templates, you edit template properties such as event classes and data columns, in the same order that the properties were set originally, on the **Events Selection** tab of the **Trace Properties** dialog box.</span></span> <span data-ttu-id="31ad1-106">Классы событий и столбцы данных можно добавлять и удалять, а фильтры изменять.</span><span class="sxs-lookup"><span data-stu-id="31ad1-106">Event classes and data columns can be added or removed, and filters can be changed.</span></span> <span data-ttu-id="31ad1-107">После изменения шаблона создается пользовательский шаблон и исходный системный шаблон остается без изменений.</span><span class="sxs-lookup"><span data-stu-id="31ad1-107">After the template is modified, a user-specific template is created and the original system template is left intact.</span></span> <span data-ttu-id="31ad1-108">Дополнительные сведения см. в разделе [Сохранение трассировок и шаблонов трассировок](save-traces-and-trace-templates.md).</span><span class="sxs-lookup"><span data-stu-id="31ad1-108">For more information, see [Save Traces and Trace Templates](save-traces-and-trace-templates.md).</span></span>  
  
 <span data-ttu-id="31ad1-109">Может потребоваться производный шаблон от существующего файла трассировки, если пользователь не помнит (или не сохранил) исходный шаблон, использованный при создании трассировки, или если нужно выполнить ту же трассировку в последующий день.</span><span class="sxs-lookup"><span data-stu-id="31ad1-109">You may need to derive a template from an existing trace file if you cannot remember (or have not saved) the original template that was used to create the trace, or if you want to run the same trace at a later date.</span></span> <span data-ttu-id="31ad1-110">При работе с существующими трассировками можно просматривать свойства, но нельзя изменять их.</span><span class="sxs-lookup"><span data-stu-id="31ad1-110">When working with existing traces, you can view the properties, but you cannot modify the properties.</span></span> <span data-ttu-id="31ad1-111">Чтобы изменить свойства, необходимо остановить или приостановить трассировку.</span><span class="sxs-lookup"><span data-stu-id="31ad1-111">To modify the properties, stop or pause the trace.</span></span> <span data-ttu-id="31ad1-112">Дополнительные сведения см. в разделах [Создать шаблон на основе файла трассировки или таблицы трассировки (приложение SQL Server Profiler)](sql-server-profiler.md) и [Создать шаблон на основе выполняемой трассировки (приложение SQL Server Profiler)](derive-a-template-from-a-running-trace-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="31ad1-112">For more information, see [Derive a Template from a Trace File or Trace Table &#40;SQL Server Profiler&#41;](sql-server-profiler.md) and [Derive a Template from a Running Trace &#40;SQL Server Profiler&#41;](derive-a-template-from-a-running-trace-sql-server-profiler.md).</span></span>  
  
 <span data-ttu-id="31ad1-113">**Создание шаблона трассировки**</span><span class="sxs-lookup"><span data-stu-id="31ad1-113">**To create a trace template**</span></span>  
  
 [<span data-ttu-id="31ad1-114">Создание шаблона трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="31ad1-114">Create a Trace Template &#40;SQL Server Profiler&#41;</span></span>](create-a-trace-template-sql-server-profiler.md)  
  
 <span data-ttu-id="31ad1-115">**Запуск трассировки из шаблона**</span><span class="sxs-lookup"><span data-stu-id="31ad1-115">**To run a trace from a trace template**</span></span>  
  
 [<span data-ttu-id="31ad1-116">Создание трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="31ad1-116">Create a Trace &#40;SQL Server Profiler&#41;</span></span>](create-a-trace-sql-server-profiler.md)  
  
 <span data-ttu-id="31ad1-117">**Изменение шаблона трассировки**</span><span class="sxs-lookup"><span data-stu-id="31ad1-117">**To modify a trace template**</span></span>  
  
 [<span data-ttu-id="31ad1-118">Использование приложения SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="31ad1-118">Using SQL Server Profiler</span></span>](../../database-engine/modify-a-trace-template-sql-server-profiler.md)  
  
 [<span data-ttu-id="31ad1-119">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="31ad1-119">Using Transact-SQL</span></span>](../../relational-databases/sql-trace/modify-an-existing-trace-transact-sql.md)  
  
 <span data-ttu-id="31ad1-120">**Добавление и удаление событий из шаблона трассировки или файла трассировки**</span><span class="sxs-lookup"><span data-stu-id="31ad1-120">**To add or remove events from a trace template or trace file**</span></span>  
  
 [<span data-ttu-id="31ad1-121">Использование приложения SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="31ad1-121">Using SQL Server Profiler</span></span>](specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md)  
  
 [<span data-ttu-id="31ad1-122">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="31ad1-122">Using Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="31ad1-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="31ad1-123">See Also</span></span>  
 [<span data-ttu-id="31ad1-124">Запуск трассировки</span><span class="sxs-lookup"><span data-stu-id="31ad1-124">Start a Trace</span></span>](start-a-trace.md)  
  
  

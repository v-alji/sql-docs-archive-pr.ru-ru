---
title: Диалоговое окно «SQL Server Profiler-Поиск» | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.find.f1
helpviewer_keywords:
- Find dialog box
ms.assetid: dfaeec04-93d3-4214-9fc1-38b80179b36b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cedf50930c06d211ebcee0c45a249667219f392c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736725"
---
# <a name="sql-server-profiler---find-dialog-box"></a><span data-ttu-id="7170e-102">Приложение SQL Server Profiler — диалоговое окно «Поиск»</span><span class="sxs-lookup"><span data-stu-id="7170e-102">SQL Server Profiler - Find Dialog Box</span></span>
  <span data-ttu-id="7170e-103">Диалоговое окно **Поиск** предназначено для поиска в трассировках по заданным символам или словам.</span><span class="sxs-lookup"><span data-stu-id="7170e-103">Use the **Find** dialog box to search a trace for specific characters or words.</span></span> <span data-ttu-id="7170e-104">Чтобы отменить поиск во время выполнения, нажмите клавишу ESC.</span><span class="sxs-lookup"><span data-stu-id="7170e-104">To cancel a search in progress, press ESC.</span></span>  
  
 <span data-ttu-id="7170e-105">Чтобы открыть это диалоговое окно в приложении [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], в меню **Правка** выберите команду **Найти**.</span><span class="sxs-lookup"><span data-stu-id="7170e-105">To open this dialog box in [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], on the **Edit** menu, click **Find**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7170e-106">Варианты</span><span class="sxs-lookup"><span data-stu-id="7170e-106">Options</span></span>  
 <span data-ttu-id="7170e-107">**Найти**</span><span class="sxs-lookup"><span data-stu-id="7170e-107">**Find what**</span></span>  
 <span data-ttu-id="7170e-108">Введите текст, который требуется найти.</span><span class="sxs-lookup"><span data-stu-id="7170e-108">Enter the text that you want to search for.</span></span> <span data-ttu-id="7170e-109">Условию поиска соответствует любая строка, содержащая заданную строку.</span><span class="sxs-lookup"><span data-stu-id="7170e-109">The search matches any string containing the specified string.</span></span> <span data-ttu-id="7170e-110">Например, условию поиска строки «Completed» соответствует строка «SQL:BatchCompleted».</span><span class="sxs-lookup"><span data-stu-id="7170e-110">For example, searching for "Completed" matches "SQL:BatchCompleted."</span></span> <span data-ttu-id="7170e-111">Знаки подстановки (\*, ? и т. д.) не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="7170e-111">Wild card characters (\*, ?, etc.) are not supported.</span></span>  
  
 <span data-ttu-id="7170e-112">**Искать в столбце**</span><span class="sxs-lookup"><span data-stu-id="7170e-112">**Search in column**</span></span>  
 <span data-ttu-id="7170e-113">Щелкните столбец данных для поиска или нажмите **\<All columns>** для поиска всех столбцов данных в трассировке.</span><span class="sxs-lookup"><span data-stu-id="7170e-113">Click a data column to search, or click **\<All columns>** to search all the data columns in the trace.</span></span>  
  
 <span data-ttu-id="7170e-114">**Учитывать регистр**</span><span class="sxs-lookup"><span data-stu-id="7170e-114">**Match case**</span></span>  
 <span data-ttu-id="7170e-115">Поиск текста в том же регистре, что и в поле **Найти** .</span><span class="sxs-lookup"><span data-stu-id="7170e-115">Finds text that has the same case as the **Find what** box.</span></span> <span data-ttu-id="7170e-116">Чтобы искать в трассировке строки как в верхнем, так и в нижнем регистре, снимите этот флажок.</span><span class="sxs-lookup"><span data-stu-id="7170e-116">Clear this check box to find examples in the trace that are in both uppercase and lowercase text characters.</span></span>  
  
 <span data-ttu-id="7170e-117">**Слово целиком**</span><span class="sxs-lookup"><span data-stu-id="7170e-117">**Match whole word**</span></span>  
 <span data-ttu-id="7170e-118">Ограничение поиска целыми словами.</span><span class="sxs-lookup"><span data-stu-id="7170e-118">Restricts the search to entire words.</span></span> <span data-ttu-id="7170e-119">Чтобы найти символы в слове, снимите флажок **Слово целиком** .</span><span class="sxs-lookup"><span data-stu-id="7170e-119">Clear the **Match whole word** check box to search for characters within a word.</span></span>  
  
 <span data-ttu-id="7170e-120">**Следующий**</span><span class="sxs-lookup"><span data-stu-id="7170e-120">**Find Next**</span></span>  
 <span data-ttu-id="7170e-121">Ищет следующее вхождение символов, указанных в поле **Найти** .</span><span class="sxs-lookup"><span data-stu-id="7170e-121">Finds the next example of the characters in the **Find what** box.</span></span>  
  
 <span data-ttu-id="7170e-122">**Найти ранее**</span><span class="sxs-lookup"><span data-stu-id="7170e-122">**Find Previous**</span></span>  
 <span data-ttu-id="7170e-123">Производит поиск в трассировке в обратном направлении, чтобы найти предыдущее вхождение символов, указанных в поле **Найти** .</span><span class="sxs-lookup"><span data-stu-id="7170e-123">Searches backwards in the trace, to find the previous example of the characters in the **Find what** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7170e-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="7170e-124">See Also</span></span>  
 <span data-ttu-id="7170e-125">[Поиск значения или столбца данных во время трассировки &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/find-a-value-or-data-column-while-tracing-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="7170e-125">[Find a Value or Data Column While Tracing &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/find-a-value-or-data-column-while-tracing-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="7170e-126">[Создание SQL Server Profiler &#40;трассировки&#41;](../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="7170e-126">[Create a Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="7170e-127">[Откройте таблицу трассировки &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/open-a-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="7170e-127">[Open a Trace Table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/open-a-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="7170e-128">[Откройте файл трассировки &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/open-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="7170e-128">[Open a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/open-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="7170e-129">[Шаблоны и разрешения приложения SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="7170e-129">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="7170e-130">Приложение SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="7170e-130">SQL Server Profiler</span></span>](../tools/sql-server-profiler/sql-server-profiler.md)  
  
  

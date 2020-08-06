---
title: Фильтрация событий по времени окончания (приложение SQL Server Profiler) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- event end times [SQL Server]
- filters [SQL Server], traces
- traces [SQL Server], filters
- traces [SQL Server], events
ms.assetid: 74628f9e-2d39-496a-a443-0a3887db223d
author: stevestein
ms.author: sstein
ms.openlocfilehash: d25d8e1adbd95f48d88fd1516c48dcc0f8374a7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750388"
---
# <a name="filter-events-based-on-the-event-end-time-sql-server-profiler"></a><span data-ttu-id="77dd5-102">фильтровать события на основе времени окончания события (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="77dd5-102">Filter Events Based on the Event End Time (SQL Server Profiler)</span></span>
  <span data-ttu-id="77dd5-103">В этом подразделе описывается, как при помощи приложения [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]отфильтровать события трассировки на основе времени окончания события.</span><span class="sxs-lookup"><span data-stu-id="77dd5-103">This topic describes how to filter trace events based on the event ending time by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-filter-events-based-on-the-event-end-time"></a><span data-ttu-id="77dd5-104">Фильтрование событий на основе времени окончания события</span><span class="sxs-lookup"><span data-stu-id="77dd5-104">To filter events based on the event end time</span></span>  
  
1.  <span data-ttu-id="77dd5-105">В меню **Файл** выберите пункт **Создать трассировку**, а затем подключитесь к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77dd5-105">On the **File** menu, click **New Trace**, and then connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="77dd5-106">Отображается диалоговое окно **Свойства трассировки**.</span><span class="sxs-lookup"><span data-stu-id="77dd5-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="77dd5-107">Если установлен параметр **Начать трассировку немедленно после установления соединения**, диалоговое окно **Свойства трассировки**не отображается, а вместо этого начинается трассировка.</span><span class="sxs-lookup"><span data-stu-id="77dd5-107">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear and the trace begins instead.</span></span> <span data-ttu-id="77dd5-108">Чтобы отключить этот параметр, в меню **Сервис**выберите пункт **Параметры**и снимите флажок **Начать трассировку немедленно после установления соединения** .</span><span class="sxs-lookup"><span data-stu-id="77dd5-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="77dd5-109">В диалоговом окне **Свойства трассировки** выберите вкладку **Общие** и введите имя в текстовое поле **Имя трассировки** .</span><span class="sxs-lookup"><span data-stu-id="77dd5-109">In the **Trace Properties** dialog box, make sure the **General** tab is selected, and enter a name in the **TraceName** text box.</span></span>  
  
3.  <span data-ttu-id="77dd5-110">В списке **Использовать шаблон**выберите шаблон трассировки.</span><span class="sxs-lookup"><span data-stu-id="77dd5-110">From the **Use the template**list, select a trace template.</span></span>  
  
4.  <span data-ttu-id="77dd5-111">Можно также задать целевой файл или таблицу, в которых будут сохраняться результаты трассировки.</span><span class="sxs-lookup"><span data-stu-id="77dd5-111">Optionally, specify a destination file or table in which to save the trace results.</span></span>  
  
5.  <span data-ttu-id="77dd5-112">На вкладке **Выбор событий**щелкните столбец данных **EndTime** , чтобы открыть диалоговое окно **Изменение фильтра** .</span><span class="sxs-lookup"><span data-stu-id="77dd5-112">On the **Events Selection**tab, click the **EndTime** data column to launch the **Edit Filter** dialog box.</span></span> <span data-ttu-id="77dd5-113">Можно также щелкнуть правой кнопкой мыши заголовок столбца и выбрать пункт **Изменить фильтр столбца**.</span><span class="sxs-lookup"><span data-stu-id="77dd5-113">You can also right-click the column heading, and select **Edit Column Filter**.</span></span>  
  
6.  <span data-ttu-id="77dd5-114">Разверните узел **больше** или **меньше**, а затем введите `datetime` значение в поле, которое отображается под оператором сравнения.</span><span class="sxs-lookup"><span data-stu-id="77dd5-114">Expand **Greater than** or **Less than**, and enter a `datetime`value in the field that appears beneath the comparison operator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77dd5-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="77dd5-115">See Also</span></span>  
 <span data-ttu-id="77dd5-116">[Приложение SQL Server Profiler](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="77dd5-116">[SQL Server Profiler](sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="77dd5-117">Приложение SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="77dd5-117">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  

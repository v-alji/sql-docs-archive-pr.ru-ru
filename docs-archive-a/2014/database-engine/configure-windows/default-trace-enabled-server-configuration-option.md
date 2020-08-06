---
title: Параметр конфигурации сервера "default trace enabled" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], traces
- traces [SQL Server], logs
- default trace enabled option
ms.assetid: 1322d668-44f4-469e-8fd6-e0d02a81c8f2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8d40305de7375f2ae10d563871fd40b7acfa463f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740421"
---
# <a name="default-trace-enabled-server-configuration-option"></a><span data-ttu-id="75f23-102">Параметр конфигурации сервера «default trace enabled»</span><span class="sxs-lookup"><span data-stu-id="75f23-102">default trace enabled Server Configuration Option</span></span>
  <span data-ttu-id="75f23-103">Используйте параметр **default trace enabled** , чтобы включить или отключить файлы журнала трассировки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="75f23-103">Use the **default trace enabled** option to enable or disable the default trace log files.</span></span> <span data-ttu-id="75f23-104">Функциональные возможности трассировки по умолчанию обеспечивают насыщенный, стабильный журнал активности и изменений, в основном связанных с параметрами конфигурации.</span><span class="sxs-lookup"><span data-stu-id="75f23-104">The default trace functionality provides a rich, persistent log of activity and changes primarily related to the configuration options.</span></span>  
  
> [!WARNING]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] <span data-ttu-id="75f23-105">Вместо этого используйте расширенные события.</span><span class="sxs-lookup"><span data-stu-id="75f23-105">Use Extended Events instead.</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="75f23-106">Назначение</span><span class="sxs-lookup"><span data-stu-id="75f23-106">Purpose</span></span>  
 <span data-ttu-id="75f23-107">Трассировка по умолчанию обеспечивает помощь в поиске неисправностей администраторам базы данных, гарантируя, что они имеют необходимые регистрационные данные для диагностики проблем сразу же, как только они происходят.</span><span class="sxs-lookup"><span data-stu-id="75f23-107">Default trace provides troubleshooting assistance to database administrators by ensuring that they have the log data necessary to diagnose problems the first time they occur.</span></span>  
  
## <a name="viewing"></a><span data-ttu-id="75f23-108">просмотр</span><span class="sxs-lookup"><span data-stu-id="75f23-108">Viewing</span></span>  
 <span data-ttu-id="75f23-109">Журналы трассировки по умолчанию можно открыть и исследовать в приложении [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] , либо к ним можно применить запросы на языке [!INCLUDE[tsql](../../includes/tsql-md.md)] с помощью системной функции `fn_trace_gettable` .</span><span class="sxs-lookup"><span data-stu-id="75f23-109">The default trace logs can be opened and examined by [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] or queried with [!INCLUDE[tsql](../../includes/tsql-md.md)] by using the `fn_trace_gettable` system function.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="75f23-110">позволяет открывать файлы используемых по умолчанию журналов трассировки таким же образом, как и обычные выходные файлы трассировки.</span><span class="sxs-lookup"><span data-stu-id="75f23-110">can open the default trace log files just as it does normal trace output files.</span></span> <span data-ttu-id="75f23-111">Файл журнала трассировки по умолчанию хранится по умолчанию в каталоге `\MSSQL\LOG` , используя файл продолжения трассировки.</span><span class="sxs-lookup"><span data-stu-id="75f23-111">The default trace log is stored by default in the `\MSSQL\LOG` directory using a rollover trace file.</span></span> <span data-ttu-id="75f23-112">Базовое имя файла для файла журнала трассировки по умолчанию — `log.trc`.</span><span class="sxs-lookup"><span data-stu-id="75f23-112">The base file name for the default trace log file is `log.trc`.</span></span> <span data-ttu-id="75f23-113">Как правило, в установке [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]трассировка по умолчанию разрешена, поэтому TraceID будет равно 1.</span><span class="sxs-lookup"><span data-stu-id="75f23-113">In a typical installation of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the default trace is enabled and thus becomes TraceID 1.</span></span> <span data-ttu-id="75f23-114">Если разрешение будет дано после установки и создания других трассировок, то числовое обозначение TraceID может стать больше.</span><span class="sxs-lookup"><span data-stu-id="75f23-114">If enabled after installation and after creating other traces, the TraceID can become a larger number.</span></span>  
  
 <span data-ttu-id="75f23-115">Дополнительные сведения об использовании приложения [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Profiler для просмотра этого файла трассировки см. в разделе [Открыть файл трассировки (приложение SQL Server Profiler)](../../tools/sql-server-profiler/open-a-trace-file-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="75f23-115">For more information about using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Profiler to view this trace file, see [Open a Trace File &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/open-a-trace-file-sql-server-profiler.md)</span></span>  
  
### <a name="example"></a><span data-ttu-id="75f23-116">Пример</span><span class="sxs-lookup"><span data-stu-id="75f23-116">Example:</span></span>  
 <span data-ttu-id="75f23-117">Следующая инструкция открывает журнал трассировки по умолчанию в расположении по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="75f23-117">The following statement opens the default trace log in the default location:</span></span>  
  
```  
SELECT *   
FROM fn_trace_gettable  
('C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\LOG\log.trc', default);  
GO  
  
```  
  
## <a name="configuring"></a><span data-ttu-id="75f23-118">Настройка</span><span class="sxs-lookup"><span data-stu-id="75f23-118">Configuring</span></span>  
 <span data-ttu-id="75f23-119">Установка параметра **default trace enabled** в значение 1 включает **трассировку по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="75f23-119">When set to 1, the **default trace enabled** option enables **Default Trace**.</span></span> <span data-ttu-id="75f23-120">Настройка по умолчанию для этого параметра — 1 (включено).</span><span class="sxs-lookup"><span data-stu-id="75f23-120">The default setting for this option is 1 (ON).</span></span> <span data-ttu-id="75f23-121">Значение 0 выключает трассировку.</span><span class="sxs-lookup"><span data-stu-id="75f23-121">A value of 0 turns off the trace.</span></span>  
  
 <span data-ttu-id="75f23-122">Параметр **default trace enabled** является дополнительным параметром.</span><span class="sxs-lookup"><span data-stu-id="75f23-122">The **default trace enabled** option is an advanced option.</span></span> <span data-ttu-id="75f23-123">Если для изменения этого параметра используется системная хранимая процедура **sp_configure** , то возможность изменить значение параметра **default trace enabled** разрешена только в том случае, если параметр **show advanced options** имеет значение 1.</span><span class="sxs-lookup"><span data-stu-id="75f23-123">If you are using the **sp_configure** system stored procedure to change the setting, you can change the **default trace enabled** option only when **show advanced options** is set to 1.</span></span> <span data-ttu-id="75f23-124">Параметр вступает в силу сразу без перезапуска сервера.</span><span class="sxs-lookup"><span data-stu-id="75f23-124">The setting takes effect immediately without a server restart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75f23-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="75f23-125">See Also</span></span>  
 <span data-ttu-id="75f23-126">[RECONFIGURE (Transact-SQL)](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="75f23-126">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="75f23-127">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="75f23-127">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="75f23-128">sp_configure (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="75f23-128">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  

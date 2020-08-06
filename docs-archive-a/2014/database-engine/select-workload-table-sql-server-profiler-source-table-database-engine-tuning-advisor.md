---
title: SQL Server Profiler-Source Table-помощник по настройке ядра СУБД — выбор таблицы рабочей нагрузки | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.replay.tools.sourcetable.f1
helpviewer_keywords:
- Select Workload Table dialog box
- Source Table dialog box
ms.assetid: 51185be7-7092-480a-a52c-cf7786c4a0a0
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d10899c01df8e7fbc7ee45d108841a18d3248500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658380"
---
# <a name="sql-server-profiler---source-table-database-engine-tuning-advisor---select-workload-table"></a><span data-ttu-id="40c70-102">SQL Server Profiler-Source Table-помощник по настройке ядра СУБД — выбор таблицы рабочей нагрузки</span><span class="sxs-lookup"><span data-stu-id="40c70-102">SQL Server Profiler - Source Table-Database Engine Tuning Advisor - Select Workload Table</span></span>
  <span data-ttu-id="40c70-103">Microsoft [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] и помощник по настройке [!INCLUDE[ssDE](../includes/ssde-md.md)] используют это диалоговое окно для выбора таблиц.</span><span class="sxs-lookup"><span data-stu-id="40c70-103">Microsoft [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] and [!INCLUDE[ssDE](../includes/ssde-md.md)] Tuning Advisor use this dialog box to select tables.</span></span>  
  
 <span data-ttu-id="40c70-104">В [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] диалоговое окно **Исходная таблица** используется для задания исходной таблицы для таблицы трассировки.</span><span class="sxs-lookup"><span data-stu-id="40c70-104">In [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], use the **Source Table** dialog box to specify a source table for a trace table.</span></span> <span data-ttu-id="40c70-105">Это таблица, из которой загружается трассировка, и содержимое которой просматривается или используется для воспроизведения трассировки.</span><span class="sxs-lookup"><span data-stu-id="40c70-105">This is a table from which a trace is loaded, and the contents of which are viewed or used for replaying the trace.</span></span>  
  
 <span data-ttu-id="40c70-106">В помощнике по настройке [!INCLUDE[ssDE](../includes/ssde-md.md)] диалоговое окно **Выбор таблицы рабочей нагрузки** используется для выбора таблицы базы данных, содержащей данные трассировки [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], для использования в качестве рабочей нагрузки при настройке или для предварительного просмотра содержимого таблицы перед началом анализа настройки.</span><span class="sxs-lookup"><span data-stu-id="40c70-106">In [!INCLUDE[ssDE](../includes/ssde-md.md)] Tuning Advisor, use the **Select Workload Table** dialog box to select a database table that contains [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] trace information to use as a tuning workload, or to preview the table contents before starting tuning analysis.</span></span>  
  
## <a name="options"></a><span data-ttu-id="40c70-107">Варианты</span><span class="sxs-lookup"><span data-stu-id="40c70-107">Options</span></span>  
 <span data-ttu-id="40c70-108">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="40c70-108">**SQL Server**</span></span>  
 <span data-ttu-id="40c70-109">Указывает экземпляр [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , к которому в данный момент установлено подключение.</span><span class="sxs-lookup"><span data-stu-id="40c70-109">Specifies the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] currently connected.</span></span> <span data-ttu-id="40c70-110">Это поле заполняется автоматически и не может быть изменено.</span><span class="sxs-lookup"><span data-stu-id="40c70-110">This field is populated automatically and cannot be updated.</span></span>  
  
 <span data-ttu-id="40c70-111">**База данных**</span><span class="sxs-lookup"><span data-stu-id="40c70-111">**Database**</span></span>  
 <span data-ttu-id="40c70-112">Задайте базу данных, в которой расположена таблица трассировки.</span><span class="sxs-lookup"><span data-stu-id="40c70-112">Specify the database where the trace table is located.</span></span>  
  
 <span data-ttu-id="40c70-113">**Владелец**</span><span class="sxs-lookup"><span data-stu-id="40c70-113">**Owner**</span></span>  
 <span data-ttu-id="40c70-114">Specifies the owner of the trace table.</span><span class="sxs-lookup"><span data-stu-id="40c70-114">Specifies the owner of the trace table.</span></span> <span data-ttu-id="40c70-115">Это поле автоматически заполняется значением **dbo**.</span><span class="sxs-lookup"><span data-stu-id="40c70-115">This field is populated automatically as **dbo**.</span></span>  
  
 <span data-ttu-id="40c70-116">**Таблица**</span><span class="sxs-lookup"><span data-stu-id="40c70-116">**Table**</span></span>  
 <span data-ttu-id="40c70-117">Задайте имя таблицы трассировки, из которой должна читаться трассировка.</span><span class="sxs-lookup"><span data-stu-id="40c70-117">Specify the name of the trace table from which the trace should be read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40c70-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="40c70-118">See Also</span></span>  
 <span data-ttu-id="40c70-119">[Сохранение результатов трассировки в таблицу (приложение SQL Server Profiler)](../tools/sql-server-profiler/save-trace-results-to-a-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="40c70-119">[Save Trace Results to a Table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/save-trace-results-to-a-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="40c70-120">[Шаблоны и разрешения приложения SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="40c70-120">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="40c70-121">Database Engine Tuning Advisor</span><span class="sxs-lookup"><span data-stu-id="40c70-121">Database Engine Tuning Advisor</span></span>](../relational-databases/performance/database-engine-tuning-advisor.md)  
  
  

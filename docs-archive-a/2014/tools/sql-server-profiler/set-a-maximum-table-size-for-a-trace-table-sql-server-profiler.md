---
title: Задание максимального размера для таблицы трассировки (приложение SQL Server Profiler) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- size [SQL Server], trace tables
- maximum table size for traces
ms.assetid: d0ae83e5-1c88-4a2e-be05-2c341280b978
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5f48efbe02e300e06faf857ed0fb36ae340ad979
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727558"
---
# <a name="set-a-maximum-table-size-for-a-trace-table-sql-server-profiler"></a><span data-ttu-id="1da36-102">установить максимальный размер для таблицы трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="1da36-102">Set a Maximum Table Size for a Trace Table (SQL Server Profiler)</span></span>
  <span data-ttu-id="1da36-103">В этом подразделе рассказывается о том, как задать максимальный размер таблицы трассировки при помощи приложения [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1da36-103">This topic describes how to set a maximum table size for trace tables by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-set-a-maximum-table-size-for-a-trace-table"></a><span data-ttu-id="1da36-104">Установка максимального размера таблицы трассировки</span><span class="sxs-lookup"><span data-stu-id="1da36-104">To set a maximum table size for a trace table</span></span>  
  
1.  <span data-ttu-id="1da36-105">В меню **Файл** выберите пункт **Создать трассировку**, а затем подключитесь к экземпляру SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1da36-105">On the **File** menu, click **New Trace**, and then connect to an instance of SQL Server.</span></span>  
  
     <span data-ttu-id="1da36-106">Отображается диалоговое окно **Свойства трассировки**.</span><span class="sxs-lookup"><span data-stu-id="1da36-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1da36-107">Если установлен параметр **Начать трассировку немедленно после установления соединения**, диалоговое окно **Свойства трассировки**не отображается, а вместо этого начинается трассировка.</span><span class="sxs-lookup"><span data-stu-id="1da36-107">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear and the trace begins instead.</span></span> <span data-ttu-id="1da36-108">Чтобы отключить этот параметр, в меню **Сервис**выберите пункт **Параметры**и снимите флажок **Начать трассировку немедленно после установления соединения** .</span><span class="sxs-lookup"><span data-stu-id="1da36-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="1da36-109">В поле **Имя трассировки** введите имя трассировки.</span><span class="sxs-lookup"><span data-stu-id="1da36-109">In the **Trace name** box, type a name for the trace.</span></span>  
  
3.  <span data-ttu-id="1da36-110">В списке **Имя шаблона**выберите шаблон трассировки.</span><span class="sxs-lookup"><span data-stu-id="1da36-110">In the **Template name**list, select a trace template.</span></span>  
  
4.  <span data-ttu-id="1da36-111">Установите флажок **Сохранить в таблицу**.</span><span class="sxs-lookup"><span data-stu-id="1da36-111">Select the **Save to table**check box.</span></span>  
  
5.  <span data-ttu-id="1da36-112">Подключитесь к серверу, на который будет записываться трассировка.</span><span class="sxs-lookup"><span data-stu-id="1da36-112">Connect to the server on which you want the trace to be stored.</span></span>  
  
     <span data-ttu-id="1da36-113">Откроется диалоговое окно **Целевая таблица** .</span><span class="sxs-lookup"><span data-stu-id="1da36-113">The **Destination Table** dialog box appears.</span></span>  
  
6.  <span data-ttu-id="1da36-114">Выберите базу данных для трассировки из списка **База данных** .</span><span class="sxs-lookup"><span data-stu-id="1da36-114">Select a database for the trace from the **Database** list.</span></span>  
  
7.  <span data-ttu-id="1da36-115">В поле **Таблица** введите или выберите имя таблицы.</span><span class="sxs-lookup"><span data-stu-id="1da36-115">In the **Table** box, type or select a table name.</span></span>  
  
8.  <span data-ttu-id="1da36-116">Установите флажок **Установить максимальное число строк** и укажите максимальное число строк для таблицы трассировки.</span><span class="sxs-lookup"><span data-stu-id="1da36-116">Select the **Set maximum rows** check box, and specify a maximum number of rows for the trace table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1da36-117">Когда количество строк в таблице превысит указанный максимум, регистрация событий трассировки прекратится.</span><span class="sxs-lookup"><span data-stu-id="1da36-117">When the number of rows in the table exceeds the maximum that you have specified, the trace events are no longer recorded.</span></span> <span data-ttu-id="1da36-118">Однако трассировка продолжится.</span><span class="sxs-lookup"><span data-stu-id="1da36-118">However, tracing continues.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1da36-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="1da36-119">See Also</span></span>  
 <span data-ttu-id="1da36-120">[Приложение SQL Server Profiler](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="1da36-120">[SQL Server Profiler](sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="1da36-121">Приложение SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="1da36-121">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  

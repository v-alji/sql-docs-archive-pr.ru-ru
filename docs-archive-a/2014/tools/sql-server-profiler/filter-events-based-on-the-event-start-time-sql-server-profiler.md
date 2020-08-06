---
title: Фильтрация событий по времени начала (приложение SQL Server Profiler) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- event start times [SQL Server]
- filters [SQL Server], traces
- traces [SQL Server], filters
- traces [SQL Server], events
ms.assetid: e965579e-d006-41a3-89ec-cfd5398c67d2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7f652952ec6706580b876e3e9a20f96e62598f81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739026"
---
# <a name="filter-events-based-on-the-event-start-time-sql-server-profiler"></a><span data-ttu-id="f38f9-102">фильтровать события по времени начала (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="f38f9-102">Filter Events Based on the Event Start Time (SQL Server Profiler)</span></span>
  <span data-ttu-id="f38f9-103">В этом разделе описана фильтрация событий трассировки по времени начала с помощью приложения [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f38f9-103">This topic describes how to filter trace events based on the event start time by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-filter-an-event-based-on-the-event-start-time"></a><span data-ttu-id="f38f9-104">Фильтрация событий по времени начала события</span><span class="sxs-lookup"><span data-stu-id="f38f9-104">To filter an event based on the event start time</span></span>  
  
1.  <span data-ttu-id="f38f9-105">В меню **Файл** выберите пункт **Создать трассировку**, а затем подключитесь к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f38f9-105">On the **File** menu, click **New Trace**, and then connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="f38f9-106">Отображается диалоговое окно **Свойства трассировки**.</span><span class="sxs-lookup"><span data-stu-id="f38f9-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f38f9-107">Если установлен параметр **Начать трассировку немедленно после установления соединения**, диалоговое окно **Свойства трассировки**не отображается, а вместо этого начинается трассировка.</span><span class="sxs-lookup"><span data-stu-id="f38f9-107">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear, and the trace begins instead.</span></span> <span data-ttu-id="f38f9-108">Чтобы отключить этот параметр, в меню **Сервис**выберите пункт **Параметры**и снимите флажок **Начать трассировку немедленно после установления соединения** .</span><span class="sxs-lookup"><span data-stu-id="f38f9-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="f38f9-109">В поле **Имя трассировки** введите имя трассировки.</span><span class="sxs-lookup"><span data-stu-id="f38f9-109">In the **Trace name** box, type a name for the trace.</span></span>  
  
3.  <span data-ttu-id="f38f9-110">В списке имен **Использовать шаблон**выберите шаблон трассировки.</span><span class="sxs-lookup"><span data-stu-id="f38f9-110">In the **Use the template**name list, select a trace template.</span></span>  
  
4.  <span data-ttu-id="f38f9-111">При необходимости задайте целевые расположения для сохранения результатов трассировки.</span><span class="sxs-lookup"><span data-stu-id="f38f9-111">Optionally specify a destination for the trace results.</span></span>  
  
5.  <span data-ttu-id="f38f9-112">На вкладке **Выбор событий**щелкните заголовок столбца **StartTime** .</span><span class="sxs-lookup"><span data-stu-id="f38f9-112">On the **Events Selection**tab, click the **StartTime** column heading.</span></span> <span data-ttu-id="f38f9-113">Кроме того, для открытия диалогового окна **Редактирование фильтра** щелкните правой кнопкой мыши заголовок столбца и выберите пункт **Изменить фильтр** .</span><span class="sxs-lookup"><span data-stu-id="f38f9-113">You can also right-click the column heading, and then click **Edit Column Filter** to launch the **Edit Filter** dialog box.</span></span>  
  
6.  <span data-ttu-id="f38f9-114">Разверните узел **больше** или **меньше**, а затем введите `datetime` значение в поле, которое отображается под оператором сравнения.</span><span class="sxs-lookup"><span data-stu-id="f38f9-114">Expand **Greater than** or **Less than**, and then enter a `datetime` value in the field that appears beneath the comparison operator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f38f9-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="f38f9-115">See Also</span></span>  
 [<span data-ttu-id="f38f9-116">Приложение SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="f38f9-116">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  

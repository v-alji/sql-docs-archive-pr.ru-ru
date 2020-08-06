---
title: Фильтрация идентификаторов процессов сервера (SPID) в трассировке (приложение SQL Server Profiler) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server], traces
- filters [SQL Server], SPIDs
- traces [SQL Server], filters
ms.assetid: f5945c39-be6b-4632-91cb-92066c80e188
author: stevestein
ms.author: sstein
ms.openlocfilehash: 99ae7eac6f19bd942a04f97b0a7da580eadc9dbf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739020"
---
# <a name="filter-server-process-ids-spids-in-a-trace-sql-server-profiler"></a><span data-ttu-id="b6568-102">отфильтровать идентификаторы процессов сервера (SPID) в трассировке (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="b6568-102">Filter Server Process IDs (SPIDs) in a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="b6568-103">Данный подраздел описывает, как отфильтровать идентификаторы процессов сервера (SPID) в трассировке при использовании приложения [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6568-103">This topic describes how to filter server process identifiers (SPIDs) in a trace by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-filter-system-ids-in-a-trace"></a><span data-ttu-id="b6568-104">Фильтрация системных идентификаторов в трассировке</span><span class="sxs-lookup"><span data-stu-id="b6568-104">To filter system IDs in a trace</span></span>  
  
1.  <span data-ttu-id="b6568-105">В меню **Файл** выберите пункт **Создать трассировку**, а затем подключитесь к экземпляру SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b6568-105">On the **File** menu, click **New Trace**, and then connect to an instance of SQL Server.</span></span>  
  
     <span data-ttu-id="b6568-106">Отображается диалоговое окно **Свойства трассировки**.</span><span class="sxs-lookup"><span data-stu-id="b6568-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b6568-107">Если выбран параметр **Начать трассировку немедленно после**установления соединения, диалоговое окно **Свойства трассировки**не отображается, а вместо этого начинается трассировка.</span><span class="sxs-lookup"><span data-stu-id="b6568-107">if **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear, and the trace begins instead.</span></span> <span data-ttu-id="b6568-108">Чтобы отключить этот параметр, в меню **Сервис**выберите пункт **Параметры**и снимите флажок **Начать трассировку немедленно после установления соединения** .</span><span class="sxs-lookup"><span data-stu-id="b6568-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="b6568-109">В поле **Имя трассировки** введите имя трассировки.</span><span class="sxs-lookup"><span data-stu-id="b6568-109">In the **Trace name** box, type a name for the trace.</span></span>  
  
3.  <span data-ttu-id="b6568-110">В списке имен **Использовать шаблон**выберите шаблон трассировки.</span><span class="sxs-lookup"><span data-stu-id="b6568-110">In the **Use the template**name list, select a trace template.</span></span>  
  
4.  <span data-ttu-id="b6568-111">Можно также задать целевой файл или таблицу, в которых будут сохраняться результаты трассировки.</span><span class="sxs-lookup"><span data-stu-id="b6568-111">Optionally, specify a destination file or table in which to save the trace results.</span></span>  
  
5.  <span data-ttu-id="b6568-112">На вкладке **Выбор событий**щелкните заголовок столбца **SPID**, чтобы открыть диалоговое окно **Изменение фильтра** .</span><span class="sxs-lookup"><span data-stu-id="b6568-112">On the **Events Selection**tab, click the **SPID**column heading to launch the **Edit Filter** dialog box.</span></span> <span data-ttu-id="b6568-113">Можно также правой кнопкой мыши щелкнуть заголовок столбца и выбрать пункт **Изменить фильтр столбца**.</span><span class="sxs-lookup"><span data-stu-id="b6568-113">You can also right-click the column heading and choose **Edit Column Filter**.</span></span> <span data-ttu-id="b6568-114">Если столбец **SPID** не отображается, установите флажок **Показать все столбцы** .</span><span class="sxs-lookup"><span data-stu-id="b6568-114">If the **SPID** column does not appear, check the **Show all columns** box.</span></span>  
  
6.  <span data-ttu-id="b6568-115">В диалоговом окне **Изменение фильтра** раскройте соответствующий оператор сравнения и введите SPID как значение для сравнения.</span><span class="sxs-lookup"><span data-stu-id="b6568-115">In the **Edit Filter** dialog box, expand the appropriate comparison operator, and enter a SPID as a value for the comparison.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6568-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="b6568-116">See Also</span></span>  
 [<span data-ttu-id="b6568-117">Приложение SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="b6568-117">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  

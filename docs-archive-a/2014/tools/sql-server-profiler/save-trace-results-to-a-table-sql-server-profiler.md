---
title: Сохранение результатов трассировки в таблицу (приложение SQL Server Profiler) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- saving traces
- traces [SQL Server], saving
ms.assetid: edbecf74-683b-4e43-a1ef-7a3d5f5e27f6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 08acfb4e7136f8b28d1c990d508b8578f96a57b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737187"
---
# <a name="save-trace-results-to-a-table-sql-server-profiler"></a><span data-ttu-id="b952d-102">сохранять результаты трассировки в таблицу (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="b952d-102">Save Trace Results to a Table (SQL Server Profiler)</span></span>
  <span data-ttu-id="b952d-103">В этом подразделе описывается, как сохранять результаты трассировок в таблицу базы данных с помощью приложения [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b952d-103">This topic describes how to save trace results to a database table by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-save-trace-results-to-a-table"></a><span data-ttu-id="b952d-104">Сохранение результатов трассировки в таблицу</span><span class="sxs-lookup"><span data-stu-id="b952d-104">To save trace results to a table</span></span>  
  
1.  <span data-ttu-id="b952d-105">В меню **Файл** выберите пункт **Создать трассировку**, а затем подключитесь к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b952d-105">On the **File** menu, click **New Trace**, and then connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="b952d-106">Отображается диалоговое окно **Свойства трассировки**.</span><span class="sxs-lookup"><span data-stu-id="b952d-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b952d-107">Если установлен параметр **Начать трассировку немедленно после установления соединения**, диалоговое окно **Свойства трассировки**не отображается, а вместо этого начинается трассировка.</span><span class="sxs-lookup"><span data-stu-id="b952d-107">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear and the trace begins instead.</span></span> <span data-ttu-id="b952d-108">Чтобы отключить этот параметр, в меню **Сервис**выберите пункт **Параметры**и снимите флажок **Начать трассировку немедленно после установления соединения** .</span><span class="sxs-lookup"><span data-stu-id="b952d-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="b952d-109">В поле **Имя трассировки** введите имя трассировки и нажмите кнопку **Сохранить в таблицу**.</span><span class="sxs-lookup"><span data-stu-id="b952d-109">In the **Trace name** box, type a name for the trace, and then click **Save to table**.</span></span>  
  
3.  <span data-ttu-id="b952d-110">В диалоговом окне **Соединение с сервером** подключитесь к содержащей таблицу трассировок базе данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b952d-110">In the **Connect to server** dialog box, connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database that will contain the trace table.</span></span>  
  
4.  <span data-ttu-id="b952d-111">В диалоговом окне **Целевая таблица** выберите базу данных из списка **База данных**.</span><span class="sxs-lookup"><span data-stu-id="b952d-111">In the **Destination Table** dialog box, select a database from the **Database**list.</span></span>  
  
5.  <span data-ttu-id="b952d-112">В списке **Владелец** выберите владельца трассировки.</span><span class="sxs-lookup"><span data-stu-id="b952d-112">In the **Owner** list, select the owner for the trace.</span></span>  
  
6.  <span data-ttu-id="b952d-113">В списке **Таблица** введите или выберите имя таблицы для сохранения результатов трассировки.</span><span class="sxs-lookup"><span data-stu-id="b952d-113">In the **Table** list, type or select the table name for the trace results.</span></span> <span data-ttu-id="b952d-114">Нажмите кнопку **ОК.**</span><span class="sxs-lookup"><span data-stu-id="b952d-114">Click **OK.**</span></span>  
  
7.  <span data-ttu-id="b952d-115">В диалоговом окне **Свойства трассировки** установите флажок **установить максимальное число строк (в тысячах)** , чтобы указать максимальное количество строк для сохранения.</span><span class="sxs-lookup"><span data-stu-id="b952d-115">In the **Trace Properties** dialog box, select the **Set maximum rows (in thousands)** check box to specify the maximum number of rows to save.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b952d-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="b952d-116">See Also</span></span>  
 [<span data-ttu-id="b952d-117">Приложение SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="b952d-117">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  

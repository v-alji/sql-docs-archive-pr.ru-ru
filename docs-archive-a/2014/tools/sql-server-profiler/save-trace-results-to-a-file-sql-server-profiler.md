---
title: Сохранение результатов трассировки в файл (приложение SQL Server Profiler) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- saving traces
- traces [SQL Server], saving
ms.assetid: ac528747-0c19-4f3d-96f5-44c762a4abed
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9644751cda3689cf7b7cb00ec25310bc700ca1c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737220"
---
# <a name="save-trace-results-to-a-file-sql-server-profiler"></a><span data-ttu-id="00dec-102">сохранить результаты трассировки в файл (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="00dec-102">Save Trace Results to a File (SQL Server Profiler)</span></span>
  <span data-ttu-id="00dec-103">В данном разделе описано сохранение результатов трассировки в файл с помощью [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00dec-103">This topic describes how to save trace results to a file by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-save-trace-results-to-a-file"></a><span data-ttu-id="00dec-104">Сохранение результатов трассировки в файл</span><span class="sxs-lookup"><span data-stu-id="00dec-104">To save trace results to a file</span></span>  
  
1.  <span data-ttu-id="00dec-105">В меню **Файл** выберите пункт **Создать трассировку**, а затем подключитесь к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00dec-105">On the **File** menu, click **New Trace**, and then connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="00dec-106">Отображается диалоговое окно **Свойства трассировки**.</span><span class="sxs-lookup"><span data-stu-id="00dec-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="00dec-107">Если установлен параметр **Начать трассировку немедленно после установления соединения**, диалоговое окно **Свойства трассировки**не отображается, а вместо этого начинается трассировка.</span><span class="sxs-lookup"><span data-stu-id="00dec-107">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear and the trace begins instead.</span></span> <span data-ttu-id="00dec-108">Чтобы отключить этот параметр, в меню **Сервис**выберите пункт **Параметры**и снимите флажок **Начать трассировку немедленно после установления соединения** .</span><span class="sxs-lookup"><span data-stu-id="00dec-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="00dec-109">В поле **Имя трассировки** введите имя трассировки.</span><span class="sxs-lookup"><span data-stu-id="00dec-109">In the **Trace name** box, type a name for the trace.</span></span>  
  
3.  <span data-ttu-id="00dec-110">Установите флажок **Сохранять в файл** .</span><span class="sxs-lookup"><span data-stu-id="00dec-110">Select the **Save to file** check box.</span></span>  
  
     <span data-ttu-id="00dec-111">Отображается диалоговое окно **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="00dec-111">The **Save As**dialog box appears.</span></span>  
  
4.  <span data-ttu-id="00dec-112">Укажите путь и имя файла в диалоговом окне **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="00dec-112">Specify a path and filename in the **Save As**dialog box.</span></span> <span data-ttu-id="00dec-113">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="00dec-113">Click **Save.**</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="00dec-114">Убедитесь, что служба SQL Server обладает достаточными разрешениями для записи в файл в указанном каталоге.</span><span class="sxs-lookup"><span data-stu-id="00dec-114">Ensure that the SQL Server service has sufficient permissions to write to a file in the directory specified.</span></span>  
  
5.  <span data-ttu-id="00dec-115">В диалоговом окне **Свойства трассировки** введите максимальный размер файла в поле **Максимальный размер файла (МБ)** .</span><span class="sxs-lookup"><span data-stu-id="00dec-115">In the **Trace Properties** dialog box, enter the maximum file size in the **Set maximum file size (MB)** text box.</span></span> <span data-ttu-id="00dec-116">Значение по умолчанию — 5 мегабайт.</span><span class="sxs-lookup"><span data-stu-id="00dec-116">The default value is 5 megabytes (MB).</span></span>  
  
6.  <span data-ttu-id="00dec-117">При необходимости укажите следующие необязательные параметры:</span><span class="sxs-lookup"><span data-stu-id="00dec-117">Optionally, specify the following options:</span></span>  
  
    -   <span data-ttu-id="00dec-118">Установите флажок **Включить операцию переключения на файл продолжения** , чтобы [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] создавал новые файлы данных трассировки при достижении максимального размера файла.</span><span class="sxs-lookup"><span data-stu-id="00dec-118">Select the **Enable file rollover** check box to have [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] create new files for trace data once the maximum file size is reached.</span></span> <span data-ttu-id="00dec-119">Этот параметр выбран по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="00dec-119">This option is selected by default.</span></span>  
  
    -   <span data-ttu-id="00dec-120">Установите флажок **Данные трассировки серверных процессов** , чтобы гарантировать, что сервер сохранит данные обо всех событиях трассировки.</span><span class="sxs-lookup"><span data-stu-id="00dec-120">Select the **Server processes trace data** check box to ensure that the server records each trace event.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="00dec-121">Когда флажок **Данные трассировки серверных процессов**снят, сервер не записывает события, если запись событий привела бы к существенному понижению производительности.</span><span class="sxs-lookup"><span data-stu-id="00dec-121">When **Server processes trace data**is cleared, the server does not record events if recording events significantly degrades performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00dec-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="00dec-122">See Also</span></span>  
 [<span data-ttu-id="00dec-123">Приложение SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="00dec-123">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  

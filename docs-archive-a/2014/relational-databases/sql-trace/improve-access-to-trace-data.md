---
title: Улучшение доступа к данным трассировки | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Profiler [SQL Server Profiler], space
- SQL Server Profiler, space
- space [SQL Server], SQL Server Profiler
ms.assetid: c260c000-fd53-4831-993f-df6894f3228b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 60e01ad04ddd9f7fe6d858c399abb552716f2bea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730294"
---
# <a name="improve-access-to-trace-data"></a><span data-ttu-id="de9fb-102">Улучшение доступа для трассировки данных</span><span class="sxs-lookup"><span data-stu-id="de9fb-102">Improve Access to Trace Data</span></span>
  [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="de9fb-103">использует пространство в каталоге **temp** для улучшения доступа к трассировке данных.</span><span class="sxs-lookup"><span data-stu-id="de9fb-103">uses space in the **temp** directory to improve access to trace data.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="de9fb-104">требует по крайней мере 10 мегабайт (МБ) свободного пространства.</span><span class="sxs-lookup"><span data-stu-id="de9fb-104">requires at least 10 megabytes (MB) of free space.</span></span> <span data-ttu-id="de9fb-105">Если во время работы приложения [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]объем свободного места становится менее 10 Мб, то выполнение всех функций [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] прекращается.</span><span class="sxs-lookup"><span data-stu-id="de9fb-105">If free space drops below 10 MB while you are using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], all [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] functions stop.</span></span>  
  
 <span data-ttu-id="de9fb-106">Использование приложением [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] места в каталоге **temp** может вызвать быстрое увеличение объема каталога **temp** .</span><span class="sxs-lookup"><span data-stu-id="de9fb-106">When [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] uses space in the **temp** directory, this space usage may cause the **temp** directory to grow rapidly.</span></span> <span data-ttu-id="de9fb-107">Чтобы избежать проблем с увеличением объема файлов, можно поместить каталог **temp** на диск, не являющийся системным; для этого необходимо изменить значение переменной среды TEMP.</span><span class="sxs-lookup"><span data-stu-id="de9fb-107">To avoid file-growth problems, you can place the **temp** directory on a drive that is not a system drive by changing the value for the TEMP environment variable.</span></span>  
  
 <span data-ttu-id="de9fb-108">В следующей процедуре описаны действия, необходимые для изменения значения переменной среды TEMP в большинстве операционных систем Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="de9fb-108">The following procedure describes how to change the value for the TEMP environment variable in most Microsoft Windows operating systems.</span></span> <span data-ttu-id="de9fb-109">Дополнительные сведения об установке значений переменных среды см. в документации по операционной системе Windows.</span><span class="sxs-lookup"><span data-stu-id="de9fb-109">For more information about setting environment variables, see your Windows operating system documentation.</span></span>  
  
### <a name="to-change-the-temp-environment-variable-in-windows-operating-systems"></a><span data-ttu-id="de9fb-110">Изменение значения переменной среды TEMP в операционных системах Windows</span><span class="sxs-lookup"><span data-stu-id="de9fb-110">To change the TEMP environment variable in Windows operating systems</span></span>  
  
1.  <span data-ttu-id="de9fb-111">В меню **Пуск** выберите пункт **Панель управления**, а затем выберите **Система**.</span><span class="sxs-lookup"><span data-stu-id="de9fb-111">On the **Start** menu, choose **Control Panel**, and then click **System**.</span></span>  
  
2.  <span data-ttu-id="de9fb-112">В диалоговом окне **Свойства системы** выберите вкладку **Дополнительно** , затем нажмите кнопку **Переменные среды**.</span><span class="sxs-lookup"><span data-stu-id="de9fb-112">In the **System Properties** dialog box, click the **Advanced** tab, and then click **Environment Variables**.</span></span>  
  
3.  <span data-ttu-id="de9fb-113">Прокрутите вниз список **Системные переменные**, выберите строку, соответствующую переменной **TEMP** , затем нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="de9fb-113">Scroll down the list of **System Variables**, select the row that corresponds to the **TEMP** variable, and click **Edit**.</span></span>  
  
4.  <span data-ttu-id="de9fb-114">В диалоговом окне **Изменение системной переменной** введите путь и имя диска и каталога, где необходимо разместить каталог **temp** .</span><span class="sxs-lookup"><span data-stu-id="de9fb-114">In the **Edit System Variable** dialog box, enter the path and name of the drive and directory where you want the **temp** directory to be located.</span></span>  
  
5.  <span data-ttu-id="de9fb-115">Нажмите **ОК** для сохранения изменений.</span><span class="sxs-lookup"><span data-stu-id="de9fb-115">Click **OK** to save the change.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de9fb-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="de9fb-116">See Also</span></span>  
 <span data-ttu-id="de9fb-117">[Запуск приложения SQL Server Profiler](../../tools/sql-server-profiler/start-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="de9fb-117">[Start SQL Server Profiler](../../tools/sql-server-profiler/start-sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="de9fb-118">Приложение SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="de9fb-118">SQL Server Profiler</span></span>](../../tools/sql-server-profiler/sql-server-profiler.md)  
  
  

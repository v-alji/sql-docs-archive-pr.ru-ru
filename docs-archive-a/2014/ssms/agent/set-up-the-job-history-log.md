---
title: Настройка журнала заданий | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], history
- logs [SQL Server], jobs
- SQL Server Agent jobs, history
- historical information [SQL Server], jobs
ms.assetid: 018e5c49-d3a0-4504-851a-f70996a34bb7
author: stevestein
ms.author: sstein
ms.openlocfilehash: cb42e1daaee8a3a9e5ae9cc3c09a8cc42dcbff56
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727890"
---
# <a name="set-up-the-job-history-log"></a><span data-ttu-id="28ac9-102">Set Up the Job History Log</span><span class="sxs-lookup"><span data-stu-id="28ac9-102">Set Up the Job History Log</span></span>
  <span data-ttu-id="28ac9-103">В этом разделе описывается настройка [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] журнала заданий агента.</span><span class="sxs-lookup"><span data-stu-id="28ac9-103">This topic describes how to set up the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job history log.</span></span>  
  
-   <span data-ttu-id="28ac9-104">**Перед началом работы**  [Безопасность](#Security)</span><span class="sxs-lookup"><span data-stu-id="28ac9-104">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="28ac9-105">**Для настройки журнала заданий используется:**  [Среда SQL Server Management Studio](#SSMS)</span><span class="sxs-lookup"><span data-stu-id="28ac9-105">**To setup the job history log, using:**  [SQL Server Management Studio](#SSMS)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="28ac9-106">Перед началом</span><span class="sxs-lookup"><span data-stu-id="28ac9-106">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="28ac9-107">безопасность</span><span class="sxs-lookup"><span data-stu-id="28ac9-107">Security</span></span>  
 <span data-ttu-id="28ac9-108">Дополнительные сведения см. в разделе [Обеспечение безопасности агента SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="28ac9-108">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="28ac9-109">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="28ac9-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="28ac9-110">**Настройка журнала заданий**</span><span class="sxs-lookup"><span data-stu-id="28ac9-110">**To set up the job history log**</span></span>  
  
1.  <span data-ttu-id="28ac9-111">В **обозревателе объектов** подключитесь к экземпляру [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , а затем разверните этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="28ac9-111">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="28ac9-112">Щелкните правой кнопкой мыши **агент SQL Server**, затем выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="28ac9-112">Right-click **SQL Server Agent**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="28ac9-113">В диалоговом окне **Свойства агента SQL Server** выберите страницу **Журнал** .</span><span class="sxs-lookup"><span data-stu-id="28ac9-113">In the **SQL Server Agent Properties** dialog box, select the **History** page.</span></span>  
  
4.  <span data-ttu-id="28ac9-114">Выберите один из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="28ac9-114">Choose from the following options:</span></span>  
  
    1.  <span data-ttu-id="28ac9-115">Выберите **Ограниченный размер журнала заданий**, а затем введите максимальное число строк для журнала заданий и максимальное число строк на задание.</span><span class="sxs-lookup"><span data-stu-id="28ac9-115">Check **Limit size of job history log**, and then type the maximum number of rows for the job history log, and the maximum number of rows per job.</span></span>  
  
    2.  <span data-ttu-id="28ac9-116">Выберите **Автоматически удалять журнал агента**и задайте период времени, записи старше которого будут автоматически удаляться из журнала.</span><span class="sxs-lookup"><span data-stu-id="28ac9-116">Check **Automatically remove agent history**, and specify a time period, such that history older than this period will be purged from the log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28ac9-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="28ac9-117">See Also</span></span>  
 <span data-ttu-id="28ac9-118">[Реализация заданий](implement-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="28ac9-118">[Implement Jobs](implement-jobs.md) </span></span>  
 <span data-ttu-id="28ac9-119">[Мониторинг активности заданий](monitor-job-activity.md) </span><span class="sxs-lookup"><span data-stu-id="28ac9-119">[Monitor Job Activity](monitor-job-activity.md) </span></span>  
 [<span data-ttu-id="28ac9-120">Создание заданий</span><span class="sxs-lookup"><span data-stu-id="28ac9-120">Create Jobs</span></span>](create-jobs.md)  
  
  

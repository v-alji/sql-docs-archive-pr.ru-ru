---
title: Изменение размера журнала заданий | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], history
- resizing job history log
- size [SQL Server], job history log
- logs [SQL Server], jobs
- SQL Server Agent jobs, history
- historical information [SQL Server], jobs
ms.assetid: ddee1ce8-9d1b-4017-9894-bf7256aed95d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4c25cc43295d47b2bc19d48b5b257dbbe6bcfe9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658039"
---
# <a name="resize-the-job-history-log"></a><span data-ttu-id="7b14e-102">Resize the Job History Log</span><span class="sxs-lookup"><span data-stu-id="7b14e-102">Resize the Job History Log</span></span>
  <span data-ttu-id="7b14e-103">В этом разделе описывается, как задать ограничения размера для [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] журналов заданий агента в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7b14e-103">This topic describes how to set size limits for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job history logs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="7b14e-104">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="7b14e-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7b14e-105">Безопасность</span><span class="sxs-lookup"><span data-stu-id="7b14e-105">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7b14e-106">**Для задания ограничений на размер журнала заданий используется:**</span><span class="sxs-lookup"><span data-stu-id="7b14e-106">**To set size limits for job history logs, using:**</span></span>  
  
     [<span data-ttu-id="7b14e-107">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7b14e-107">SQL Server Management Studio</span></span>](#SSMS)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7b14e-108">Перед началом</span><span class="sxs-lookup"><span data-stu-id="7b14e-108">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7b14e-109">безопасность</span><span class="sxs-lookup"><span data-stu-id="7b14e-109">Security</span></span>  
 <span data-ttu-id="7b14e-110">Дополнительные сведения см. в разделе [Обеспечение безопасности агента SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="7b14e-110">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="7b14e-111">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7b14e-111">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-resize-the-job-history-log-based-on-raw-size"></a><span data-ttu-id="7b14e-112">Изменение размера журнала заданий, основанного на необработанном размере</span><span class="sxs-lookup"><span data-stu-id="7b14e-112">To resize the job history log based on raw size</span></span>  
  
1.  <span data-ttu-id="7b14e-113">В **обозревателе объектов** подключитесь к экземпляру [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , а затем разверните этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="7b14e-113">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="7b14e-114">Щелкните правой кнопкой мыши **агент SQL Server**, затем выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="7b14e-114">Right-click **SQL Server Agent**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="7b14e-115">Выберите страницу **Журнал** и убедитесь, что флажок **Ограниченный размер журнала заданий**установлен.</span><span class="sxs-lookup"><span data-stu-id="7b14e-115">Select the **History** page, and then confirm that **Limit size of job history log**is checked.</span></span>  
  
4.  <span data-ttu-id="7b14e-116">В диалоговом окне **Максимальный размер журнала заданий** введите максимальное число строк для журнала заданий.</span><span class="sxs-lookup"><span data-stu-id="7b14e-116">In the **Maximum job history log size** box, enter the maximum number of rows the job history log should allow.</span></span>  
  
5.  <span data-ttu-id="7b14e-117">В диалоговом окне **Максимальное число строк журнала для одного задания** введите максимальное число строк журнала для одного задания.</span><span class="sxs-lookup"><span data-stu-id="7b14e-117">In the **Maximum job history rows per job** box, enter the maximum number of job history rows to allow for a job.</span></span>  
  
#### <a name="to-resize-the-job-history-log-based-on-time"></a><span data-ttu-id="7b14e-118">Изменить размера журнала заданий, основанного на времени</span><span class="sxs-lookup"><span data-stu-id="7b14e-118">To resize the job history log based on time</span></span>  
  
1.  <span data-ttu-id="7b14e-119">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]и разверните его.</span><span class="sxs-lookup"><span data-stu-id="7b14e-119">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="7b14e-120">Щелкните правой кнопкой мыши **агент SQL Server**, затем выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="7b14e-120">Right-click **SQL Server Agent**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="7b14e-121">Выберите страницу **Журнал** и щелкните **Автоматически удалять журнал агента**.</span><span class="sxs-lookup"><span data-stu-id="7b14e-121">Select the **History** page, and then click **Automatically remove agent history**.</span></span>  
  
4.  <span data-ttu-id="7b14e-122">Выберите подходящее количество **дней**, **недель**или **месяцев**.</span><span class="sxs-lookup"><span data-stu-id="7b14e-122">Select the appropriate number of **Days(s)**, **Week(s)**, or **Month(s)**.</span></span>  
  
  

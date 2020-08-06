---
title: Установка времени и длительности простоя ЦП (среда SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- CPU [SQL Server], idle conditions
- time [SQL Server], CPU idle and duration
- duration of CPU idle [SQL Server]
- SQL Server Agent, CPU idle conditions
- idle time [SQL Server]
ms.assetid: 8647b465-d899-4cc7-9640-134a506d0a2e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1660f6d70977b8f590a18adf952a6a19f32a26cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751635"
---
# <a name="set-cpu-idle-time-and-duration-sql-server-management-studio"></a><span data-ttu-id="e8009-102">Установка времени и длительности простоя ЦП (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="e8009-102">Set CPU Idle Time and Duration (SQL Server Management Studio)</span></span>
  <span data-ttu-id="e8009-103">В этом разделе рассказывается о том, как задать условие простоя ЦП для сервера в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8009-103">This topic explains how to define the CPU idle condition for your server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="e8009-104">Определение простоя ЦП влияет на [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] реакцию агента на события.</span><span class="sxs-lookup"><span data-stu-id="e8009-104">The CPU idle definition influences how [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent responds to events.</span></span> <span data-ttu-id="e8009-105">Например, предположим, определены такие условия простоя ЦП, что средняя загрузка ЦП не превышает 10% и остается на этом уровне в течение 10 минут.</span><span class="sxs-lookup"><span data-stu-id="e8009-105">For example, suppose that you define the CPU idle condition as when the average CPU usage falls below 10 percent and remains at this level for 10 minutes.</span></span> <span data-ttu-id="e8009-106">Тогда, если определены задания, которые должны выполняться при достижении ЦП сервера условий простоя, выполнение задания начнется, как только загрузка ЦП упадет ниже 10% и пробудет на этом уровне 10 минут.</span><span class="sxs-lookup"><span data-stu-id="e8009-106">Then if you have defined jobs to execute whenever the server CPU reaches an idle condition, the job will start when the CPU usage falls below 10 percent and remains at that level for 10 minutes.</span></span> <span data-ttu-id="e8009-107">Если это задание существенно влияет на производительность сервера, определение условий простоя ЦП имеет очень большое значение.</span><span class="sxs-lookup"><span data-stu-id="e8009-107">If this is a job that significantly impacts the performance of your server, how you define the CPU idle condition is important.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e8009-108">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e8009-108">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-cpu-idle-time-and-duration"></a><span data-ttu-id="e8009-109">Задание времени и продолжительности простоя ЦП</span><span class="sxs-lookup"><span data-stu-id="e8009-109">To set CPU idle time and duration</span></span>  
  
1.  <span data-ttu-id="e8009-110">В **обозревателе объектов** подключитесь к экземпляру [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , а затем разверните этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="e8009-110">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="e8009-111">Щелкните правой кнопкой мыши **Агент SQL Server**, выберите **Свойства**и перейдите на страницу **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="e8009-111">Right-click **SQL Server Agent**, click **Properties**, and select the **Advanced** page.</span></span>  
  
3.  <span data-ttu-id="e8009-112">В области **Условие бездействия ЦП**выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e8009-112">Under **Idle CPU condition**, do the following:</span></span>  
  
    -   <span data-ttu-id="e8009-113">Установите флажок **Определите условие бездействия ЦП**.</span><span class="sxs-lookup"><span data-stu-id="e8009-113">Check **Define idle CPU condition.**</span></span>  
  
    -   <span data-ttu-id="e8009-114">Укажите процент загрузки ЦП в поле **Среднее время использования ЦП сократилось до** (для всех процессоров).</span><span class="sxs-lookup"><span data-stu-id="e8009-114">Specify a percentage for the **Average CPU usage falls below** (across all CPUs) box.</span></span> <span data-ttu-id="e8009-115">Так задается максимальный уровень загрузки для времени простоя ЦП.</span><span class="sxs-lookup"><span data-stu-id="e8009-115">This sets the usage level that the CPU must fall below before it is considered idle.</span></span>  
  
    -   <span data-ttu-id="e8009-116">Укажите количество секунд в поле **И остается ниже этого уровня в течение** .</span><span class="sxs-lookup"><span data-stu-id="e8009-116">Specify a number of seconds for the **And remains below this level for** box.</span></span> <span data-ttu-id="e8009-117">Так задается промежуток времени, в течение которого должен сохраняться минимальный уровень загрузки ЦП, чтобы считать это простоем.</span><span class="sxs-lookup"><span data-stu-id="e8009-117">This sets the duration that the minimum CPU usage must remain at before it is considered idle.</span></span>  
  
  

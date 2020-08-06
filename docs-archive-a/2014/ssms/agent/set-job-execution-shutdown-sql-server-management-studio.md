---
title: Настройка интервала ожидания задания при завершении работы (SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], stopping
- SQL Server Agent jobs, stopping
- stopping jobs
- SQL Server Agent jobs, execution shutdowns
ms.assetid: ac23e88f-53fc-41de-bb16-0c27c002d5a5
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0e60807676c3c54faf1d44de318ff0a31c2e20b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667534"
---
# <a name="set-job-execution-shutdown-sql-server-management-studio"></a><span data-ttu-id="ed8b3-102">Настройка интервала ожидания задания при завершении работы (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="ed8b3-102">Set Job Execution Shutdown (SQL Server Management Studio)</span></span>
  <span data-ttu-id="ed8b3-103">В этом разделе описывается, как задать время, в течение которого [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] агент будет ожидать завершения выполнения заданий [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , прежде чем сам агент завершит работу с [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ed8b3-103">This topic describes how to set the time that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent will wait for executing jobs to finish before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent itself finishes in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="ed8b3-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="ed8b3-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ed8b3-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="ed8b3-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ed8b3-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="ed8b3-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ed8b3-107">**Установка времени завершения работы задания агента SQL Server**</span><span class="sxs-lookup"><span data-stu-id="ed8b3-107">**To set a shutdown time for a SQL Server Agent job, using:**</span></span>  
  
     [<span data-ttu-id="ed8b3-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ed8b3-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ed8b3-109">Перед началом</span><span class="sxs-lookup"><span data-stu-id="ed8b3-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ed8b3-110">безопасность</span><span class="sxs-lookup"><span data-stu-id="ed8b3-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ed8b3-111">Permissions</span><span class="sxs-lookup"><span data-stu-id="ed8b3-111">Permissions</span></span>  
 <span data-ttu-id="ed8b3-112">По умолчанию члены предопределенной роли сервера **sysadmin** могут задавать время, в течение которого агент [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] будет ожидать выполнения заданий до того момента, как завершит работу агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed8b3-112">By default, members of the **sysadmin** fixed server role can set the time that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent will wait for executing jobs to finish before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent itself finishes.</span></span> <span data-ttu-id="ed8b3-113">Другим пользователям должна быть предоставлена одна из следующих предопределенных ролей базы данных агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в базе данных **msdb** :</span><span class="sxs-lookup"><span data-stu-id="ed8b3-113">Other users must be granted one of the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles in the **msdb** database:</span></span>  
  
-   <span data-ttu-id="ed8b3-114">**SQLAgentUserRole**</span><span class="sxs-lookup"><span data-stu-id="ed8b3-114">**SQLAgentUserRole**</span></span>  
  
-   <span data-ttu-id="ed8b3-115">**SQLAgentReaderRole**</span><span class="sxs-lookup"><span data-stu-id="ed8b3-115">**SQLAgentReaderRole**</span></span>  
  
-   <span data-ttu-id="ed8b3-116">**SQLAgentOperatorRole**</span><span class="sxs-lookup"><span data-stu-id="ed8b3-116">**SQLAgentOperatorRole**</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ed8b3-117">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ed8b3-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-job-execution-shutdown"></a><span data-ttu-id="ed8b3-118">Настройка завершения выполнения заданий</span><span class="sxs-lookup"><span data-stu-id="ed8b3-118">To set job execution shutdown</span></span>  
  
1.  <span data-ttu-id="ed8b3-119">В **обозревателе объектов** щелкните значок «плюс», чтобы развернуть сервер, на котором необходимо установить интервал выполнения задания.</span><span class="sxs-lookup"><span data-stu-id="ed8b3-119">In **Object Explorer,** , click the plus sign to expand the server where you want to set a job execution shutdown interval.</span></span>  
  
2.  <span data-ttu-id="ed8b3-120">Щелкните правой кнопкой мыши **Агент SQL Server** и выберите пункт **свойства**.</span><span class="sxs-lookup"><span data-stu-id="ed8b3-120">Right-click **SQL Server Agent** and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="ed8b3-121">В разделе **Выбор страницы**выберите пункт **Система заданий**.</span><span class="sxs-lookup"><span data-stu-id="ed8b3-121">Under **Select a page**, select **Job System**.</span></span>  
  
4.  <span data-ttu-id="ed8b3-122">Установите **Интервал ожидания при завершении работы** в секундах, чтобы увеличить или уменьшить длительность ожидания завершения работы.</span><span class="sxs-lookup"><span data-stu-id="ed8b3-122">Set the **Shutdown time-out interval** in seconds to increase or decrease the shutdown time-out interval.</span></span> <span data-ttu-id="ed8b3-123">Этот параметр определяет, как долго агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] будет ожидать завершения выполняющихся заданий перед завершением работы самого агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ed8b3-123">This determines how long [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent will wait for executing jobs to finish before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent itself finishes.</span></span>  
  
  

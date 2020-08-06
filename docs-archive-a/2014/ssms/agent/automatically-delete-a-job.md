---
title: Автоматическое удаление задания | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- dropping jobs
- SQL Server Agent jobs, removing
- automatic job removal
- jobs [SQL Server Agent], deleting
- deleting jobs
- removing jobs
ms.assetid: 92dbb6da-5919-4bde-9354-d454e9ea3da0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 07a10ec4a31d553a548bfecdcba426e3b46a1782
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665766"
---
# <a name="automatically-delete-a-job"></a><span data-ttu-id="f29ed-102">Автоматическое удаление задания</span><span class="sxs-lookup"><span data-stu-id="f29ed-102">Automatically Delete a Job</span></span>
  <span data-ttu-id="f29ed-103">В этом разделе описывается настройка [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] агента в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] для автоматического удаления заданий при их успешном выполнении, сбое или завершении с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или управляющие объекты SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f29ed-103">This topic describes how to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] to automatically delete jobs when they succeed, fail, or complete by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="f29ed-104">Ответы заданий дают гарантию того, что администраторы базы данных будут знать о завершении выполнения заданий и частоте их выполнения.</span><span class="sxs-lookup"><span data-stu-id="f29ed-104">Job responses ensure that database administrators know when jobs complete and how frequently they run.</span></span> <span data-ttu-id="f29ed-105">Обычными ответами заданий являются следующие.</span><span class="sxs-lookup"><span data-stu-id="f29ed-105">Typical job responses include:</span></span>  
  
-   <span data-ttu-id="f29ed-106">Уведомление оператора с помощью электронной почты, системы пейджинга или сообщения **net send** .</span><span class="sxs-lookup"><span data-stu-id="f29ed-106">Notifying the operator by using e-mail, electronic paging, or a **net send** message.</span></span>  
  
     <span data-ttu-id="f29ed-107">Используйте один из этих ответов на задание, если оператор должен выполнить последующие действия.</span><span class="sxs-lookup"><span data-stu-id="f29ed-107">Use one of these job responses if the operator must perform a follow-up action.</span></span> <span data-ttu-id="f29ed-108">Например, после успешного выполнения задания резервного копирования оператор должен получить напоминание об удалении магнитной ленты с резервной копией и сохранении ее в безопасном месте.</span><span class="sxs-lookup"><span data-stu-id="f29ed-108">For example, if a backup job completes successfully, the operator must be notified to remove the backup tape and store it in a safe location.</span></span>  
  
-   <span data-ttu-id="f29ed-109">Запись сообщений о событиях в журнал приложений Windows.</span><span class="sxs-lookup"><span data-stu-id="f29ed-109">Writing an event message to the Windows application log.</span></span>  
  
     <span data-ttu-id="f29ed-110">Этот ответ можно использовать только для неудачно завершившихся заданий.</span><span class="sxs-lookup"><span data-stu-id="f29ed-110">You can use this response only for failed jobs.</span></span>  
  
-   <span data-ttu-id="f29ed-111">Автоматическое удаление задания.</span><span class="sxs-lookup"><span data-stu-id="f29ed-111">Automatically deleting the job.</span></span>  
  
     <span data-ttu-id="f29ed-112">Используйте этот ответ только тогда, когда есть уверенность в том, что не понадобится выполнять это задание повторно.</span><span class="sxs-lookup"><span data-stu-id="f29ed-112">Use this job response if you are certain that you do not need to rerun this job.</span></span>  
  
 <span data-ttu-id="f29ed-113">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="f29ed-113">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f29ed-114">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="f29ed-114">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f29ed-115">Безопасность</span><span class="sxs-lookup"><span data-stu-id="f29ed-115">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f29ed-116">**Для задания ответов заданий используется:**</span><span class="sxs-lookup"><span data-stu-id="f29ed-116">**To specify job responses, using:**</span></span>  
  
     [<span data-ttu-id="f29ed-117">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f29ed-117">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="f29ed-118">Управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="f29ed-118">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f29ed-119">Перед началом</span><span class="sxs-lookup"><span data-stu-id="f29ed-119">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f29ed-120">безопасность</span><span class="sxs-lookup"><span data-stu-id="f29ed-120">Security</span></span>  
 <span data-ttu-id="f29ed-121">Дополнительные сведения см. в разделе [Обеспечение безопасности агента SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="f29ed-121">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="f29ed-122">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f29ed-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-automatically-delete-a-job"></a><span data-ttu-id="f29ed-123">Автоматическое удаление задания</span><span class="sxs-lookup"><span data-stu-id="f29ed-123">To automatically delete a job</span></span>  
  
1.  <span data-ttu-id="f29ed-124">В **обозревателе объектов** подключитесь к экземпляру [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , а затем разверните этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="f29ed-124">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="f29ed-125">Разверните узел **Агент SQL Server**, выберите раздел **Задания**, щелкните правой кнопкой мыши задание, которое нужно изменить, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="f29ed-125">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to edit, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="f29ed-126">Выберите страницу **Уведомления** .</span><span class="sxs-lookup"><span data-stu-id="f29ed-126">Select the **Notifications** page.</span></span>  
  
4.  <span data-ttu-id="f29ed-127">Поставьте флажок **Автоматически удалить задание**и выберите одно из следующих.</span><span class="sxs-lookup"><span data-stu-id="f29ed-127">Check **Automatically delete job**, and choose one of the following:</span></span>  
  
    -   <span data-ttu-id="f29ed-128">Чтобы задание автоматически удалялось при его успешном завершении, выберите пункт **При успешном завершении задания** .</span><span class="sxs-lookup"><span data-stu-id="f29ed-128">Click **When the job succeeds** to delete the job status when it has completed successfully.</span></span>  
  
    -   <span data-ttu-id="f29ed-129">Чтобы задание автоматически удалялось в случае неуспешного завершения, выберите пункт **При ошибке задания** .</span><span class="sxs-lookup"><span data-stu-id="f29ed-129">Click **When the job fails** to delete the job when it has completed unsuccessfully.</span></span>  
  
    -   <span data-ttu-id="f29ed-130">Чтобы задание автоматически удалялось по завершении в любом случае, выберите пункт **По завершении задания** .</span><span class="sxs-lookup"><span data-stu-id="f29ed-130">Click **When the job completes** to delete the job regardless of completion status.</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="f29ed-131">Использование управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="f29ed-131">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="f29ed-132">**Автоматическое удаление задания**</span><span class="sxs-lookup"><span data-stu-id="f29ed-132">**To automatically delete a job**</span></span>  
  
 <span data-ttu-id="f29ed-133">Вызовите свойство `DeleteLevel` класса `Job`, используя выбранный язык программирования, например Visual Basic, Visual C# или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f29ed-133">Use the `DeleteLevel` property of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="f29ed-134">Дополнительные сведения см. в статье [Управляющие объекты SQL Server (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="f29ed-134">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
  
  

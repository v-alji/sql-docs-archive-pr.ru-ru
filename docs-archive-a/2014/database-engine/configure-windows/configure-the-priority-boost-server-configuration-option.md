---
title: Настройка параметра конфигурации сервера "priority boost" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- priority boost option
ms.assetid: 765f1e83-dd52-44fb-b0c8-1078f213607b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f42d7d2022e07dcac3039557295dc70e4500583d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657885"
---
# <a name="configure-the-priority-boost-server-configuration-option"></a><span data-ttu-id="a4689-102">Настройка параметра конфигурации сервера priority boost</span><span class="sxs-lookup"><span data-stu-id="a4689-102">Configure the priority boost Server Configuration Option</span></span>
  <span data-ttu-id="a4689-103">В этом разделе описывается настройка параметра конфигурации сервера **priority boost** в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4689-103">This topic describes how to configure the **priority boost** configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="a4689-104">С помощью параметра **priority boost** задается, должен ли [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] выполняться с большим приоритетом в [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 2008 или Windows 2008 R2 по сравнению с остальными процессами на том же компьютере.</span><span class="sxs-lookup"><span data-stu-id="a4689-104">Use the **priority boost** option to specify whether [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should run at a higher [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 2008 or Windows 2008 R2 scheduling priority than other processes on the same computer.</span></span> <span data-ttu-id="a4689-105">Если установить этот параметр в значение 1, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] выполняется в планировщике Windows 2008 или Windows Server 2008 R2 с базовым приоритетом 13.</span><span class="sxs-lookup"><span data-stu-id="a4689-105">If you set this option to 1, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] runs at a priority base of 13 in the Windows 2008 or Windows Server 2008 R2 scheduler.</span></span> <span data-ttu-id="a4689-106">Значением по умолчанию является 0, что соответствует базовому значению приоритета 7.</span><span class="sxs-lookup"><span data-stu-id="a4689-106">The default is 0, which is a priority base of 7.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)]  
  
 <span data-ttu-id="a4689-107">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="a4689-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a4689-108">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="a4689-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a4689-109">Ограничения</span><span class="sxs-lookup"><span data-stu-id="a4689-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="a4689-110">Безопасность</span><span class="sxs-lookup"><span data-stu-id="a4689-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a4689-111">**Настройка параметра повышения приоритета с помощью:**</span><span class="sxs-lookup"><span data-stu-id="a4689-111">**To configure the priority boost option, using:**</span></span>  
  
     [<span data-ttu-id="a4689-112">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a4689-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a4689-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a4689-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="a4689-114">**Дальнейшие действия.**  [После настройки параметра priority boost](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="a4689-114">**Follow Up:**  [After you configure the priority boost option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a4689-115">Перед началом</span><span class="sxs-lookup"><span data-stu-id="a4689-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="a4689-116">Ограничения</span><span class="sxs-lookup"><span data-stu-id="a4689-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="a4689-117">Задание слишком высокого приоритета может лишить ресурсов операционную систему и сетевые функции, что может вызвать проблемы при завершении работы SQL Server и выполнении на сервере других административных задач.</span><span class="sxs-lookup"><span data-stu-id="a4689-117">Raising the priority too high may drain resources from essential operating system and network functions, resulting in problems shutting down SQL Server or using other operating system tasks on the server.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a4689-118">безопасность</span><span class="sxs-lookup"><span data-stu-id="a4689-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a4689-119">Permissions</span><span class="sxs-lookup"><span data-stu-id="a4689-119">Permissions</span></span>  
 <span data-ttu-id="a4689-120">Разрешения на выполнение хранимой процедуры **sp_configure** без параметров или только с первым параметром по умолчанию предоставляются всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="a4689-120">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="a4689-121">Для выполнения процедуры **sp_configure** с обоими параметрами для изменения параметра конфигурации или запуска инструкции RECONFIGURE необходимо иметь разрешение ALTER SETTINGS на уровне сервера.</span><span class="sxs-lookup"><span data-stu-id="a4689-121">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="a4689-122">Разрешение ALTER SETTINGS неявным образом предоставлено предопределенным ролям сервера **sysadmin** и **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="a4689-122">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a4689-123">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a4689-123">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-priority-boost-option"></a><span data-ttu-id="a4689-124">Настройка параметра повышения приоритета</span><span class="sxs-lookup"><span data-stu-id="a4689-124">To configure the priority boost option</span></span>  
  
1.  <span data-ttu-id="a4689-125">В обозревателе объектов щелкните правой кнопкой мыши сервер и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="a4689-125">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="a4689-126">Щелкните узел **Процессоры** .</span><span class="sxs-lookup"><span data-stu-id="a4689-126">Click the **Processors** node.</span></span>  
  
3.  <span data-ttu-id="a4689-127">В разделе **Потоки**установите флажок **Повысить приоритет SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="a4689-127">Under **Threads**, select the **Boost SQL Server priority** check box.</span></span>  
  
4.  <span data-ttu-id="a4689-128">Остановите и снова запустите [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4689-128">Stop and restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a4689-129">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a4689-129">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-priority-boost-option"></a><span data-ttu-id="a4689-130">Настройка параметра повышения приоритета</span><span class="sxs-lookup"><span data-stu-id="a4689-130">To configure the priority boost option</span></span>  
  
1.  <span data-ttu-id="a4689-131">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4689-131">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a4689-132">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="a4689-132">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a4689-133">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="a4689-133">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="a4689-134">В этом примере описывается использование процедуры [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) для задания значения параметра `priority boost` равным `1`.</span><span class="sxs-lookup"><span data-stu-id="a4689-134">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `priority boost` option to `1`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'priority boost', 1 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="a4689-135">Дополнительные сведения см. в разделе [Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="a4689-135">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-priority-boost-option"></a><a name="FollowUp"></a> <span data-ttu-id="a4689-136">Дальнейшие действия. После настройки параметра priority boost</span><span class="sxs-lookup"><span data-stu-id="a4689-136">Follow Up: After you configure the priority boost option</span></span>  
 <span data-ttu-id="a4689-137">Чтобы изменения вступили в силу, необходимо перезапустить сервер.</span><span class="sxs-lookup"><span data-stu-id="a4689-137">The server must be restarted before the setting can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4689-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="a4689-138">See Also</span></span>  
 <span data-ttu-id="a4689-139">[RECONFIGURE (Transact-SQL)](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a4689-139">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="a4689-140">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a4689-140">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="a4689-141">sp_configure (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a4689-141">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  

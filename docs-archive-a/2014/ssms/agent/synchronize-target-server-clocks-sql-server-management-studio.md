---
title: Синхронизация часов на целевых серверах (SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, target servers
- clocks [SQL Server]
- master servers [SQL Server], clock synchronization
- synchronization [SQL Server], target server clocks
- target servers [SQL Server], clock synchronization
ms.assetid: 4fb80502-d271-4d06-bcbc-bfbbceb5f2a2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8e7150cd42699503ab22cdd89fb6206194bd64e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727885"
---
# <a name="synchronize-target-server-clocks-sql-server-management-studio"></a><span data-ttu-id="03e91-102">Synchronize Target Server Clocks (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="03e91-102">Synchronize Target Server Clocks (SQL Server Management Studio)</span></span>
  <span data-ttu-id="03e91-103">В этом разделе описано, как в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] синхронизировать часы на целевом сервере с часами на главном сервере с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03e91-103">This topic describes how to synchronize target server clocks in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] with the master server clock by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="03e91-104">Синхронизация этих системных часов обслуживает расписания заданий.</span><span class="sxs-lookup"><span data-stu-id="03e91-104">Synchronizing these system clocks supports your job schedules.</span></span>  
  
 <span data-ttu-id="03e91-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="03e91-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="03e91-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="03e91-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="03e91-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="03e91-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="03e91-108">**Синхронизация часов целевого сервера с помощью:**</span><span class="sxs-lookup"><span data-stu-id="03e91-108">**To synchronize target server clocks, using:**</span></span>  
  
     [<span data-ttu-id="03e91-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="03e91-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="03e91-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="03e91-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="03e91-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="03e91-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="03e91-112">безопасность</span><span class="sxs-lookup"><span data-stu-id="03e91-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="03e91-113">Permissions</span><span class="sxs-lookup"><span data-stu-id="03e91-113">Permissions</span></span>  
 <span data-ttu-id="03e91-114">Необходимо членство в предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="03e91-114">Requires membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="03e91-115">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="03e91-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-synchronize-target-server-clocks"></a><span data-ttu-id="03e91-116">Синхронизация часов целевых серверов</span><span class="sxs-lookup"><span data-stu-id="03e91-116">To synchronize target server clocks</span></span>  
  
1.  <span data-ttu-id="03e91-117">В **обозревателе объектов** щелкните значок «плюс», чтобы развернуть сервер, где необходимо синхронизировать часы целевого сервера с часами главного сервера.</span><span class="sxs-lookup"><span data-stu-id="03e91-117">In **Object Explorer,** click the plus sign to expand the server where you want to synchronize the target server clocks with the master server clock.</span></span>  
  
2.  <span data-ttu-id="03e91-118">Щелкните правой кнопкой мыши элемент **Агент SQL Server**, укажите пункт **Администрирование нескольких серверов**, а затем выберите пункт **Управление целевыми серверами**.</span><span class="sxs-lookup"><span data-stu-id="03e91-118">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and select **Manage Target Servers**.</span></span>  
  
3.  <span data-ttu-id="03e91-119">В диалоговом окне **Управление целевыми серверами** нажмите кнопку **Отправить инструкции**.</span><span class="sxs-lookup"><span data-stu-id="03e91-119">In the **Manage Target Servers** dialog box, click **Post Instructions**.</span></span>  
  
4.  <span data-ttu-id="03e91-120">В списке **Тип инструкции** выберите **Синхронизировать часы**.</span><span class="sxs-lookup"><span data-stu-id="03e91-120">In the **Instruction type** list, select **Synchronize clocks**.</span></span>  
  
5.  <span data-ttu-id="03e91-121">В пункте **Адресаты**выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="03e91-121">Under **Recipients**, do one of the following:</span></span>  
  
    -   <span data-ttu-id="03e91-122">Установите флажок **Все целевые серверы** , чтобы синхронизировать часы всех целевых серверов с часами главного сервера.</span><span class="sxs-lookup"><span data-stu-id="03e91-122">Click **All target servers** to synchronize all target server clocks with the master server clock.</span></span>  
  
    -   <span data-ttu-id="03e91-123">Установите флажок **Эти целевые серверы** , чтобы синхронизировать часы определенных серверов, затем выберите целевые серверы, часы которых необходимо синхронизировать с часами главного сервера.</span><span class="sxs-lookup"><span data-stu-id="03e91-123">Click **These target servers** to synchronize certain server clocks, and then select each target server whose clock you want to synchronize with the master server clock.</span></span>  
  
6.  <span data-ttu-id="03e91-124">После завершения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="03e91-124">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="03e91-125">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="03e91-125">Using Transact-SQL</span></span>  
  
#### <a name="to-synchronize-target-server-clocks"></a><span data-ttu-id="03e91-126">Синхронизация часов целевых серверов</span><span class="sxs-lookup"><span data-stu-id="03e91-126">To synchronize target server clocks</span></span>  
  
1.  <span data-ttu-id="03e91-127">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03e91-127">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="03e91-128">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="03e91-128">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="03e91-129">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="03e91-129">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb ;  
    GO  
    -- resynchronizes the SEATTLE1 target server  
    EXEC dbo.sp_resync_targetserver  
        N'SEATTLE1' ;  
    GO  
    ```  
  
 <span data-ttu-id="03e91-130">Дополнительные сведения см. в разделе [sp_resync_targetserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-resync-targetserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="03e91-130">For more information, see [sp_resync_targetserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-resync-targetserver-transact-sql).</span></span>  
  
  

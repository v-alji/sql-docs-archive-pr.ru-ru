---
title: Отключение или повторное включение предупреждения | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, alerts
- alerts [SQL Server], reactivating
- deleting alerts
- canceling alerts
- dropping alerts
- disabling alerts
- alerts [SQL Server], disabling
- reactivating alerts
- removing alerts
ms.assetid: 4cb37dc6-1134-405d-8590-58b44dcf63b2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3eec4ea7288f4847c0e9b861d80f23eb9c9ddba8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734922"
---
# <a name="disable-or-reactivate-an-alert"></a><span data-ttu-id="66f1d-102">Disable or Reactivate an Alert</span><span class="sxs-lookup"><span data-stu-id="66f1d-102">Disable or Reactivate an Alert</span></span>
  <span data-ttu-id="66f1d-103">В этом разделе описывается, как отключить или повторно активировать [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] предупреждение агента в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="66f1d-103">This topic describes how to disable or reactivate a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="66f1d-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="66f1d-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="66f1d-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="66f1d-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="66f1d-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="66f1d-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="66f1d-107">**Отключение или повторное включение предупреждения с помощью:**</span><span class="sxs-lookup"><span data-stu-id="66f1d-107">**To disable or reactivate an alert, using:**</span></span>  
  
     [<span data-ttu-id="66f1d-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="66f1d-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="66f1d-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="66f1d-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="66f1d-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="66f1d-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="66f1d-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="66f1d-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="66f1d-112">Permissions</span><span class="sxs-lookup"><span data-stu-id="66f1d-112">Permissions</span></span>  
 <span data-ttu-id="66f1d-113">По умолчанию только члены предопределенной роли сервера **sysadmin** могут изменять сведения в предупреждении.</span><span class="sxs-lookup"><span data-stu-id="66f1d-113">By default, members of the **sysadmin** fixed server role can edit information in an alert.</span></span> <span data-ttu-id="66f1d-114">Другим пользователям должна быть предоставлена предопределенная роль базы данных **SQLAgentOperatorRole** в базе данных **msdb** .</span><span class="sxs-lookup"><span data-stu-id="66f1d-114">Other users must be granted the **SQLAgentOperatorRole** fixed database role in the **msdb** database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="66f1d-115">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="66f1d-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-or-reactivate-an-alert"></a><span data-ttu-id="66f1d-116">Отключение или повторное включение предупреждения</span><span class="sxs-lookup"><span data-stu-id="66f1d-116">To disable or reactivate an alert</span></span>  
  
1.  <span data-ttu-id="66f1d-117">В **обозревателе объектов**щелкните знак «плюс», чтобы развернуть сервер, содержащий предупреждение, которое необходимо отключить или включить повторно.</span><span class="sxs-lookup"><span data-stu-id="66f1d-117">In **Object Explorer**, click the plus sign to expand server that contains the alert you wish to disable or reactivate.</span></span>  
  
2.  <span data-ttu-id="66f1d-118">Щелкните знак "плюс", чтобы развернуть **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="66f1d-118">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="66f1d-119">Чтобы развернуть папку **Предупреждения** , щелкните значок "плюс".</span><span class="sxs-lookup"><span data-stu-id="66f1d-119">Click the plus sign to expand the **Alerts** folder.</span></span>  
  
4.  <span data-ttu-id="66f1d-120">Правой кнопкой мыши щелкните предупреждение, которое необходимо включить, и выберите **Включить** . Для отключения предупреждения щелкните правой кнопкой мыши предупреждение, которое необходимо отключить, и выберите **Отключить**.</span><span class="sxs-lookup"><span data-stu-id="66f1d-120">Right-click the alert you wish to enable and select **Enable** To disable an alert, right-click the alert you want to disable and select **Disable**.</span></span>  
  
5.  <span data-ttu-id="66f1d-121">В диалоговом окне **Отключить предупреждение** или **Включить предупреждение** показано состояние процесса.</span><span class="sxs-lookup"><span data-stu-id="66f1d-121">The **Disable Alert** or **Enable Alert** dialog box displays showing the status of the process.</span></span> <span data-ttu-id="66f1d-122">После завершения нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="66f1d-122">When finished, click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="66f1d-123">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="66f1d-123">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-or-reactivate-an-alert"></a><span data-ttu-id="66f1d-124">Отключение или повторное включение предупреждения</span><span class="sxs-lookup"><span data-stu-id="66f1d-124">To disable or reactivate an alert</span></span>  
  
1.  <span data-ttu-id="66f1d-125">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="66f1d-125">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="66f1d-126">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="66f1d-126">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="66f1d-127">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="66f1d-127">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- changes the enabled setting of Test Alert to 0  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_alert  
        @name = N'Test Alert',  
        @enabled = 0 ;  
    GO  
    ```  
  
 <span data-ttu-id="66f1d-128">Дополнительные сведения см. в разделе [sp_update_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="66f1d-128">For more information, see [sp_update_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql).</span></span>  
  
  

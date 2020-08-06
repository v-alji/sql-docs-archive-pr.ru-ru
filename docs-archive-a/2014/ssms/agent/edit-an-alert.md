---
title: Изменение предупреждения | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, alerts
- alerts [SQL Server], modifying
- modifying alerts
ms.assetid: f518e528-cc8f-446a-b37d-98505b86e430
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1eae606b3c2ca4c18d088e650e774986d4e31387
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665214"
---
# <a name="edit-an-alert"></a><span data-ttu-id="6c715-102">Изменение предупреждения</span><span class="sxs-lookup"><span data-stu-id="6c715-102">Edit an Alert</span></span>
  <span data-ttu-id="6c715-103">В этом разделе описывается, как изменить [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] предупреждение агента в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6c715-103">This topic describes how to edit a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="6c715-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="6c715-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6c715-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="6c715-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6c715-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="6c715-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6c715-107">**Изменение оповещения с помощью:**</span><span class="sxs-lookup"><span data-stu-id="6c715-107">**To edit an alert, using:**</span></span>  
  
     [<span data-ttu-id="6c715-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6c715-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="6c715-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6c715-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6c715-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="6c715-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6c715-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="6c715-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6c715-112">Permissions</span><span class="sxs-lookup"><span data-stu-id="6c715-112">Permissions</span></span>  
 <span data-ttu-id="6c715-113">По умолчанию только члены предопределенной роли сервера **sysadmin** могут изменять сведения в предупреждении.</span><span class="sxs-lookup"><span data-stu-id="6c715-113">By default, members of the **sysadmin** fixed server role can edit information in an alert.</span></span> <span data-ttu-id="6c715-114">Другим пользователям должна быть предоставлена предопределенная роль базы данных **SQLAgentOperatorRole** в базе данных **msdb** .</span><span class="sxs-lookup"><span data-stu-id="6c715-114">Other users must be granted the **SQLAgentOperatorRole** fixed database role in the **msdb** database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6c715-115">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6c715-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-edit-an-alert"></a><span data-ttu-id="6c715-116">Изменение предупреждения</span><span class="sxs-lookup"><span data-stu-id="6c715-116">To edit an alert</span></span>  
  
1.  <span data-ttu-id="6c715-117">В **обозревателе объектов** щелкните значок «плюс», чтобы развернуть сервер, содержащий предупреждение, данные которого нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="6c715-117">In **Object Explorer,** click the plus sign to expand the server containing the alert you want to edit.</span></span>  
  
2.  <span data-ttu-id="6c715-118">Щелкните знак "плюс", чтобы развернуть **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="6c715-118">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="6c715-119">Чтобы развернуть папку **Предупреждения** , щелкните значок "плюс".</span><span class="sxs-lookup"><span data-stu-id="6c715-119">Click the plus sign to expand the **Alerts** folder.</span></span>  
  
4.  <span data-ttu-id="6c715-120">Щелкните правой кнопкой мыши предупреждение, которое необходимо изменить, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="6c715-120">Right-click the alert you want to edit and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="6c715-121">Обновите свойства предупреждения на страницах **Общие**, **Отклик**и **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="6c715-121">Update the alert properties on the **General**, **Response**, and **Options** pages.</span></span>  
  
6.  <span data-ttu-id="6c715-122">После завершения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6c715-122">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6c715-123">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6c715-123">Using Transact-SQL</span></span>  
  
#### <a name="to-edit-an-alert"></a><span data-ttu-id="6c715-124">Изменение предупреждения</span><span class="sxs-lookup"><span data-stu-id="6c715-124">To edit an alert</span></span>  
  
1.  <span data-ttu-id="6c715-125">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6c715-125">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6c715-126">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="6c715-126">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6c715-127">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="6c715-127">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- changes the enabled setting of Test Alert to 0  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_alert  
        @name = N'Test Alert',  
        @enabled = 0 ;  
    GO  
    ```  
  
 <span data-ttu-id="6c715-128">Дополнительные сведения см. в разделе [sp_update_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6c715-128">For more information, see [sp_update_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql).</span></span>  
  
  

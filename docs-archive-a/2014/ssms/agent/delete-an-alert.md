---
title: Удаление предупреждения | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, alerts
- alerts [SQL Server], deleting
- deleting alerts
- canceling alerts
- dropping alerts
- disabling alerts
- removing alerts
ms.assetid: c982b208-e2d1-4d34-8cee-940b9baf6586
author: stevestein
ms.author: sstein
ms.openlocfilehash: 15fdae19b150a5a06a32e91ec1947a0acfa5f900
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666327"
---
# <a name="delete-an-alert"></a><span data-ttu-id="65f82-102">Удаление предупреждения</span><span class="sxs-lookup"><span data-stu-id="65f82-102">Delete an Alert</span></span>
  <span data-ttu-id="65f82-103">В этом разделе описывается удаление [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] предупреждений агента в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="65f82-103">This topic describes how to delete [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="65f82-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="65f82-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="65f82-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="65f82-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="65f82-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="65f82-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="65f82-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="65f82-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="65f82-108">**Удаление предупреждения с помощью**</span><span class="sxs-lookup"><span data-stu-id="65f82-108">**To delete an alert, using:**</span></span>  
  
     [<span data-ttu-id="65f82-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="65f82-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="65f82-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="65f82-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="65f82-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="65f82-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="65f82-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="65f82-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="65f82-113">Удаление предупреждения приводит также к удалению всех связанных с ним уведомлений.</span><span class="sxs-lookup"><span data-stu-id="65f82-113">Removing an alert also removes any notifications associated with the alert.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="65f82-114">безопасность</span><span class="sxs-lookup"><span data-stu-id="65f82-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="65f82-115">Permissions</span><span class="sxs-lookup"><span data-stu-id="65f82-115">Permissions</span></span>  
 <span data-ttu-id="65f82-116">По умолчанию только члены предопределенной роли сервера **sysadmin** могут удалять предупреждения.</span><span class="sxs-lookup"><span data-stu-id="65f82-116">By default, only members of the **sysadmin** fixed server role can delete alerts.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="65f82-117">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="65f82-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-an-alert"></a><span data-ttu-id="65f82-118">Удаление предупреждения</span><span class="sxs-lookup"><span data-stu-id="65f82-118">To delete an alert</span></span>  
  
1.  <span data-ttu-id="65f82-119">В **обозревателе объектов** щелкните значок «плюс», чтобы развернуть сервер, содержащий предупреждение агента SQL Server, которое необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="65f82-119">In **Object Explorer,** click the plus sign to expand the server that contains the SQL Server Agent alert that you want to delete.</span></span>  
  
2.  <span data-ttu-id="65f82-120">Щелкните знак "плюс", чтобы развернуть **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="65f82-120">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="65f82-121">Чтобы развернуть папку **Предупреждения** , щелкните значок "плюс".</span><span class="sxs-lookup"><span data-stu-id="65f82-121">Click the plus sign to expand the **Alerts** folder.</span></span>  
  
4.  <span data-ttu-id="65f82-122">Щелкните правой кнопкой мыши предупреждение, которое необходимо удалить, и выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="65f82-122">Right-click the alert you want to delete and select **Delete**.</span></span>  
  
5.  <span data-ttu-id="65f82-123">В диалоговом окне **Удаление объекта** убедитесь, что выбрано верное предупреждение, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="65f82-123">In the **Delete Object** dialog box, confirm that the correct alert is selected and click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="65f82-124">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="65f82-124">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-an-alert"></a><span data-ttu-id="65f82-125">Удаление предупреждения</span><span class="sxs-lookup"><span data-stu-id="65f82-125">To delete an alert</span></span>  
  
1.  <span data-ttu-id="65f82-126">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65f82-126">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="65f82-127">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="65f82-127">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="65f82-128">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="65f82-128">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- deletes the SQL Server Agent alert called 'Test Alert.'  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_delete_alert  
       @name = N'Test Alert' ;  
    GO  
    ```  
  
 <span data-ttu-id="65f82-129">Дополнительные сведения см. в разделе s[sp_delete_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="65f82-129">For more information, see s[sp_delete_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-alert-transact-sql).</span></span>  
  
  

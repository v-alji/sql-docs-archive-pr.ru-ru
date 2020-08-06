---
title: Просмотр сведений о предупреждении | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, alerts
- viewing alerts
- alerts [SQL Server], viewing
- displaying alerts
- status information [SQL Server], alerts
ms.assetid: a0e3a8c4-e3c2-42a5-b2f8-aa06061d3fa6
author: stevestein
ms.author: sstein
ms.openlocfilehash: ee72512a507299e71f13fee689709a9403bb04e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658034"
---
# <a name="view-information-about-an-alert"></a><span data-ttu-id="09ea9-102">Просмотр сведений о предупреждении</span><span class="sxs-lookup"><span data-stu-id="09ea9-102">View Information About an Alert</span></span>
  <span data-ttu-id="09ea9-103">В этом разделе описывается Просмотр сведений об [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] оповещениях агента в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="09ea9-103">This topic describes how to view information about [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="09ea9-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="09ea9-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="09ea9-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="09ea9-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="09ea9-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="09ea9-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="09ea9-107">**Просмотр сведений о предупреждении**</span><span class="sxs-lookup"><span data-stu-id="09ea9-107">**To view information about an alert, using:**</span></span>  
  
     [<span data-ttu-id="09ea9-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="09ea9-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="09ea9-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="09ea9-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="09ea9-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="09ea9-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="09ea9-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="09ea9-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="09ea9-112">Permissions</span><span class="sxs-lookup"><span data-stu-id="09ea9-112">Permissions</span></span>  
 <span data-ttu-id="09ea9-113">По умолчанию только члены предопределенной роли сервера **sysadmin** могут просматривать сведения о предупреждении.</span><span class="sxs-lookup"><span data-stu-id="09ea9-113">By default, members of the **sysadmin** fixed server role can view information about an alert.</span></span> <span data-ttu-id="09ea9-114">Другим пользователям должна быть предоставлена предопределенная роль базы данных **SQLAgentOperatorRole** в базе данных **msdb** .</span><span class="sxs-lookup"><span data-stu-id="09ea9-114">Other users must be granted the **SQLAgentOperatorRole** fixed database role in the **msdb** database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="09ea9-115">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="09ea9-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-information-about-an-alert"></a><span data-ttu-id="09ea9-116">Просмотр сведений о предупреждении</span><span class="sxs-lookup"><span data-stu-id="09ea9-116">To view information about an alert</span></span>  
  
1.  <span data-ttu-id="09ea9-117">В **обозревателе объектов** щелкните знак «плюс», чтобы развернуть сервер, на котором необходимо просмотреть сведения о предупреждении.</span><span class="sxs-lookup"><span data-stu-id="09ea9-117">In **Object Explorer,** click the plus sign to expand the server where you want to view information about an alert.</span></span>  
  
2.  <span data-ttu-id="09ea9-118">Щелкните знак "плюс", чтобы развернуть **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="09ea9-118">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="09ea9-119">Чтобы развернуть папку **Предупреждения** , щелкните значок "плюс".</span><span class="sxs-lookup"><span data-stu-id="09ea9-119">Click the plus sign to expand the **Alerts** folder.</span></span>  
  
4.  <span data-ttu-id="09ea9-120">Щелкните правой кнопкой мыши предупреждение, в котором содержатся сведения для просмотра, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="09ea9-120">Right-click the alert that has the information you want to view and select **Properties**.</span></span>  
  
     <span data-ttu-id="09ea9-121">Для получения дополнительных сведений о допустимых параметрах, содержащихся в диалоговом окне _Свойства предупреждения_**имя_предупреждения** , см. следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="09ea9-121">For more information on the available options contained in the _alert_name_**alert properties** dialog box, see:</span></span>  
  
    -   [<span data-ttu-id="09ea9-122">Свойства предупреждения — новое оповещение &#40;общие&#41;страницы</span><span class="sxs-lookup"><span data-stu-id="09ea9-122">Alert Properties-New Alert &#40;General Page&#41;</span></span>](../../integration-services/general-page-of-integration-services-designers-options.md)  
  
    -   [<span data-ttu-id="09ea9-123">Свойства предупреждения — страница "создание ответа" &#40;"предупреждение"&#41;</span><span class="sxs-lookup"><span data-stu-id="09ea9-123">Alert Properties-New Alert &#40;Response Page&#41;</span></span>](alert-properties-new-alert-response-page.md)  
  
    -   [<span data-ttu-id="09ea9-124">Свойства предупреждения: страница "новые параметры &#40;предупреждений"&#41;</span><span class="sxs-lookup"><span data-stu-id="09ea9-124">Alert Properties: New Alert &#40;Options Page&#41;</span></span>](alert-properties-new-alert-options-page.md)  
  
    -   [<span data-ttu-id="09ea9-125">Свойства предупреждения (страница "Журнал")</span><span class="sxs-lookup"><span data-stu-id="09ea9-125">Alert Properties &#40;History Page&#41;</span></span>](alert-properties-history-page.md)  
  
5.  <span data-ttu-id="09ea9-126">После завершения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="09ea9-126">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="09ea9-127">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="09ea9-127">Using Transact-SQL</span></span>  
  
#### <a name="to-view-information-about-an-alert"></a><span data-ttu-id="09ea9-128">Просмотр сведений о предупреждении</span><span class="sxs-lookup"><span data-stu-id="09ea9-128">To view information about an alert</span></span>  
  
1.  <span data-ttu-id="09ea9-129">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09ea9-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="09ea9-130">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="09ea9-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="09ea9-131">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="09ea9-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- reports information about the Demo: Sev. 25 Errors alert  
    -- This example assumes that the 'Demo: Sev. 25 Errors' alert exists.  
    USE msdb ;  
    GO  
  
    EXEC sp_help_alert @alert_name = 'Demo: Sev. 25 Errors'  
    GO  
    ```  
  
 <span data-ttu-id="09ea9-132">Дополнительные сведения см. в разделе [sp_help_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="09ea9-132">For more information, see [sp_help_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-alert-transact-sql).</span></span>  
  
  

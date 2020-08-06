---
title: Укажите расположение целевого сервера&#39;s (SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, target servers
- target servers [SQL Server], location
ms.assetid: 511ff311-21f5-4f2f-839f-b4deee26ec98
author: stevestein
ms.author: sstein
ms.openlocfilehash: 938528ab78f0f457cde69d8fd4d5432cc14a79b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666324"
---
# <a name="specify-a-target-server39s-location-sql-server-management-studio"></a><span data-ttu-id="0b5c4-102">Определение расположения целевого сервера (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="0b5c4-102">Specify a Target Server&#39;s Location (SQL Server Management Studio)</span></span>
  <span data-ttu-id="0b5c4-103">В этом разделе описано, как задать расположение целевого сервера в конфигурации администрирования нескольких серверов в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0b5c4-103">This topic describes how to specify the location of a target server in a multiserver administration configuration in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="0b5c4-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="0b5c4-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0b5c4-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="0b5c4-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0b5c4-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="0b5c4-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="0b5c4-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="0b5c4-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="0b5c4-108">**Задание расположения целевого сервера с помощью:**</span><span class="sxs-lookup"><span data-stu-id="0b5c4-108">**To specify a target server's location, using:**</span></span>  
  
     [<span data-ttu-id="0b5c4-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0b5c4-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="0b5c4-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0b5c4-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0b5c4-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="0b5c4-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="0b5c4-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="0b5c4-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="0b5c4-113">Выполнение этого действие ведет к изменению реестра.</span><span class="sxs-lookup"><span data-stu-id="0b5c4-113">Performing this action edits the registry.</span></span> <span data-ttu-id="0b5c4-114">Редактировать реестр вручную не рекомендуется, так как неуместные или неверные изменения могут серьезно нарушить конфигурацию системы.</span><span class="sxs-lookup"><span data-stu-id="0b5c4-114">Manual editing of the registry is not recommended because inappropriate or incorrect changes can cause serious configuration problems for your system.</span></span> <span data-ttu-id="0b5c4-115">Пользоваться программой редактирования реестра должны только опытные пользователи.</span><span class="sxs-lookup"><span data-stu-id="0b5c4-115">Therefore, only experienced users should use the Registry Editor program to edit the registry.</span></span> <span data-ttu-id="0b5c4-116">Дополнительные сведения см. в документации Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="0b5c4-116">For more information, see the Microsoft Windows documentation.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0b5c4-117">безопасность</span><span class="sxs-lookup"><span data-stu-id="0b5c4-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0b5c4-118">Permissions</span><span class="sxs-lookup"><span data-stu-id="0b5c4-118">Permissions</span></span>  
 <span data-ttu-id="0b5c4-119">Необходимо членство в предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="0b5c4-119">Requires membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0b5c4-120">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0b5c4-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-specify-a-target-servers-location"></a><span data-ttu-id="0b5c4-121">Задание расположения целевого сервера</span><span class="sxs-lookup"><span data-stu-id="0b5c4-121">To specify a target server's location</span></span>  
  
1.  <span data-ttu-id="0b5c4-122">В **обозревателе объектов**щелкните значок «плюс», чтобы развернуть главный сервер, на котором необходимо задать расположение целевого сервера.</span><span class="sxs-lookup"><span data-stu-id="0b5c4-122">In **Object Explorer**, click the plus sign to expand the master server on which you want to specify a target server's location.</span></span>  
  
2.  <span data-ttu-id="0b5c4-123">Щелкните правой кнопкой мыши элемент **Агент SQL Server**, укажите пункт **Администрирование нескольких серверов**, а затем выберите пункт **Управление целевыми серверами**.</span><span class="sxs-lookup"><span data-stu-id="0b5c4-123">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and select **Manage Target Servers**.</span></span>  
  
3.  <span data-ttu-id="0b5c4-124">Щелкните правой кнопкой мыши целевой сервер и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="0b5c4-124">Right-click a target server and select **Properties**.</span></span>  
  
4.  <span data-ttu-id="0b5c4-125">В окне **Расположение** введите расположение сервера, затем нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0b5c4-125">In the **Location** box, enter a location for the server, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="0b5c4-126">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0b5c4-126">Using Transact-SQL</span></span>  
  
#### <a name="to-specify-a-target-servers-location"></a><span data-ttu-id="0b5c4-127">Задание расположения целевого сервера</span><span class="sxs-lookup"><span data-stu-id="0b5c4-127">To specify a target server's location</span></span>  
  
1.  <span data-ttu-id="0b5c4-128">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0b5c4-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="0b5c4-129">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="0b5c4-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="0b5c4-130">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="0b5c4-130">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb ;  
    GO  
    -- enlists the current server into the AdventureWorks1 master server.   
    -- The location for the current server is Building 21, Room 309, Rack 5  
    EXEC dbo.sp_msx_enlist N'AdventureWorks2012',   
        N'Building 21, Room 309, Rack 5' ;  
    GO  
    ```  
  
 <span data-ttu-id="0b5c4-131">Дополнительные сведения см. в разделе [sp_msx_enlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0b5c4-131">For more information, see [sp_msx_enlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql).</span></span>  
  
  

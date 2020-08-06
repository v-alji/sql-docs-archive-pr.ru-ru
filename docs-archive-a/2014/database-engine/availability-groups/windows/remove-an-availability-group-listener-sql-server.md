---
title: Удаление прослушивателя группы доступности (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.removeaglistener.default.f1
helpviewer_keywords:
- Availability Groups [SQL Server], listeners
ms.assetid: fd9bba9a-d29f-4c23-8ecd-aaa049ed5f1b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 057b9c137cb4d8bbbdd03be61df600f7e59b264c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657318"
---
# <a name="remove-an-availability-group-listener-sql-server"></a><span data-ttu-id="1a6e7-102">Удаление прослушивателя группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1a6e7-102">Remove an Availability Group Listener (SQL Server)</span></span>
  <span data-ttu-id="1a6e7-103">В этом разделе описывается удаление прослушивателя группы доступности из группы доступности AlwaysOn с помощью среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]или PowerShell в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1a6e7-103">This topic describes how to remove an availability group listener from an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="1a6e7-104">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="1a6e7-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1a6e7-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="1a6e7-105">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="1a6e7-106">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="1a6e7-106">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="1a6e7-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="1a6e7-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1a6e7-108">**Удаление прослушивателя с помощью**</span><span class="sxs-lookup"><span data-stu-id="1a6e7-108">**To remove a listener, using:**</span></span>  
  
     [<span data-ttu-id="1a6e7-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1a6e7-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1a6e7-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1a6e7-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="1a6e7-111">PowerShell</span><span class="sxs-lookup"><span data-stu-id="1a6e7-111">PowerShell</span></span>](#PowerShellProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1a6e7-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="1a6e7-112">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="1a6e7-113">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="1a6e7-113">Prerequisites</span></span>  
  
-   <span data-ttu-id="1a6e7-114">Необходимо подключиться к экземпляру сервера, на котором размещена первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="1a6e7-114">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="1a6e7-115">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="1a6e7-115">Recommendations</span></span>  
 <span data-ttu-id="1a6e7-116">Перед удалением прослушивателя группы доступности рекомендуется убедиться, что он не используется никакими приложениями.</span><span class="sxs-lookup"><span data-stu-id="1a6e7-116">Before you delete an availability group listener, we recommend that you ensure that no applications are using it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1a6e7-117">безопасность</span><span class="sxs-lookup"><span data-stu-id="1a6e7-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1a6e7-118">Permissions</span><span class="sxs-lookup"><span data-stu-id="1a6e7-118">Permissions</span></span>  
 <span data-ttu-id="1a6e7-119">Необходимо разрешение ALTER AVAILABILITY GROUP для группы доступности, разрешение CONTROL AVAILABILITY GROUP, разрешение ALTER ANY AVAILABILITY GROUP или разрешение CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="1a6e7-119">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1a6e7-120">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1a6e7-120">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="1a6e7-121">**Удаление прослушивателя группы доступности**</span><span class="sxs-lookup"><span data-stu-id="1a6e7-121">**To remove an availability group listener**</span></span>  
  
1.  <span data-ttu-id="1a6e7-122">В обозревателе объектов подключитесь к экземпляру сервера, на котором размещена первичная реплика, и щелкните имя сервера, чтобы развернуть его дерево.</span><span class="sxs-lookup"><span data-stu-id="1a6e7-122">In Object Explorer, connect to the server instance that hosts the primary replica, and click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="1a6e7-123">Разверните узел **Высокий уровень доступности AlwaysOn** и узел **Группы доступности** .</span><span class="sxs-lookup"><span data-stu-id="1a6e7-123">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="1a6e7-124">Разверните узел группы доступности и разверните узел **Прослушиватели группы доступности** .</span><span class="sxs-lookup"><span data-stu-id="1a6e7-124">Expand the node of the availability group, and expand the **Availability Groups Listeners** node.</span></span>  
  
4.  <span data-ttu-id="1a6e7-125">Правой кнопкой щелкните прослушиватель, который необходимо удалить, и выберите команду **Удалить** .</span><span class="sxs-lookup"><span data-stu-id="1a6e7-125">Right-click the listener to be removed, and select the **Delete** command.</span></span>  
  
5.  <span data-ttu-id="1a6e7-126">Откроется диалоговое окно **Удаление прослушивателя из группы доступности** .</span><span class="sxs-lookup"><span data-stu-id="1a6e7-126">This opens the **Remove Listener from Availability Group** dialog box.</span></span> <span data-ttu-id="1a6e7-127">Дополнительные сведения см. в подразделе [Удаление прослушивателя из группы доступности](#AgListenerPropertiesDialog)далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="1a6e7-127">For more information, see [Remove Listener from Availability Group](#AgListenerPropertiesDialog), later in this topic.</span></span>  
  
###  <a name="remove-listener-from-availability-group-dialog-box"></a><a name="AgListenerPropertiesDialog"></a><span data-ttu-id="1a6e7-128">Удалить прослушиватель из группы доступности (диалоговое окно)</span><span class="sxs-lookup"><span data-stu-id="1a6e7-128">Remove Listener from Availability Group (Dialog Box)</span></span>  
 <span data-ttu-id="1a6e7-129">**имя**;</span><span class="sxs-lookup"><span data-stu-id="1a6e7-129">**Name**</span></span>  
 <span data-ttu-id="1a6e7-130">Имя удаляемого прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="1a6e7-130">The name of the listener to be removed.</span></span>  
  
 <span data-ttu-id="1a6e7-131">**Результат**</span><span class="sxs-lookup"><span data-stu-id="1a6e7-131">**Result**</span></span>  
 <span data-ttu-id="1a6e7-132">Отображает ссылку **Успешно** или **Ошибка**, которую можно щелкнуть для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="1a6e7-132">Displays a link, either **Success** or **Error**, which you can click for more information.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1a6e7-133">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1a6e7-133">Using Transact-SQL</span></span>  
 <span data-ttu-id="1a6e7-134">**Удаление прослушивателя группы доступности**</span><span class="sxs-lookup"><span data-stu-id="1a6e7-134">**To remove an availability group listener**</span></span>  
  
1.  <span data-ttu-id="1a6e7-135">Подключитесь к экземпляру сервера, на котором находится первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="1a6e7-135">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="1a6e7-136">Инструкция [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) используется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1a6e7-136">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="1a6e7-137">ALTER AVAILABILITY GROUP *group_name* удалить прослушиватель **" *`dns_name`* "**</span><span class="sxs-lookup"><span data-stu-id="1a6e7-137">ALTER AVAILABILITY GROUP *group_name* REMOVE LISTENER **'*`dns_name`*'**</span></span>  
  
     <span data-ttu-id="1a6e7-138">где *group_name* — имя группы доступности, а *dns_name* — DNS-имя прослушивателя группы доступности.</span><span class="sxs-lookup"><span data-stu-id="1a6e7-138">where *group_name* is the name of the availability group and *dns_name* is the DNS name of the availability group listener.</span></span>  
  
     <span data-ttu-id="1a6e7-139">В следующем примере выполняется удаление прослушивателя группы доступности `AccountsAG` .</span><span class="sxs-lookup"><span data-stu-id="1a6e7-139">The following example deletes the listener of the `AccountsAG` availability group.</span></span> <span data-ttu-id="1a6e7-140">Имя DNS — AccountsAG_Listener.</span><span class="sxs-lookup"><span data-stu-id="1a6e7-140">The DNS name is AccountsAG_Listener.</span></span>  
  
    ```sql
    ALTER AVAILABILITY GROUP AccountsAG REMOVE LISTENER 'AccountsAG_Listener';  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="1a6e7-141">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="1a6e7-141">Using PowerShell</span></span>  
 <span data-ttu-id="1a6e7-142">**Удаление прослушивателя группы доступности**</span><span class="sxs-lookup"><span data-stu-id="1a6e7-142">**To remove an availability group listener**</span></span>  
  
1.  <span data-ttu-id="1a6e7-143">Установите значение по умолчанию (`cd`) равным серверу экземпляра, на котором размещена первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="1a6e7-143">Set default (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="1a6e7-144">Для удаления прослушивателя используйте встроенный командлет `Remove-Item`.</span><span class="sxs-lookup"><span data-stu-id="1a6e7-144">Use the built in `Remove-Item` cmdlet to remove a listener.</span></span> <span data-ttu-id="1a6e7-145">Например, следующая команда удаляет прослушиватель с именем `MyListener` из группы доступности с именем `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="1a6e7-145">For example, the following command removes a listener named `MyListener` from an availability group named `MyAg`.</span></span>  
  
    ```powershell
    Remove-Item SQLSERVER:\Sql\PrimaryServer\InstanceName\AvailabilityGroups\MyAg\AGListeners\MyListener  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="1a6e7-146">Чтобы просмотреть синтаксис командлета, воспользуйтесь командлетом `Get-Help` в среде [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1a6e7-146">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="1a6e7-147">Дополнительные сведения см. в разделе [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="1a6e7-147">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="1a6e7-148">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="1a6e7-148">Related Tasks</span></span>  
  
-   [<span data-ttu-id="1a6e7-149">Создание или настройка прослушивателя группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1a6e7-149">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="1a6e7-150">Просмотр свойств прослушивателя группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1a6e7-150">View Availability Group Listener Properties &#40;SQL Server&#41;</span></span>](view-availability-group-listener-properties-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="1a6e7-151">См. также:</span><span class="sxs-lookup"><span data-stu-id="1a6e7-151">See Also</span></span>  
 <span data-ttu-id="1a6e7-152">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1a6e7-152">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="1a6e7-153">Прослушиватели групп доступности, возможность подключения клиентов и отработка отказа приложений (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1a6e7-153">Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;</span></span>](../../listeners-client-connectivity-application-failover.md)  

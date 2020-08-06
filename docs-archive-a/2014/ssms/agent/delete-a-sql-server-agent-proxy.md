---
title: Удаление учетной записи-посредника агента SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- deleting SQL Server Agent proxies
- proxies [SQL Server Agent], deleting
- removing SQL Server Agent proxies
ms.assetid: 9248841d-7294-47d4-94f3-b34a0521fabc
author: stevestein
ms.author: sstein
ms.openlocfilehash: a672c6392e2ffed3ca2a7ed655b806d9d093b10c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666329"
---
# <a name="delete-a-sql-server-agent-proxy"></a><span data-ttu-id="0fe78-102">Delete a SQL Server Agent Proxy</span><span class="sxs-lookup"><span data-stu-id="0fe78-102">Delete a SQL Server Agent Proxy</span></span>
  <span data-ttu-id="0fe78-103">В этом разделе описывается, как удалить учетную запись-посредник агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0fe78-103">This topic describes how to delete a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy account in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="0fe78-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="0fe78-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0fe78-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="0fe78-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0fe78-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="0fe78-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="0fe78-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="0fe78-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="0fe78-108">**Удаление учетной записи-посредника агента SQL Server с помощью:**</span><span class="sxs-lookup"><span data-stu-id="0fe78-108">**To delete a SQL Server Agent proxy account, using:**</span></span>  
  
     [<span data-ttu-id="0fe78-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0fe78-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="0fe78-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0fe78-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0fe78-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="0fe78-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="0fe78-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="0fe78-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="0fe78-113">При удалении учетной записи-посредника агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] убедитесь в том, что она не ссылается ни на какие активные шаги задания.</span><span class="sxs-lookup"><span data-stu-id="0fe78-113">When you delete a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy account, make sure the proxy does not reference any active job steps.</span></span> <span data-ttu-id="0fe78-114">Чтобы узнать, на какие шаги задания ссылается учетная запись-посредник, щелкните ее правой кнопкой мыши, выберите **Свойства**и в диалоговом окне _Свойства учетной записи-посредника_**имя_учетной_записи-посредника** перейдите на страницу **Ссылки** .</span><span class="sxs-lookup"><span data-stu-id="0fe78-114">To check for any job steps that reference the proxy, right-click the proxy, select **Properties**, and then, in the _proxy_name_**Proxy Account Properties** dialog box, select the **References** page.</span></span> <span data-ttu-id="0fe78-115">При удалении учетной записи-посредника существует возможность переназначить все шаги задания, которые ее используют, в диалоговом окне **Удаление объекта** .</span><span class="sxs-lookup"><span data-stu-id="0fe78-115">If you delete a proxy, you are given the option to reassign all job steps that use that proxy in the **Delete Object** dialog box.</span></span>  
  
-   <span data-ttu-id="0fe78-116">Учетные записи-посредники агента[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] используют учетные данные для хранения сведений об учетных записях пользователей Windows.</span><span class="sxs-lookup"><span data-stu-id="0fe78-116">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxies use credentials to store information about Windows user accounts.</span></span> <span data-ttu-id="0fe78-117">Указанный в учетных данных пользователь должен иметь разрешение «Вход в систему в качестве пакетного задания» на компьютере, где запущен [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0fe78-117">The user specified in the credential must have "Log on as a batch job" permission on the computer on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0fe78-118">проверяет действительность доступа к подсистеме учетной записи-посредника и предоставляет ей доступ при каждом выполнении шага задания.</span><span class="sxs-lookup"><span data-stu-id="0fe78-118">Agent checks subsystem access for a proxy and gives access to the proxy each time the job step runs.</span></span> <span data-ttu-id="0fe78-119">Если учетная запись-посредник больше не имеет доступа к подсистеме, шаг задания завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="0fe78-119">If the proxy no longer has access to the subsystem, the job step fails.</span></span> <span data-ttu-id="0fe78-120">В противном случае агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] олицетворяет пользователя, указанного в учетной записи-посреднике, и запускает шаг задания.</span><span class="sxs-lookup"><span data-stu-id="0fe78-120">Otherwise, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent impersonates the user that is specified in the proxy and runs the job step.</span></span>  
  
-   <span data-ttu-id="0fe78-121">Если имени входа пользователя предоставлен доступ к учетной записи-посреднику или пользователь принадлежит к любой роли с доступом к учетной записи-посреднику, то он может использовать учетную запись-посредник в шаге задания.</span><span class="sxs-lookup"><span data-stu-id="0fe78-121">If the login for the user has access to the proxy, or the user belongs to any role with access to the proxy, the user can use the proxy in a job step.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0fe78-122">безопасность</span><span class="sxs-lookup"><span data-stu-id="0fe78-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0fe78-123">Permissions</span><span class="sxs-lookup"><span data-stu-id="0fe78-123">Permissions</span></span>  
 <span data-ttu-id="0fe78-124">Создавать, изменять или удалять учетные записи-посредники могут только члены предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="0fe78-124">Only members of the **sysadmin** fixed server role can create, modify, or delete proxy accounts.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0fe78-125">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0fe78-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-sql-server-agent-proxy-account"></a><span data-ttu-id="0fe78-126">Удаление учетной записи-посредника агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="0fe78-126">To delete a SQL Server Agent proxy account</span></span>  
  
1.  <span data-ttu-id="0fe78-127">В **обозревателе объектов**щелкните знак «плюс», чтобы развернуть сервер, содержащий учетную запись-посредник, которую необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="0fe78-127">In **Object Explorer**, click the plus sign to expand a server that contains the proxy account that you want to delete.</span></span>  
  
2.  <span data-ttu-id="0fe78-128">Щелкните знак "плюс", чтобы развернуть **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="0fe78-128">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="0fe78-129">Щелкните знак «плюс», чтобы развернуть папку **Учетные записи-посредники** .</span><span class="sxs-lookup"><span data-stu-id="0fe78-129">Click the plus sign to expand the **Proxies** folder.</span></span>  
  
4.  <span data-ttu-id="0fe78-130">Чтобы развернуть подсистему, содержащую учетную запись-посредник (например, **Скрипт ActiveX**), которую необходимо удалить, щелкните знак "плюс" (+).</span><span class="sxs-lookup"><span data-stu-id="0fe78-130">Click the plus sign to expand the subsystem that contains the proxy account you want to delete (for example, **ActiveX Script)**.</span></span>  
  
5.  <span data-ttu-id="0fe78-131">Щелкните правой кнопкой мыши удаляемую учетную запись-посредник и выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="0fe78-131">Right-click the proxy account that you want to delete and select **Delete**.</span></span>  
  
6.  <span data-ttu-id="0fe78-132">В диалоговом окне **Удаление объекта** убедитесь, что выбрана соответствующая учетная запись-посредник.</span><span class="sxs-lookup"><span data-stu-id="0fe78-132">In the **Delete Object** dialog box, confirm that the correct proxy account is selected.</span></span> <span data-ttu-id="0fe78-133">Установите флажок **Переназначить** для того, чтобы переназначить шаги задания, которые ссылаются на эту учетную запись-посредник, на другую учетную запись.</span><span class="sxs-lookup"><span data-stu-id="0fe78-133">Check the **Reassign to** check box to reassign the job steps that reference this proxy account to another account.</span></span>  
  
7.  <span data-ttu-id="0fe78-134">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0fe78-134">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="0fe78-135">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0fe78-135">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-sql-server-agent-proxy-account"></a><span data-ttu-id="0fe78-136">Удаление учетной записи-посредника агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="0fe78-136">To delete a SQL Server Agent proxy account</span></span>  
  
1.  <span data-ttu-id="0fe78-137">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0fe78-137">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="0fe78-138">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="0fe78-138">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="0fe78-139">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="0fe78-139">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- deletes the proxy "Catalog application proxy"  
    USE msdb ;  
    GO  
    EXEC dbo.sp_delete_proxy  
        @proxy_name = N'Catalog application proxy' ;  
    GO  
    ```  
  
 <span data-ttu-id="0fe78-140">Дополнительные сведения см. в разделе [sp_delete_proxy &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-proxy-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0fe78-140">For more information, see [sp_delete_proxy &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-proxy-transact-sql).</span></span>  
  
  

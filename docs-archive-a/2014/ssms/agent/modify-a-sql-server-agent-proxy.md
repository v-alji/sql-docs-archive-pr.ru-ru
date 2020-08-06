---
title: Изменение учетной записи-посредника агента SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- proxies [SQL Server Agent], modifying
- modifying SQL Server Agent proxy
ms.assetid: 6e1dfbaa-8089-4813-940c-d5a2e13d8552
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2f86793a8ddcc6fe8f981d6b367d2178c5a794ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658054"
---
# <a name="modify-a-sql-server-agent-proxy"></a><span data-ttu-id="e80ad-102">Modify a SQL Server Agent Proxy</span><span class="sxs-lookup"><span data-stu-id="e80ad-102">Modify a SQL Server Agent Proxy</span></span>
  <span data-ttu-id="e80ad-103">В этом разделе описывается изменение [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] учетной записи-посредника агента в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e80ad-103">This topic describes how to modify a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="e80ad-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="e80ad-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e80ad-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="e80ad-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e80ad-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="e80ad-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="e80ad-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="e80ad-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e80ad-108">**Изменение учетной записи-посредника агента SQL Server с использованием следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="e80ad-108">**To modify a SQL Server Agent proxy, using:**</span></span>  
  
     [<span data-ttu-id="e80ad-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e80ad-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e80ad-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e80ad-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e80ad-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="e80ad-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="e80ad-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="e80ad-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="e80ad-113">Учетные записи-посредники агента[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] используют учетные данные для хранения сведений об учетных записях пользователей Windows.</span><span class="sxs-lookup"><span data-stu-id="e80ad-113">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxies use credentials to store information about Windows user accounts.</span></span> <span data-ttu-id="e80ad-114">Указанный в учетных данных пользователь должен иметь разрешение «Вход в систему в качестве пакетного задания» на компьютере, где запущен [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e80ad-114">The user specified in the credential must have "Log on as a batch job" permission on the computer on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e80ad-115">проверяет действительность доступа к подсистеме учетной записи-посредника и предоставляет ей доступ при каждом выполнении шага задания.</span><span class="sxs-lookup"><span data-stu-id="e80ad-115">Agent checks subsystem access for a proxy and gives access to the proxy each time the job step runs.</span></span> <span data-ttu-id="e80ad-116">Если учетная запись-посредник больше не имеет доступа к подсистеме, шаг задания завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="e80ad-116">If the proxy no longer has access to the subsystem, the job step fails.</span></span> <span data-ttu-id="e80ad-117">В противном случае агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] олицетворяет пользователя, указанного в учетной записи-посреднике, и запускает шаг задания.</span><span class="sxs-lookup"><span data-stu-id="e80ad-117">Otherwise, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent impersonates the user that is specified in the proxy and runs the job step.</span></span>  
  
-   <span data-ttu-id="e80ad-118">Если имени входа пользователя предоставлен доступ к учетной записи-посреднику или пользователь принадлежит к любой роли с доступом к учетной записи-посреднику, то он может использовать учетную запись-посредник в шаге задания.</span><span class="sxs-lookup"><span data-stu-id="e80ad-118">If the login for the user has access to the proxy, or the user belongs to any role with access to the proxy, the user can use the proxy in a job step.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e80ad-119">безопасность</span><span class="sxs-lookup"><span data-stu-id="e80ad-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e80ad-120">Permissions</span><span class="sxs-lookup"><span data-stu-id="e80ad-120">Permissions</span></span>  
 <span data-ttu-id="e80ad-121">Создавать, изменять или удалять учетные записи-посредники могут только члены предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="e80ad-121">Only members of the **sysadmin** fixed server role can create, modify, or delete proxy accounts.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e80ad-122">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e80ad-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-ssnoversion-agent-proxy"></a><span data-ttu-id="e80ad-123">Изменение учетной записи-посредника агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e80ad-123">To modify a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy</span></span>  
  
1.  <span data-ttu-id="e80ad-124">В **обозревателе объектов**щелкните знак «плюс», чтобы развернуть сервер, содержащий учетную запись-посредник агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="e80ad-124">In **Object Explorer**, click the plus sign to expand the server that contains the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy account that you want to modify.</span></span>  
  
2.  <span data-ttu-id="e80ad-125">Щелкните знак "плюс", чтобы развернуть **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="e80ad-125">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="e80ad-126">Щелкните знак «плюс», чтобы развернуть папку **Учетные записи-посредники** .</span><span class="sxs-lookup"><span data-stu-id="e80ad-126">Click the plus sign to expand the **Proxies** folder.</span></span>  
  
4.  <span data-ttu-id="e80ad-127">Щелкните знак "плюс", чтобы развернуть узел подсистемы, содержащий учетную запись-посредник (например, **Скрипт ActiveX**).</span><span class="sxs-lookup"><span data-stu-id="e80ad-127">Click the plus sign to expand the subsystem node for the proxy (for example, **ActiveX Script**).</span></span>  
  
5.  <span data-ttu-id="e80ad-128">Щелкните правой кнопкой мыши учетную запись-посредник, которую требуется изменить, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="e80ad-128">Right-click the proxy account you want to modify and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="e80ad-129">В диалоговом окне**Свойства учетной записи-посредника** _proxy_name_внесите необходимые изменения в учетную запись-посредник.</span><span class="sxs-lookup"><span data-stu-id="e80ad-129">In the _proxy_name_**Proxy Account Properties** dialog box, make changes to the proxy account as necessary.</span></span> <span data-ttu-id="e80ad-130">Дополнительные сведения о параметрах данного диалогового окна см. в разделе [Создание учетной записи-посредника агента SQL Server](create-a-sql-server-agent-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="e80ad-130">For more information on the options in this dialog box, see [Create a SQL Server Agent Proxy](create-a-sql-server-agent-proxy.md).</span></span>  
  
7.  <span data-ttu-id="e80ad-131">После завершения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e80ad-131">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e80ad-132">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e80ad-132">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-a-ssnoversion-agent-proxy"></a><span data-ttu-id="e80ad-133">Изменение учетной записи-посредника агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e80ad-133">To modify a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy</span></span>  
  
1.  <span data-ttu-id="e80ad-134">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e80ad-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e80ad-135">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="e80ad-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e80ad-136">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="e80ad-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Disables the proxy named 'Catalog application proxy'.  
    USE msdb ;  
    GO  
    EXEC dbo.sp_update_proxy  
        @proxy_name = 'Catalog application proxy',  
        @enabled = 0;  
    GO  
    ```  
  
 <span data-ttu-id="e80ad-137">Дополнительные сведения см. в разделе [sp_update_proxy &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-proxy-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e80ad-137">For more information, see [sp_update_proxy &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-proxy-transact-sql).</span></span>  
  
  

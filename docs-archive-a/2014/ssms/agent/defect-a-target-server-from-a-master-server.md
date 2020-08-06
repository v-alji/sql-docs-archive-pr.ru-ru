---
title: Отключение целевого сервера от главного | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, target servers
- target servers [SQL Server], defecting
- SQL Server Agent jobs, master servers
- master servers [SQL Server], defecting target servers
- defecting target servers
ms.assetid: a6da262b-7b38-4ce4-bfd6-6a557c6e8a84
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2b17703fa87f5c0d3e7146a1660ac1ca7c7c1d81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731366"
---
# <a name="defect-a-target-server-from-a-master-server"></a><span data-ttu-id="1b5d1-102">Отключение целевого сервера от главного сервера</span><span class="sxs-lookup"><span data-stu-id="1b5d1-102">Defect a Target Server from a Master Server</span></span>
  <span data-ttu-id="1b5d1-103">В этом разделе описывается исключение целевого сервера из главного в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] или управляющих объектов SQL Server (SMO).</span><span class="sxs-lookup"><span data-stu-id="1b5d1-103">This topic describes how to defect a target server from a master server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="1b5d1-104">Запустите эту процедуру на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="1b5d1-104">Run this procedure from the target server.</span></span>  
  
 <span data-ttu-id="1b5d1-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="1b5d1-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1b5d1-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="1b5d1-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1b5d1-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="1b5d1-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1b5d1-108">**Для исключения целевого сервера используется:**</span><span class="sxs-lookup"><span data-stu-id="1b5d1-108">**To defect a target server, using:**</span></span>  
  
     [<span data-ttu-id="1b5d1-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1b5d1-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1b5d1-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1b5d1-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="1b5d1-111">ОБЪЕКТАХ</span><span class="sxs-lookup"><span data-stu-id="1b5d1-111">SMO</span></span>](#PowerShellProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1b5d1-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="1b5d1-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1b5d1-113">безопасность</span><span class="sxs-lookup"><span data-stu-id="1b5d1-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1b5d1-114">Permissions</span><span class="sxs-lookup"><span data-stu-id="1b5d1-114">Permissions</span></span>  
 <span data-ttu-id="1b5d1-115">Для выполнения этой хранимой процедуры пользователь должен быть членом предопределенной роли сервера `sysadmin`.</span><span class="sxs-lookup"><span data-stu-id="1b5d1-115">To execute this stored procedure, a user must be a member of the `sysadmin` fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1b5d1-116">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1b5d1-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-defect-a-target-server-from-a-master-server"></a><span data-ttu-id="1b5d1-117">Отключение целевого сервера от главного</span><span class="sxs-lookup"><span data-stu-id="1b5d1-117">To defect a target server from a master server</span></span>  
  
1.  <span data-ttu-id="1b5d1-118">В **обозревателе объектов**разверните сервер, настроенный как целевой сервер.</span><span class="sxs-lookup"><span data-stu-id="1b5d1-118">In **Object Explorer**, expand a server that is configured as a target server.</span></span>  
  
2.  <span data-ttu-id="1b5d1-119">Щелкните правой кнопкой мыши **Агент SQL Server**, выберите **Администрирование нескольких серверов**и нажмите **Отключить**.</span><span class="sxs-lookup"><span data-stu-id="1b5d1-119">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Defect**.</span></span>  
  
3.  <span data-ttu-id="1b5d1-120">Щелкните **Да** , подтверждая, что этот целевой сервер необходимо отключить от главного сервера.</span><span class="sxs-lookup"><span data-stu-id="1b5d1-120">Click **Yes** to confirm that you want to defect this target server from a master server.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1b5d1-121">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1b5d1-121">Using Transact-SQL</span></span>  
  
#### <a name="to-defect-a-target-server-from-a-master-server"></a><span data-ttu-id="1b5d1-122">Отключение целевого сервера от главного</span><span class="sxs-lookup"><span data-stu-id="1b5d1-122">To defect a target server from a master server</span></span>  
  
1.  <span data-ttu-id="1b5d1-123">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1b5d1-123">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1b5d1-124">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="1b5d1-124">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1b5d1-125">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="1b5d1-125">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
```sql
sp_msx_defect ;  
```  
  
 <span data-ttu-id="1b5d1-126">Дополнительные сведения см. в разделе [sp_msx_defect &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-defect-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1b5d1-126">For more information, see [sp_msx_defect &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-defect-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects-smo"></a><a name="PowerShellProcedure"></a><span data-ttu-id="1b5d1-127">Использование управляющие объекты SQL Server (SMO)</span><span class="sxs-lookup"><span data-stu-id="1b5d1-127">Using SQL Server Management Objects (SMO)</span></span>  
 <span data-ttu-id="1b5d1-128">Используйте `MsxDefect Method`.</span><span class="sxs-lookup"><span data-stu-id="1b5d1-128">Use the `MsxDefect Method`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b5d1-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="1b5d1-129">See Also</span></span>  
 <span data-ttu-id="1b5d1-130">[Создание многосерверной среды](create-a-multiserver-environment.md) </span><span class="sxs-lookup"><span data-stu-id="1b5d1-130">[Create a Multiserver Environment](create-a-multiserver-environment.md) </span></span>  
 <span data-ttu-id="1b5d1-131">[Автоматизация администрирования в масштабах предприятия](automated-administration-across-an-enterprise.md) </span><span class="sxs-lookup"><span data-stu-id="1b5d1-131">[Automated Administration Across an Enterprise](automated-administration-across-an-enterprise.md) </span></span>  
 [<span data-ttu-id="1b5d1-132">Отключение нескольких целевых серверов от главного</span><span class="sxs-lookup"><span data-stu-id="1b5d1-132">Defect Multiple Target Servers from a Master Server</span></span>](defect-multiple-target-servers-from-a-master-server.md)  

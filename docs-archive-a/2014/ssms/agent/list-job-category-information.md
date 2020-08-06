---
title: Просмотр сведений о категории задания | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 0fc668d4-6244-4fef-b90e-62d2c776cd7c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 924e2b064980b2ea7068230610414262995da1a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735849"
---
# <a name="list-job-category-information"></a><span data-ttu-id="b57da-102">Просмотр сведений о категории задания</span><span class="sxs-lookup"><span data-stu-id="b57da-102">List Job Category Information</span></span>
  <span data-ttu-id="b57da-103">Сведения о том, как составить список сведений о категории заданий в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[tsql](../../includes/tsql-md.md)] или управляющие объекты SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b57da-103">How to list job category information in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)] or SQL Server Management Objects.</span></span>  

  
##  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b57da-104">безопасность</span><span class="sxs-lookup"><span data-stu-id="b57da-104">Security</span></span>  
 <span data-ttu-id="b57da-105">Дополнительные сведения см. в разделе [Обеспечение безопасности агента SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="b57da-105">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  

  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="b57da-106">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b57da-106">Using Transact-SQL</span></span>  
  
#### <a name="to-list-job-category-information"></a><span data-ttu-id="b57da-107">Просмотр сведений о категории задания</span><span class="sxs-lookup"><span data-stu-id="b57da-107">To list job category information</span></span>  
  
1.  <span data-ttu-id="b57da-108">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b57da-108">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b57da-109">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="b57da-109">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b57da-110">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="b57da-110">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- returns information about jobs that are administered locally  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_help_category  
        @type = N'LOCAL' ;  
    GO  
    ```  
  
 <span data-ttu-id="b57da-111">Дополнительные сведения см. в разделе [sp_help_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-category-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b57da-111">For more information, see [sp_help_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-category-transact-sql).</span></span>  
  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="b57da-112">Использование управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="b57da-112">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="b57da-113">**Просмотр сведений о категории задания**</span><span class="sxs-lookup"><span data-stu-id="b57da-113">**To list job category information**</span></span>  
  
 <span data-ttu-id="b57da-114">Воспользуйтесь классом `JobCategory` на любом языке программирования, таком как Visual Basic, Visual C# или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b57da-114">Use the `JobCategory` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell..</span></span> <span data-ttu-id="b57da-115">Дополнительные сведения см. в разделе [управляющие объекты SQL Server &#40;SMO&#41; Guide](../../relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide.md).</span><span class="sxs-lookup"><span data-stu-id="b57da-115">For more information, see [SQL Server Management Objects &#40;SMO&#41; Programming Guide](../../relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide.md).</span></span>  

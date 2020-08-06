---
title: Изменение доступности оператора | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- canceling operators
- reactivating operators
- removing operators
- deleting operators
- available operators [SQL Server]
- dropping operators
- jobs [SQL Server Agent], operators
- notifications [SQL Server], job status
- disabling operators
- operators (users) [Database Engine], changing availability with Management Studio
ms.assetid: 10d58b92-b67b-47e2-af9c-9f9fd6968bba
author: stevestein
ms.author: sstein
ms.openlocfilehash: fb369ea6a2d1edf1ed8f4377b627fb1ba7339a03
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668607"
---
# <a name="change-an-operator39s-availability"></a><span data-ttu-id="5e00d-102">Изменение доступности оператора</span><span class="sxs-lookup"><span data-stu-id="5e00d-102">Change an Operator&#39;s Availability</span></span>
  <span data-ttu-id="5e00d-103">В этом разделе описано, как изменить расписание оператора по приему уведомлений о предупреждениях в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e00d-103">This topic describes how to change an operator's schedule for receiving alert notifications in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="5e00d-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="5e00d-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5e00d-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="5e00d-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5e00d-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="5e00d-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5e00d-107">**Изменение доступности оператора с помощью:**</span><span class="sxs-lookup"><span data-stu-id="5e00d-107">**To change an operator's availability, using:**</span></span>  
  
     [<span data-ttu-id="5e00d-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5e00d-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5e00d-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5e00d-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5e00d-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="5e00d-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5e00d-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="5e00d-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5e00d-112">Permissions</span><span class="sxs-lookup"><span data-stu-id="5e00d-112">Permissions</span></span>  
 <span data-ttu-id="5e00d-113">Изменять данные операторов могут указывать только члены предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="5e00d-113">Only members of the **sysadmin** fixed server role can edit operators.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5e00d-114">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5e00d-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-an-operators-availability"></a><span data-ttu-id="5e00d-115">Изменение доступности оператора</span><span class="sxs-lookup"><span data-stu-id="5e00d-115">To change an operator's availability</span></span>  
  
1.  <span data-ttu-id="5e00d-116">В **обозревателе объектов**щелкните значок «плюс», чтобы развернуть сервер, содержащий оператора, которого нужно включить или отключить.</span><span class="sxs-lookup"><span data-stu-id="5e00d-116">In **Object Explorer**, click the plus sign to expand server that contains the operator that you want to enable or disable.</span></span>  
  
2.  <span data-ttu-id="5e00d-117">Щелкните знак "плюс", чтобы развернуть **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="5e00d-117">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="5e00d-118">Щелкните значок «плюс», чтобы развернуть папку **Операторы** .</span><span class="sxs-lookup"><span data-stu-id="5e00d-118">Click the plus sign to expand the **Operators** folder.</span></span>  
  
4.  <span data-ttu-id="5e00d-119">Щелкните правой кнопкой мыши оператора, которого нужно включить или отключить, и выберите пункт **Свойства**, а затем перейдите на вкладку **Общие** .</span><span class="sxs-lookup"><span data-stu-id="5e00d-119">Right-click the operator that you want to enable or disable and select **Properties**, then click the **General** tab.</span></span>  
  
5.  <span data-ttu-id="5e00d-120">В диалоговом окне**свойства** _operator_name_установите или снимите флажок **включено** .</span><span class="sxs-lookup"><span data-stu-id="5e00d-120">In the _operator_name_**Properties** dialog box, select or clear the **Enabled** check box.</span></span>  
  
6.  <span data-ttu-id="5e00d-121">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5e00d-121">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5e00d-122">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5e00d-122">Using Transact-SQL</span></span>  
  
#### <a name="to-change-an-operators-availability"></a><span data-ttu-id="5e00d-123">Изменение доступности оператора</span><span class="sxs-lookup"><span data-stu-id="5e00d-123">To change an operator's availability</span></span>  
  
1.  <span data-ttu-id="5e00d-124">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e00d-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5e00d-125">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="5e00d-125">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5e00d-126">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="5e00d-126">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- disables the 'Fran??ois Ajenstat' operator  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_operator   
        @name = N'Fran??ois Ajenstat',  
        @enabled = 0;  
    GO  
    ```  
  
 <span data-ttu-id="5e00d-127">Дополнительные сведения см. в разделе [sp_update_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-operator-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5e00d-127">For more information, see [sp_update_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-operator-transact-sql).</span></span>  
  
  

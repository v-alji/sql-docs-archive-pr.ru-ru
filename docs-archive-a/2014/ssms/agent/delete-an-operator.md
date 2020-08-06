---
title: Удаление оператора | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- canceling operators
- removing operators
- deleting operators
- dropping operators
- jobs [SQL Server Agent], operators
- operators (users) [Database Engine], deleting with Management Studio
ms.assetid: 2b7b8627-082d-4189-8584-abd3a9b604cf
author: stevestein
ms.author: sstein
ms.openlocfilehash: 75bea1c5c5fabff7ce55fe07a5181baa8f99e0fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655527"
---
# <a name="delete-an-operator"></a><span data-ttu-id="151ef-102">Удаление оператора</span><span class="sxs-lookup"><span data-stu-id="151ef-102">Delete an Operator</span></span>
  <span data-ttu-id="151ef-103">В этом разделе описано, как удалить оператора, чтобы он больше не получал [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] уведомления об оповещениях агента в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="151ef-103">This topic describes how to remove an operator so they no longer receive [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert notifications in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="151ef-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="151ef-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="151ef-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="151ef-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="151ef-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="151ef-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="151ef-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="151ef-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="151ef-108">**Удаление оператора с помощью:**</span><span class="sxs-lookup"><span data-stu-id="151ef-108">**To delete an operator, using:**</span></span>  
  
     [<span data-ttu-id="151ef-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="151ef-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="151ef-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="151ef-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="151ef-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="151ef-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="151ef-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="151ef-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="151ef-113">При удалении оператора также удаляются все связанные с ним уведомления.</span><span class="sxs-lookup"><span data-stu-id="151ef-113">When an operator is removed, all the notifications associated with the operator are also removed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="151ef-114">безопасность</span><span class="sxs-lookup"><span data-stu-id="151ef-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="151ef-115">Permissions</span><span class="sxs-lookup"><span data-stu-id="151ef-115">Permissions</span></span>  
 <span data-ttu-id="151ef-116">Удалять операторов могут члены предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="151ef-116">Members of the **sysadmin** fixed server role can delete operators.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="151ef-117">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="151ef-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-an-operator"></a><span data-ttu-id="151ef-118">Удаление оператора</span><span class="sxs-lookup"><span data-stu-id="151ef-118">To delete an operator</span></span>  
  
1.  <span data-ttu-id="151ef-119">В **обозревателе объектов**щелкните значок «плюс», чтобы развернуть сервер, содержащий оператора, которого нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="151ef-119">In **Object Explorer**, click the plus sign to expand the server that contains the operator you want to delete.</span></span>  
  
2.  <span data-ttu-id="151ef-120">Щелкните знак "плюс", чтобы развернуть **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="151ef-120">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="151ef-121">Щелкните значок «плюс», чтобы развернуть папку **Операторы** .</span><span class="sxs-lookup"><span data-stu-id="151ef-121">Click the plus sign to expand the **Operators** folder.</span></span>  
  
4.  <span data-ttu-id="151ef-122">Щелкните правой кнопкой мыши оператор, который необходимо удалить, и выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="151ef-122">Right-click the operator that you want to delete and select **Delete**.</span></span>  
  
5.  <span data-ttu-id="151ef-123">В диалоговом окне **Удаление объекта** убедитесь, что выбран верный оператор, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="151ef-123">In the **Delete Object** dialog box, make sure that the correct operator is selected, and then click **OK**.</span></span> <span data-ttu-id="151ef-124">Если нужно, чтобы предупреждения и задания, предназначенные удаленному оператору, получал другой оператор, установите флажок **Переназначить** и выберите любого оператора из списка</span><span class="sxs-lookup"><span data-stu-id="151ef-124">If you want another operator to receive the alerts and jobs sent to the deleted operator, check **Reassign to** and select an operator in the list.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="151ef-125">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="151ef-125">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-an-operator"></a><span data-ttu-id="151ef-126">Удаление оператора</span><span class="sxs-lookup"><span data-stu-id="151ef-126">To delete an operator</span></span>  
  
1.  <span data-ttu-id="151ef-127">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="151ef-127">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="151ef-128">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="151ef-128">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="151ef-129">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="151ef-129">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- deletes operator 'Test Operator' and reassigns all alerts and jobs sent to that operator to 'Fran??ois Ajenstat'  
    USE msdb ;  
    GO  
  
    EXEC sp_delete_operator @name = 'Test Operator',  
        @reassign_to_operator = 'Fran??ois Ajenstat';  
    GO  
    ```  
  
 <span data-ttu-id="151ef-130">Дополнительные сведения см. в разделе [sp_delete_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-operator-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="151ef-130">For more information, see [sp_delete_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-operator-transact-sql).</span></span>  
  
  

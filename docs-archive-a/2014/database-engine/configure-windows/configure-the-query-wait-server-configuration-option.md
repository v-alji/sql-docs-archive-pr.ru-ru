---
title: Настройка параметра конфигурации сервера "query wait" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], timing out
- time [SQL Server], query wait time
- query wait option [SQL Server]
ms.assetid: 0fc4aa01-65a3-4a33-9ef4-caca41add238
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 638afff2aa05a9fc4e61bc71e8610dba1dda8cf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665553"
---
# <a name="configure-the-query-wait-server-configuration-option"></a><span data-ttu-id="f4006-102">Настройка параметра конфигурации сервера query wait</span><span class="sxs-lookup"><span data-stu-id="f4006-102">Configure the query wait Server Configuration Option</span></span>
  <span data-ttu-id="f4006-103">В этом разделе описано, как настроить параметр конфигурации сервера **query wait** в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4006-103">This topic describes how to configure the **query wait** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="f4006-104">Запросы, требующие много памяти (например, включающие сортировку и хеширование), помещаются в очередь, если для выполнения запроса не хватает памяти.</span><span class="sxs-lookup"><span data-stu-id="f4006-104">Memory-intensive queries (such as those involving sorting and hashing) are queued when there is not enough memory available to run the query.</span></span> <span data-ttu-id="f4006-105">Параметр **query wait** указывает время в секундах (от 0 до 2147483647), в течение которого запрос будет ожидать необходимые ресурсы. Значение по умолчанию для этого параметра равно -1.</span><span class="sxs-lookup"><span data-stu-id="f4006-105">The **query wait** option specifies the time, in seconds (from 0 through 2147483647), that a query waits for resources before it times out. The default value for this option is -1.</span></span> <span data-ttu-id="f4006-106">Это означает, что время ожидания вычисляется как время на запрос, умноженное на 25 раз.</span><span class="sxs-lookup"><span data-stu-id="f4006-106">This means the time-out is calculated as 25 times the estimated query cost.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f4006-107">Транзакция, содержащая ожидающий запрос, может блокироваться, пока запрос ожидает памяти.</span><span class="sxs-lookup"><span data-stu-id="f4006-107">A transaction that contains the waiting query might hold locks while the query waits for memory.</span></span> <span data-ttu-id="f4006-108">В редких ситуациях возможна неопределяемая взаимоблокировка.</span><span class="sxs-lookup"><span data-stu-id="f4006-108">In rare situations, it is possible for an undetectable deadlock to occur.</span></span> <span data-ttu-id="f4006-109">Уменьшение времени ожидания запроса снижает вероятность такой взаимоблокировки.</span><span class="sxs-lookup"><span data-stu-id="f4006-109">Decreasing the query wait time lowers the probability of such deadlocks.</span></span> <span data-ttu-id="f4006-110">Со временем ожидающий запрос будет отменен, и блокировка транзакции снимется.</span><span class="sxs-lookup"><span data-stu-id="f4006-110">Eventually, a waiting query will be terminated and the transaction locks released.</span></span> <span data-ttu-id="f4006-111">Однако увеличение максимального времени ожидания может увеличить время, необходимое для отмены запроса.</span><span class="sxs-lookup"><span data-stu-id="f4006-111">However, increasing the maximum wait time may increase the amount of time for the query to be terminated.</span></span> <span data-ttu-id="f4006-112">Этот параметр не рекомендуется менять.</span><span class="sxs-lookup"><span data-stu-id="f4006-112">Changes to this option are not recommended.</span></span>  
  
 <span data-ttu-id="f4006-113">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="f4006-113">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f4006-114">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="f4006-114">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f4006-115">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="f4006-115">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="f4006-116">Безопасность</span><span class="sxs-lookup"><span data-stu-id="f4006-116">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f4006-117">**Настройка параметра query wait**</span><span class="sxs-lookup"><span data-stu-id="f4006-117">**To configure the query wait option, using:**</span></span>  
  
     [<span data-ttu-id="f4006-118">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f4006-118">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f4006-119">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f4006-119">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="f4006-120">**Дальнейшие действия.**  [После настройки параметра query wait](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="f4006-120">**Follow Up:**  [After you configure the query wait option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f4006-121">Перед началом</span><span class="sxs-lookup"><span data-stu-id="f4006-121">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="f4006-122">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="f4006-122">Recommendations</span></span>  
  
-   <span data-ttu-id="f4006-123">Этот параметр является дополнительным и его следует изменять только опытным администраторам баз данных или сертифицированным техническим специалистам [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f4006-123">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f4006-124">безопасность</span><span class="sxs-lookup"><span data-stu-id="f4006-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f4006-125">Permissions</span><span class="sxs-lookup"><span data-stu-id="f4006-125">Permissions</span></span>  
 <span data-ttu-id="f4006-126">Разрешения на выполнение хранимой процедуры **sp_configure** без параметров или только с первым параметром по умолчанию предоставляются всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="f4006-126">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="f4006-127">Для выполнения процедуры **sp_configure** с обоими параметрами для изменения параметра конфигурации или запуска инструкции RECONFIGURE необходимо иметь разрешение ALTER SETTINGS на уровне сервера.</span><span class="sxs-lookup"><span data-stu-id="f4006-127">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="f4006-128">Разрешение ALTER SETTINGS неявным образом предоставлено предопределенным ролям сервера **sysadmin** и **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="f4006-128">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f4006-129">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f4006-129">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-query-wait-option"></a><span data-ttu-id="f4006-130">Настройка параметра query wait</span><span class="sxs-lookup"><span data-stu-id="f4006-130">To configure the query wait option</span></span>  
  
1.  <span data-ttu-id="f4006-131">В обозревателе объектов щелкните правой кнопкой мыши сервер и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="f4006-131">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="f4006-132">Щелкните узел **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="f4006-132">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="f4006-133">В разделе **Параллелизм**введите необходимое значение параметра **query wait** .</span><span class="sxs-lookup"><span data-stu-id="f4006-133">Under **Parallelism**, type the desired value for the **query wait** option.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f4006-134">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f4006-134">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-query-wait-option"></a><span data-ttu-id="f4006-135">Настройка параметра query wait</span><span class="sxs-lookup"><span data-stu-id="f4006-135">To configure the query wait option</span></span>  
  
1.  <span data-ttu-id="f4006-136">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4006-136">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f4006-137">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="f4006-137">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f4006-138">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="f4006-138">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="f4006-139">В этом примере описывается использование процедуры [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) для задания значения параметра `query wait` равным `7500` секундам.</span><span class="sxs-lookup"><span data-stu-id="f4006-139">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `query wait` option to `7500` seconds.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'query wait', 7500 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="f4006-140">Дополнительные сведения см. в разделе [Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f4006-140">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-query-wait-option"></a><a name="FollowUp"></a> <span data-ttu-id="f4006-141">Дальнейшие действия. После настройки параметра query wait</span><span class="sxs-lookup"><span data-stu-id="f4006-141">Follow Up: After you configure the query wait option</span></span>  
 <span data-ttu-id="f4006-142">Параметр вступает в силу немедленно, без перезапуска сервера.</span><span class="sxs-lookup"><span data-stu-id="f4006-142">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4006-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="f4006-143">See Also</span></span>  
 <span data-ttu-id="f4006-144">[RECONFIGURE (Transact-SQL)](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f4006-144">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="f4006-145">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f4006-145">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="f4006-146">sp_configure (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f4006-146">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  

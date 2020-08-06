---
title: Настройка параметра конфигурации сервера remote proc trans
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- remote proc trans option
- distributed transactions [SQL Server], enforcing
ms.assetid: cfbc6158-ab96-44b4-87eb-ea278c1b0c6b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 54fcaafa51eef33acb1ae8d1e2f36022840b76a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657882"
---
# <a name="configure-the-remote-proc-trans-server-configuration-option"></a><span data-ttu-id="39806-102">Настройка параметра конфигурации сервера remote proc trans</span><span class="sxs-lookup"><span data-stu-id="39806-102">Configure the remote proc trans Server Configuration Option</span></span>
  <span data-ttu-id="39806-103">В этом разделе описываются способы настройки параметра конфигурации сервера **remote proc trans** в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] при помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39806-103">This topic describes how to configure the **remote proc trans** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="39806-104">Параметр **remote proc trans** предназначен для защиты действий межсерверной процедуры с помощью транзакции координатора распределенных транзакций [!INCLUDE[msCoName](../../includes/msconame-md.md)] (MS DTC).</span><span class="sxs-lookup"><span data-stu-id="39806-104">The **remote proc trans** option helps protect the actions of a server-to-server procedure through a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC) transaction.</span></span>  
  
 <span data-ttu-id="39806-105">Установите значение параметра **remote proc trans** равным 1, чтобы применить распределенную транзакцию координатора MS DTC, защищающую свойства ACID (atomic, consistent, isolated, durable — атомарность, согласованность, изолированность, надежность) транзакций.</span><span class="sxs-lookup"><span data-stu-id="39806-105">Set the value of **remote proc trans** to 1 to provide an MS DTC-coordinated distributed transaction that protects the ACID (atomic, consistent, isolated, and durable) properties of transactions.</span></span> <span data-ttu-id="39806-106">Сеансы, начатые после установки этого параметра в 1, наследуют значение этого параметра в качестве значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="39806-106">Sessions begun after setting this option to 1 inherit the configuration setting as their default.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepNextAvoid](../../includes/ssnotedepnextavoid-md.md)]  
  
 <span data-ttu-id="39806-107">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="39806-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="39806-108">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="39806-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="39806-109">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="39806-109">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="39806-110">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="39806-110">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="39806-111">Безопасность</span><span class="sxs-lookup"><span data-stu-id="39806-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="39806-112">**Настройка параметра remote proc trans с помощью различных средств**</span><span class="sxs-lookup"><span data-stu-id="39806-112">**To configure the remote proc trans option, using:**</span></span>  
  
     [<span data-ttu-id="39806-113">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="39806-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="39806-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="39806-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="39806-115">**Дальнейшие действия.**  [После настройки параметра remote proc trans](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="39806-115">**Follow Up:**  [After you configure the remote proc trans option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="39806-116">Перед началом</span><span class="sxs-lookup"><span data-stu-id="39806-116">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="39806-117">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="39806-117">Prerequisites</span></span>  
  
-   <span data-ttu-id="39806-118">Это значение можно установить только при разрешенных соединениях с удаленными серверами.</span><span class="sxs-lookup"><span data-stu-id="39806-118">Remote server connections must be allowed before this value can be set.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="39806-119">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="39806-119">Recommendations</span></span>  
  
-   <span data-ttu-id="39806-120">Этот параметр предоставляется в целях совместимости с предыдущими версиями [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для приложений, использующих удаленные хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="39806-120">This option is provided for compatibility with earlier versions of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for applications that use remote stored procedures.</span></span> <span data-ttu-id="39806-121">Вместо вызовов удаленных хранимых процедур используйте распределенные запросы, которые ссылаются на связанные серверы, определенные с помощью процедуры [sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="39806-121">Instead of issuing remote stored procedure calls, use distributed queries that reference linked servers, which are defined by using [sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="39806-122">безопасность</span><span class="sxs-lookup"><span data-stu-id="39806-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="39806-123">Permissions</span><span class="sxs-lookup"><span data-stu-id="39806-123">Permissions</span></span>  
 <span data-ttu-id="39806-124">Разрешения на выполнение хранимой процедуры **sp_configure** без параметров или только с первым параметром по умолчанию предоставляются всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="39806-124">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="39806-125">Для выполнения процедуры **sp_configure** с обоими параметрами для изменения параметра конфигурации или запуска инструкции RECONFIGURE необходимо иметь разрешение ALTER SETTINGS на уровне сервера.</span><span class="sxs-lookup"><span data-stu-id="39806-125">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="39806-126">Разрешение ALTER SETTINGS неявным образом предоставлено предопределенным ролям сервера **sysadmin** и **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="39806-126">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="39806-127">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="39806-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-remote-proc-trans-option"></a><span data-ttu-id="39806-128">Настройка параметра remote proc trans</span><span class="sxs-lookup"><span data-stu-id="39806-128">To configure the remote proc trans option</span></span>  
  
1.  <span data-ttu-id="39806-129">В обозревателе объектов щелкните правой кнопкой мыши сервер и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="39806-129">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="39806-130">Выберите узел **Соединения** .</span><span class="sxs-lookup"><span data-stu-id="39806-130">Click the **Connections** node.</span></span>  
  
3.  <span data-ttu-id="39806-131">В области **Удаленные серверные соединения**установите флажок **Требовать распределенных транзакций для межсерверных соединений** .</span><span class="sxs-lookup"><span data-stu-id="39806-131">Under **Remote server connections**, select the **Require Distributed Transactions for server to server communication** check box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="39806-132">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="39806-132">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-remote-proc-trans-option"></a><span data-ttu-id="39806-133">Настройка параметра remote proc trans</span><span class="sxs-lookup"><span data-stu-id="39806-133">To configure the remote proc trans option</span></span>  
  
1.  <span data-ttu-id="39806-134">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39806-134">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="39806-135">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="39806-135">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="39806-136">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="39806-136">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="39806-137">В этом примере описывается использование процедуры [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) для задания значения параметра `remote proc trans` равным `1`.</span><span class="sxs-lookup"><span data-stu-id="39806-137">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `remote proc trans` option to `1`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'remote proc trans', 1 ;  
GO  
RECONFIGURE ;  
GO  
  
```  
  
 <span data-ttu-id="39806-138">Дополнительные сведения см. в разделе [Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="39806-138">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-remote-proc-trans-option"></a><a name="FollowUp"></a> <span data-ttu-id="39806-139">Дальнейшие действия. После настройки параметра remote proc trans</span><span class="sxs-lookup"><span data-stu-id="39806-139">Follow Up: After you configure the remote proc trans option</span></span>  
 <span data-ttu-id="39806-140">Параметр вступает в силу немедленно, без перезапуска сервера.</span><span class="sxs-lookup"><span data-stu-id="39806-140">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39806-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="39806-141">See Also</span></span>  
 <span data-ttu-id="39806-142">[RECONFIGURE (Transact-SQL)](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="39806-142">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="39806-143">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="39806-143">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="39806-144">sp_configure (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="39806-144">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  

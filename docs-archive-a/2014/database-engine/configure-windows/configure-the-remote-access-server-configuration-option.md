---
title: Настройка параметра конфигурации сервера "remote access" | Документы Майкрософт
ms.custom: ''
ms.date: 10/19/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- remote servers [SQL Server], stored procedure execution
ms.assetid: f5de748d-1c55-4714-9661-38fe62e5095f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: eef18ec48ede59544b13545e49dc105909cfac16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655947"
---
# <a name="configure-the-remote-access-server-configuration-option"></a><span data-ttu-id="49378-102">Настройка параметра конфигурации сервера remote access</span><span class="sxs-lookup"><span data-stu-id="49378-102">Configure the remote access Server Configuration Option</span></span>
  <span data-ttu-id="49378-103">В этом разделе описываются способы настройки параметра конфигурации сервера **remote access** в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="49378-103">This topic describes how to configure the **remote access** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="49378-104">Параметр **remote access** управляет выполнением хранимых процедур на локальных или удаленных серверах, на которых запущены экземпляры [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="49378-104">The **remote access** option controls the execution of stored procedures from local or remote servers on which instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are running.</span></span> <span data-ttu-id="49378-105">Значение этого параметра по умолчанию равно 1.</span><span class="sxs-lookup"><span data-stu-id="49378-105">This default value for this option is 1.</span></span> <span data-ttu-id="49378-106">Это предоставляет разрешение на запуск локальных хранимых процедур с удаленных серверов или удаленных хранимых процедур с локального сервера.</span><span class="sxs-lookup"><span data-stu-id="49378-106">This grants permission to run local stored procedures from remote servers or remote stored procedures from the local server.</span></span> <span data-ttu-id="49378-107">Значение параметра 0 предотвращает запуск локальных хранимых процедур с удаленных серверов или удаленных хранимых процедур на локальном сервере.</span><span class="sxs-lookup"><span data-stu-id="49378-107">To prevent local stored procedures from being run from a remote server or remote stored procedures from being run on the local server, set the option to 0.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepNextDontUse](../../includes/ssnotedepnextdontuse-md.md)] <span data-ttu-id="49378-108">Вместо этого используйте хранимую процедуру [sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="49378-108">Use [sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql) instead.</span></span>  
  
 <span data-ttu-id="49378-109">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="49378-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="49378-110">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="49378-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="49378-111">Ограничения</span><span class="sxs-lookup"><span data-stu-id="49378-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="49378-112">Безопасность</span><span class="sxs-lookup"><span data-stu-id="49378-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="49378-113">**Настройка параметра remote access с помощью**</span><span class="sxs-lookup"><span data-stu-id="49378-113">**To configure the remote access option, using:**</span></span>  
  
     [<span data-ttu-id="49378-114">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="49378-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="49378-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="49378-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="49378-116">**Дальнейшие действия.**  [После настройки параметра remote access](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="49378-116">**Follow Up:**  [After you configure the remote access option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="49378-117">Перед началом</span><span class="sxs-lookup"><span data-stu-id="49378-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="49378-118">Ограничения</span><span class="sxs-lookup"><span data-stu-id="49378-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="49378-119">Параметр **remote access** применим только к серверам, добавленным при помощи хранимой процедуры [sp_addserver](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql), и включен только в целях обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="49378-119">The **remote access** option only applies to servers that are added by using [sp_addserver](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql), and is included for backward compatibility.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="49378-120">безопасность</span><span class="sxs-lookup"><span data-stu-id="49378-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="49378-121">Permissions</span><span class="sxs-lookup"><span data-stu-id="49378-121">Permissions</span></span>  
 <span data-ttu-id="49378-122">Разрешения на выполнение хранимой процедуры **sp_configure** без параметров или только с первым параметром по умолчанию предоставляются всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="49378-122">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="49378-123">Для выполнения процедуры **sp_configure** с обоими параметрами для изменения параметра конфигурации или запуска инструкции RECONFIGURE необходимо иметь разрешение ALTER SETTINGS на уровне сервера.</span><span class="sxs-lookup"><span data-stu-id="49378-123">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="49378-124">Разрешение ALTER SETTINGS неявным образом предоставлено предопределенным ролям сервера **sysadmin** и **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="49378-124">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="49378-125">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="49378-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-remote-access-option"></a><span data-ttu-id="49378-126">Настройка параметра remote access</span><span class="sxs-lookup"><span data-stu-id="49378-126">To configure the remote access option</span></span>  
  
1.  <span data-ttu-id="49378-127">В обозревателе объектов щелкните правой кнопкой мыши сервер и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="49378-127">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="49378-128">Выберите узел **Соединения** .</span><span class="sxs-lookup"><span data-stu-id="49378-128">Click the **Connections** node.</span></span>  
  
3.  <span data-ttu-id="49378-129">В диалоговом окне **Удаленные серверные соединения**установите или сбросьте флажок **Разрешить удаленные соединения с этим сервером** .</span><span class="sxs-lookup"><span data-stu-id="49378-129">Under **Remote server connections**, select or clear the **Allow remote connections to this server** check box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="49378-130">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="49378-130">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-remote-access-option"></a><span data-ttu-id="49378-131">Настройка параметра remote access</span><span class="sxs-lookup"><span data-stu-id="49378-131">To configure the remote access option</span></span>  
  
1.  <span data-ttu-id="49378-132">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="49378-132">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="49378-133">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="49378-133">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="49378-134">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="49378-134">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="49378-135">В этом примере описывается использование процедуры [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) для задания значения параметра `remote access` равным `0`.</span><span class="sxs-lookup"><span data-stu-id="49378-135">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `remote access` option to `0`.</span></span>  
  
```sql  
EXEC sp_configure 'remote access', 0 ;  
GO  
RECONFIGURE ;  
GO  
  
```  
  
 <span data-ttu-id="49378-136">Дополнительные сведения см. в разделе [Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="49378-136">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-remote-access-option"></a><a name="FollowUp"></a> <span data-ttu-id="49378-137">Дальнейшие действия. После настройки параметра remote access</span><span class="sxs-lookup"><span data-stu-id="49378-137">Follow Up: After you configure the remote access option</span></span>  
 <span data-ttu-id="49378-138">Этот параметр вступит в силу после перезапуска SQL Server.</span><span class="sxs-lookup"><span data-stu-id="49378-138">This setting does not take effect until you restart SQL Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49378-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="49378-139">See Also</span></span>  
 <span data-ttu-id="49378-140">[RECONFIGURE (Transact-SQL)](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="49378-140">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="49378-141">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="49378-141">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="49378-142">sp_configure (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="49378-142">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  

---
title: Настройка параметра конфигурации сервера max text repl size | Документы Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- max text repl size option
ms.assetid: 3056cf64-621d-4996-9162-3913f6bc6d5b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2af0cf426583ee328f0a484de1c3539836c0d8af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665561"
---
# <a name="configure-the-max-text-repl-size-server-configuration-option"></a><span data-ttu-id="3961b-102">Настройка параметра конфигурации сервера max text repl size</span><span class="sxs-lookup"><span data-stu-id="3961b-102">Configure the max text repl size Server Configuration Option</span></span>
  <span data-ttu-id="3961b-103">В этом разделе описываются способы настройки параметра конфигурации сервера **max text repl size** в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3961b-103">This topic describes how to configure the **max text repl size** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="3961b-104">Параметр **max text repl size** задает максимальный размер (в байтах) `text` данных,, `ntext` ,,, `varchar(max)` и, `nvarchar(max)` `varbinary(max)` `xml` `image` которые могут быть добавлены к реплицируемому или записанному столбцу в одной инструкции INSERT, Update, WRITETEXT или UPDATETEXT.</span><span class="sxs-lookup"><span data-stu-id="3961b-104">The **max text repl size** option specifies the maximum size (in bytes) of `text`, `ntext`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)`, `xml`, and `image` data that can be added to a replicated column or captured column in a single INSERT, UPDATE, WRITETEXT, or UPDATETEXT statement.</span></span> <span data-ttu-id="3961b-105">Значение по умолчанию — 65 536 байт.</span><span class="sxs-lookup"><span data-stu-id="3961b-105">The default value is 65536 bytes.</span></span> <span data-ttu-id="3961b-106">Значение -1 означает отсутствие ограничений размера, кроме тех, которые налагаются типом данных.</span><span class="sxs-lookup"><span data-stu-id="3961b-106">A value of -1 indicates that there is no size limit, other than the limit imposed by the data type.</span></span>  
  
 <span data-ttu-id="3961b-107">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="3961b-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3961b-108">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="3961b-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3961b-109">Ограничения</span><span class="sxs-lookup"><span data-stu-id="3961b-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="3961b-110">Безопасность</span><span class="sxs-lookup"><span data-stu-id="3961b-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3961b-111">**Настройка параметра max text repl size с использованием следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="3961b-111">**To configure the max text repl size option, using:**</span></span>  
  
     [<span data-ttu-id="3961b-112">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3961b-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="3961b-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3961b-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="3961b-114">**Дальнейшие действия.**  [После настройки параметра max text repl size](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="3961b-114">**Follow Up:**  [After you configure the max text repl size option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3961b-115">Перед началом</span><span class="sxs-lookup"><span data-stu-id="3961b-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="3961b-116">Ограничения</span><span class="sxs-lookup"><span data-stu-id="3961b-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="3961b-117">Этот параметр применим только к репликации транзакций и системе отслеживания измененных данных.</span><span class="sxs-lookup"><span data-stu-id="3961b-117">This option applies to transactional replication and Change Data Capture.</span></span> <span data-ttu-id="3961b-118">Если сервер настроен как для репликации транзакций, так и для системы отслеживания измененных данных, заданное значение применяется к обеим функциям.</span><span class="sxs-lookup"><span data-stu-id="3961b-118">When a server is configured for both transactional replication and Change Data Capture, the specified value applies to both features.</span></span> <span data-ttu-id="3961b-119">При репликации моментальных снимков и репликации слиянием этот параметр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="3961b-119">This option is ignored by snapshot replication and merge replication.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3961b-120">безопасность</span><span class="sxs-lookup"><span data-stu-id="3961b-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3961b-121">Permissions</span><span class="sxs-lookup"><span data-stu-id="3961b-121">Permissions</span></span>  
 <span data-ttu-id="3961b-122">Разрешения на выполнение хранимой процедуры **sp_configure** без параметров или только с первым параметром по умолчанию предоставляются всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="3961b-122">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="3961b-123">Для выполнения процедуры **sp_configure** с обоими параметрами для изменения параметра конфигурации или запуска инструкции RECONFIGURE необходимо иметь разрешение ALTER SETTINGS на уровне сервера.</span><span class="sxs-lookup"><span data-stu-id="3961b-123">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="3961b-124">Разрешение ALTER SETTINGS неявным образом предоставлено предопределенным ролям сервера **sysadmin** и **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="3961b-124">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3961b-125">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3961b-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-max-text-repl-size-option"></a><span data-ttu-id="3961b-126">Настройка параметра max text repl size</span><span class="sxs-lookup"><span data-stu-id="3961b-126">To configure the max text repl size option</span></span>  
  
1.  <span data-ttu-id="3961b-127">В обозревателе объектов щелкните правой кнопкой мыши сервер и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="3961b-127">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="3961b-128">Щелкните узел **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="3961b-128">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="3961b-129">Во вкладке **Разное**задайте для параметра **max text repl size** нужное значение.</span><span class="sxs-lookup"><span data-stu-id="3961b-129">Under **Miscellaneous**, change the **Max Text Replication Size** option to the desired value.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3961b-130">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3961b-130">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-max-text-repl-size-option"></a><span data-ttu-id="3961b-131">Настройка параметра max text repl size</span><span class="sxs-lookup"><span data-stu-id="3961b-131">To configure the max text repl size option</span></span>  
  
1.  <span data-ttu-id="3961b-132">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3961b-132">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3961b-133">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="3961b-133">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3961b-134">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="3961b-134">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="3961b-135">В этом примере описывается использование процедуры [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) для задания значения параметра `max text repl size` равным `-1`.</span><span class="sxs-lookup"><span data-stu-id="3961b-135">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to configure the `max text repl size` option to `-1`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1 ;   
RECONFIGURE ;   
GO  
EXEC sp_configure 'max text repl size', -1 ;   
GO  
RECONFIGURE;   
GO  
  
```  
  
 <span data-ttu-id="3961b-136">Дополнительные сведения см. в разделе [Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3961b-136">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-max-text-repl-size-option"></a><a name="FollowUp"></a> <span data-ttu-id="3961b-137">Дальнейшие действия. После настройки параметра max text repl size</span><span class="sxs-lookup"><span data-stu-id="3961b-137">Follow Up: After you configure the max text repl size option</span></span>  
 <span data-ttu-id="3961b-138">Параметр вступает в силу немедленно, без перезапуска сервера.</span><span class="sxs-lookup"><span data-stu-id="3961b-138">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3961b-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="3961b-139">See Also</span></span>  
 <span data-ttu-id="3961b-140">[Репликация SQL Server](../../relational-databases/replication/sql-server-replication.md) </span><span class="sxs-lookup"><span data-stu-id="3961b-140">[SQL Server Replication](../../relational-databases/replication/sql-server-replication.md) </span></span>  
 <span data-ttu-id="3961b-141">[INSERT (Transact-SQL)](/sql/t-sql/statements/insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3961b-141">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span></span>  
 <span data-ttu-id="3961b-142">[RECONFIGURE (Transact-SQL)](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3961b-142">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="3961b-143">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3961b-143">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="3961b-144">[sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3961b-144">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="3961b-145">[UPDATE (Transact-SQL)](/sql/t-sql/queries/update-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3961b-145">[UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql) </span></span>  
 <span data-ttu-id="3961b-146">[UPDATETEXT (Transact-SQL)](/sql/t-sql/queries/updatetext-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3961b-146">[UPDATETEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/updatetext-transact-sql) </span></span>  
 [<span data-ttu-id="3961b-147">WRITETEXT (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="3961b-147">WRITETEXT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/writetext-transact-sql)  
  
  

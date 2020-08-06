---
title: Настройка параметра конфигурации сервера "cursor threshold" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- cursor threshold option
ms.assetid: 189f2067-c6c4-48bd-9bd9-65f6b2021c12
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0d7fd9ecafda270a02f1fba9f5dd74adc9e299d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669108"
---
# <a name="configure-the-cursor-threshold-server-configuration-option"></a><span data-ttu-id="e3072-102">Настройка параметра конфигурации сервера cursor threshold</span><span class="sxs-lookup"><span data-stu-id="e3072-102">Configure the cursor threshold Server Configuration Option</span></span>
  <span data-ttu-id="e3072-103">В этом разделе описывается настройка параметра конфигурации сервера **cursor threshold** в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e3072-103">This topic describes how to configure the **cursor threshold** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="e3072-104">Параметр **cursor threshold** используется для указания количества строк в наборе курсора, при котором наборы ключей курсора создаются асинхронно.</span><span class="sxs-lookup"><span data-stu-id="e3072-104">The **cursor threshold** option specifies the number of rows in the cursor set at which cursor keysets are generated asynchronously.</span></span> <span data-ttu-id="e3072-105">Когда курсоры формируют набор ключей для результирующего набора, оптимизатор запросов прогнозирует количество строк, которые будут возвращены для этого результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="e3072-105">When cursors generate a keyset for a result set, the query optimizer estimates the number of rows that will be returned for that result set.</span></span> <span data-ttu-id="e3072-106">Если оптимизатор запросов определяет, что число возвращенных строк превышает указанное пороговое значение, курсор формируется асинхронно, позволяя пользователю извлекать из него строки при продолжающемся процессе его заполнения.</span><span class="sxs-lookup"><span data-stu-id="e3072-106">If the query optimizer estimates that the number of returned rows is greater than this threshold, the cursor is generated asynchronously, allowing the user to fetch rows from the cursor while the cursor continues to be populated.</span></span> <span data-ttu-id="e3072-107">В противном случае курсор формируется синхронно, и запрос ожидает, пока не будут возвращены все строки.</span><span class="sxs-lookup"><span data-stu-id="e3072-107">Otherwise, the cursor is generated synchronously, and the query waits until all rows are returned.</span></span>  
  
 <span data-ttu-id="e3072-108">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="e3072-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e3072-109">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="e3072-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e3072-110">Ограничения</span><span class="sxs-lookup"><span data-stu-id="e3072-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="e3072-111">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="e3072-111">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="e3072-112">Безопасность</span><span class="sxs-lookup"><span data-stu-id="e3072-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e3072-113">**Настройка параметра cursor threshold с помощью следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="e3072-113">**To configure the cursor threshold option, using:**</span></span>  
  
     [<span data-ttu-id="e3072-114">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e3072-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e3072-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e3072-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="e3072-116">**Дальнейшие действия.**  [После настройки параметра cursor threshold](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="e3072-116">**Follow Up:**  [After you configure the cursor threshold option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e3072-117">Перед началом</span><span class="sxs-lookup"><span data-stu-id="e3072-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="e3072-118">Ограничения</span><span class="sxs-lookup"><span data-stu-id="e3072-118">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e3072-119">не поддерживает асинхронное формирование управляемых набором ключей или статических курсоров [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e3072-119">does not support generating keyset-driven or static [!INCLUDE[tsql](../../includes/tsql-md.md)] cursors asynchronously.</span></span> [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="e3072-120">(такие как OPEN или FETCH) пакетированы, поэтому нет необходимости в асинхронном формировании курсоров [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e3072-120">cursor operations such as OPEN or FETCH are batched, so there is no need for the asynchronous generation of [!INCLUDE[tsql](../../includes/tsql-md.md)] cursors.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e3072-121">продолжает поддерживать асинхронные курсоры, управляемые набором ключей, а также статические серверные курсоры API. При этом выполнение инструкции OPEN производится с небольшой задержкой, так как при каждой операции над курсором клиент осуществляет обмен данными с сервером.</span><span class="sxs-lookup"><span data-stu-id="e3072-121">continues to support asynchronous keyset-driven or static application programming interface (API) server cursors where low latency OPEN is a concern, due to client round trips for each cursor operation.</span></span>  
  
-   <span data-ttu-id="e3072-122">Точность определения приблизительного количества строк в наборе ключей зависит от валюты, используемой в статистике по каждой таблице курсора с помощью оптимизатора запросов.</span><span class="sxs-lookup"><span data-stu-id="e3072-122">The accuracy of the query optimizer to determine an estimate for the number of rows in a keyset depends on the currency of the statistics for each of the tables in the cursor.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="e3072-123">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="e3072-123">Recommendations</span></span>  
  
-   <span data-ttu-id="e3072-124">Этот параметр является дополнительным и его следует изменять только опытным администраторам баз данных или сертифицированным техническим специалистам [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e3072-124">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="e3072-125">Если значение параметра **cursor threshold** установить равным -1, все наборы ключей будут создаваться синхронно, что предпочтительно для небольших наборов курсоров.</span><span class="sxs-lookup"><span data-stu-id="e3072-125">If you set **cursor threshold** to -1, all keysets are generated synchronously, which benefits small cursor sets.</span></span> <span data-ttu-id="e3072-126">Если значение параметра **cursor threshold** установить равным 0, все наборы ключей будут создаваться асинхронно.</span><span class="sxs-lookup"><span data-stu-id="e3072-126">If you set **cursor threshold** to 0, all cursor keysets are generated asynchronously.</span></span> <span data-ttu-id="e3072-127">При других значениях оптимизатор запросов сравнивает количество предполагаемых строк в наборе курсора и формирует набор ключей асинхронно, если значение превышает число, заданное параметром **cursor threshold**.</span><span class="sxs-lookup"><span data-stu-id="e3072-127">With other values, the query optimizer compares the number of expected rows in the cursor set and builds the keyset asynchronously if it exceeds the number set in **cursor threshold**.</span></span> <span data-ttu-id="e3072-128">Не следует присваивать параметру **cursor threshold** слишком низкое значение, поскольку небольшие результирующие наборы предпочтительно формировать в синхронном режиме.</span><span class="sxs-lookup"><span data-stu-id="e3072-128">Do not set **cursor threshold** too low, because small result sets are better built synchronously.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e3072-129">безопасность</span><span class="sxs-lookup"><span data-stu-id="e3072-129">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e3072-130">Permissions</span><span class="sxs-lookup"><span data-stu-id="e3072-130">Permissions</span></span>  
 <span data-ttu-id="e3072-131">Разрешения на выполнение хранимой процедуры **sp_configure** без параметров или только с первым параметром по умолчанию предоставляются всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="e3072-131">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="e3072-132">Для выполнения процедуры **sp_configure** с обоими параметрами для изменения параметра конфигурации или запуска инструкции RECONFIGURE необходимо иметь разрешение ALTER SETTINGS на уровне сервера.</span><span class="sxs-lookup"><span data-stu-id="e3072-132">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="e3072-133">Разрешение ALTER SETTINGS неявным образом предоставлено предопределенным ролям сервера **sysadmin** и **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="e3072-133">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e3072-134">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e3072-134">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-cursor-threshold-option"></a><span data-ttu-id="e3072-135">Настройка параметра cursor threshold</span><span class="sxs-lookup"><span data-stu-id="e3072-135">To configure the cursor threshold option</span></span>  
  
1.  <span data-ttu-id="e3072-136">В обозревателе объектов щелкните правой кнопкой мыши сервер и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="e3072-136">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="e3072-137">Щелкните узел **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="e3072-137">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="e3072-138">В области **Разное**установите для параметра **Порог курсора** необходимое значение.</span><span class="sxs-lookup"><span data-stu-id="e3072-138">Under **Miscellaneous**, change the **Cursor Threshold** option to the value you want.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e3072-139">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e3072-139">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-cursor-threshold-option"></a><span data-ttu-id="e3072-140">Настройка параметра cursor threshold</span><span class="sxs-lookup"><span data-stu-id="e3072-140">To configure the cursor threshold option</span></span>  
  
1.  <span data-ttu-id="e3072-141">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e3072-141">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e3072-142">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="e3072-142">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e3072-143">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="e3072-143">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="e3072-144">В этом примере описывается использование хранимой процедуры [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) для задания значения параметра `cursor threshold` равным `0` , при котором наборы ключей курсора формируются асинхронно.</span><span class="sxs-lookup"><span data-stu-id="e3072-144">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the `cursor threshold` option to `0` so that cursor keysets are generated asynchronously.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE  
GO  
EXEC sp_configure 'cursor threshold', 0 ;  
GO  
RECONFIGURE  
GO  
  
```  
  
 <span data-ttu-id="e3072-145">Дополнительные сведения см. в разделе [Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e3072-145">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-cursor-threshold-option"></a><a name="FollowUp"></a> <span data-ttu-id="e3072-146">Дальнейшие действия. После настройки параметра cursor threshold</span><span class="sxs-lookup"><span data-stu-id="e3072-146">Follow Up: After you configure the cursor threshold option</span></span>  
 <span data-ttu-id="e3072-147">Параметр вступает в силу немедленно, без перезапуска сервера.</span><span class="sxs-lookup"><span data-stu-id="e3072-147">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3072-148">См. также:</span><span class="sxs-lookup"><span data-stu-id="e3072-148">See Also</span></span>  
 <span data-ttu-id="e3072-149">[@@CURSOR_ROWS (Transact-SQL)](/sql/t-sql/functions/cursor-rows-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e3072-149">[@@CURSOR_ROWS &#40;Transact-SQL&#41;](/sql/t-sql/functions/cursor-rows-transact-sql) </span></span>  
 <span data-ttu-id="e3072-150">[RECONFIGURE (Transact-SQL)](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e3072-150">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="e3072-151">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e3072-151">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="e3072-152">[sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e3072-152">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="e3072-153">UPDATE STATISTICS (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e3072-153">UPDATE STATISTICS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/update-statistics-transact-sql)  
  
  

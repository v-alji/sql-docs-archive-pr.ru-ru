---
title: Настройка параметра конфигурации сервера "язык полнотекстового поиска по умолчанию" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- languages [full-text search]
- default full-text language option
ms.assetid: 0fa8785b-0830-4a52-aff5-fcf8268b72fc
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ec0736326a4da0708d125bfc480996d54bb86c8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655359"
---
# <a name="configure-the-default-full-text-language-server-configuration-option"></a><span data-ttu-id="b1124-102">Настройка параметра конфигурации сервера «язык полнотекстового поиска по умолчанию»</span><span class="sxs-lookup"><span data-stu-id="b1124-102">Configure the default full-text language Server Configuration Option</span></span>
  <span data-ttu-id="b1124-103">В этом разделе описывается настройка `default full-text language` параметра конфигурации сервера в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b1124-103">This topic describes how to configure the `default full-text language` server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="b1124-104">`default full-text language`Параметр задает значение языка по умолчанию для полнотекстовых индексов.</span><span class="sxs-lookup"><span data-stu-id="b1124-104">The `default full-text language` option specifies a default language value for full-text indexes.</span></span> <span data-ttu-id="b1124-105">Лингвистический анализ выполняется для всех данных с полнотекстовой индексацией и зависит от языка, в котором эти данные представлены.</span><span class="sxs-lookup"><span data-stu-id="b1124-105">Linguistic analysis is performed on all data that is full-text indexed and is dependent on the language of the data.</span></span> <span data-ttu-id="b1124-106">Значением по умолчанию для этого параметра является язык сервера.</span><span class="sxs-lookup"><span data-stu-id="b1124-106">The default value of this option is the language of the server.</span></span> <span data-ttu-id="b1124-107">Для локализованной версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] программа установки устанавливает `default full-text language` параметр на язык сервера, если существует соответствующее совпадение.</span><span class="sxs-lookup"><span data-stu-id="b1124-107">For a localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup sets the `default full-text language` option to the language of the server if an appropriate match exists.</span></span> <span data-ttu-id="b1124-108">Для нелокализованной версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] параметр `default full-text language` по умолчанию имеет значение, соответствующее английскому языку.</span><span class="sxs-lookup"><span data-stu-id="b1124-108">For a non-localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the `default full-text language` option is English.</span></span>  
  
 <span data-ttu-id="b1124-109">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="b1124-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b1124-110">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="b1124-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b1124-111">Ограничения</span><span class="sxs-lookup"><span data-stu-id="b1124-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b1124-112">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="b1124-112">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="b1124-113">Безопасность</span><span class="sxs-lookup"><span data-stu-id="b1124-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b1124-114">**Настройка параметра default full-text language с использованием следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="b1124-114">**To configure the default full-text language option, using:**</span></span>  
  
     [<span data-ttu-id="b1124-115">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b1124-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b1124-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b1124-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="b1124-117">**Дальнейшие действия.**  [После настройки параметра default full-text language](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="b1124-117">**Follow Up:**  [After you configure the default full-text language option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b1124-118">Перед началом</span><span class="sxs-lookup"><span data-stu-id="b1124-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b1124-119">Ограничения</span><span class="sxs-lookup"><span data-stu-id="b1124-119">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="b1124-120">Значение `default full-text language` параметра используется в полнотекстовом индексе, если для столбца не указан язык, используя параметр language **language_term** в ИНСТРУКЦИЯХ CREATE FULLTEXT INDEX и ALTER FULLTEXT INDEX.</span><span class="sxs-lookup"><span data-stu-id="b1124-120">The value of the `default full-text language` option is used in a full-text index when no language is specified for a column through the LANGUAGE **language_term** option in the CREATE FULLTEXT INDEX or ALTER FULLTEXT INDEX statements.</span></span> <span data-ttu-id="b1124-121">Если установленный по умолчанию язык полнотекстового поиска не поддерживается или отсутствует пакет лингвистического анализа, операция CREATE или ALTER завершится ошибкой, а [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] вернет сообщение об указании недопустимого языка.</span><span class="sxs-lookup"><span data-stu-id="b1124-121">If the default full-text language is not supported or the linguistic analysis package is not available, the CREATE or ALTER operation will fail and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will return an error message stating that the language specified is not valid.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="b1124-122">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="b1124-122">Recommendations</span></span>  
  
-   <span data-ttu-id="b1124-123">Этот параметр является дополнительным и его следует изменять только опытным администраторам баз данных или сертифицированным техническим специалистам [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b1124-123">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="b1124-124">Для `default full-text language` параметра требуется значение LCID.</span><span class="sxs-lookup"><span data-stu-id="b1124-124">The `default full-text language` option requires an LCID value.</span></span> <span data-ttu-id="b1124-125">Список поддерживаемых кодов LCID и соответствующих им языков см. в разделе [sys.fulltext_languages (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b1124-125">For a list of supported LCIDs and their related languages, see [sys.fulltext_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql).</span></span> <span data-ttu-id="b1124-126">Могут быть доступны также и другие языки, например, от независимых поставщиков программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="b1124-126">Other languages may also be available from independent software vendors, for example.</span></span> <span data-ttu-id="b1124-127">Если не найден указанный диалект языка, средство полнотекстового поиска автоматически переключается на основной язык.</span><span class="sxs-lookup"><span data-stu-id="b1124-127">If no specific language dialect is found, the Full-Text Engine will automatically switch to the primary language.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b1124-128">безопасность</span><span class="sxs-lookup"><span data-stu-id="b1124-128">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b1124-129">Permissions</span><span class="sxs-lookup"><span data-stu-id="b1124-129">Permissions</span></span>  
 <span data-ttu-id="b1124-130">Разрешения на выполнение хранимой процедуры **sp_configure** без параметров или только с первым параметром по умолчанию предоставляются всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="b1124-130">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="b1124-131">Для выполнения процедуры **sp_configure** с обоими параметрами для изменения параметра конфигурации или запуска инструкции RECONFIGURE необходимо иметь разрешение ALTER SETTINGS на уровне сервера.</span><span class="sxs-lookup"><span data-stu-id="b1124-131">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="b1124-132">Разрешение ALTER SETTINGS неявным образом предоставлено предопределенным ролям сервера **sysadmin** и **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="b1124-132">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b1124-133">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b1124-133">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-default-full-text-language-option"></a><span data-ttu-id="b1124-134">Настройка параметра default full-text language</span><span class="sxs-lookup"><span data-stu-id="b1124-134">To configure the default full-text language option</span></span>  
  
1.  <span data-ttu-id="b1124-135">В обозревателе объектов щелкните правой кнопкой мыши сервер и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="b1124-135">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="b1124-136">Щелкните узел **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="b1124-136">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="b1124-137">На вкладке "Разное" с помощью параметра **Язык полнотекстового поиска по умолчанию** можно задать значение языка по умолчанию для полнотекстовых индексированных столбцов.</span><span class="sxs-lookup"><span data-stu-id="b1124-137">Under Miscellaneous, use **Default Full Text Language** to specify a default language value for full-text indexed columns.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b1124-138">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b1124-138">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-default-full-text-language-option"></a><span data-ttu-id="b1124-139">Настройка параметра default full-text language</span><span class="sxs-lookup"><span data-stu-id="b1124-139">To configure the default full-text language option</span></span>  
  
1.  <span data-ttu-id="b1124-140">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1124-140">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b1124-141">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="b1124-141">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b1124-142">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="b1124-142">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="b1124-143">В этом примере описывается использование хранимой процедуры [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) для присвоения параметру `default full-text` значения "Голландский" (`1043`).</span><span class="sxs-lookup"><span data-stu-id="b1124-143">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `default full-text` option to Dutch (`1043`).</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE  
GO  
EXEC sp_configure 'default full-text language', 1043 ;  
GO  
RECONFIGURE  
GO  
  
```  
  
 <span data-ttu-id="b1124-144">Дополнительные сведения см. в разделе [Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b1124-144">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-default-full-text-language-option"></a><a name="FollowUp"></a> <span data-ttu-id="b1124-145">Дальнейшие действия. После настройки параметра default full-text language</span><span class="sxs-lookup"><span data-stu-id="b1124-145">Follow Up: After you configure the default full-text language option</span></span>  
 <span data-ttu-id="b1124-146">Параметр вступает в силу немедленно, без перезапуска сервера.</span><span class="sxs-lookup"><span data-stu-id="b1124-146">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1124-147">См. также:</span><span class="sxs-lookup"><span data-stu-id="b1124-147">See Also</span></span>  
 <span data-ttu-id="b1124-148">[sys.fulltext_languages (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b1124-148">[sys.fulltext_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql) </span></span>  
 <span data-ttu-id="b1124-149">[RECONFIGURE (Transact-SQL)](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b1124-149">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="b1124-150">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b1124-150">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="b1124-151">[sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b1124-151">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="b1124-152">[CREATE FULLTEXT INDEX (Transact-SQL)](/sql/t-sql/statements/create-fulltext-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b1124-152">[CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql) </span></span>  
 [<span data-ttu-id="b1124-153">ALTER FULLTEXT INDEX (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="b1124-153">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-fulltext-index-transact-sql)  
  
  

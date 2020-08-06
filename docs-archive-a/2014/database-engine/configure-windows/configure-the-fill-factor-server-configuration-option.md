---
title: Настройка параметра конфигурации сервера "fill factor" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- fill factor option [SQL Server]
ms.assetid: b920ec34-ba8b-4bb8-af53-a3ffd06bafa6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 02258c92b4a09277d371e605fd4729ba9fda3461
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665122"
---
# <a name="configure-the-fill-factor-server-configuration-option"></a><span data-ttu-id="bd8ac-102">Настройка параметра конфигурации сервера fill factor</span><span class="sxs-lookup"><span data-stu-id="bd8ac-102">Configure the fill factor Server Configuration Option</span></span>
  <span data-ttu-id="bd8ac-103">В этом разделе описывается настройка параметра конфигурации сервера **fill factor** в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd8ac-103">This topic describes how to configure the **fill factor** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="bd8ac-104">Коэффициент заполнения служит для точной настройки хранения и производительности индекса.</span><span class="sxs-lookup"><span data-stu-id="bd8ac-104">Fill factor is provided for fine-tuning index data storage and performance.</span></span> <span data-ttu-id="bd8ac-105">При создании или перестроении индекса коэффициент заполнения отображает процент заполнения пространства каждой страницы конечного уровня, что позволяет зарезервировать оставшееся пространство как свободное — для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="bd8ac-105">When an index is created or rebuilt, the fill-factor value determines the percentage of space on each leaf-level page to be filled with data, reserving the rest as free space for future growth.</span></span> <span data-ttu-id="bd8ac-106">Дополнительные сведения см. в статье [Указание коэффициента заполнения для индекса](../../relational-databases/indexes/specify-fill-factor-for-an-index.md).</span><span class="sxs-lookup"><span data-stu-id="bd8ac-106">For more information, see [Specify Fill Factor for an Index](../../relational-databases/indexes/specify-fill-factor-for-an-index.md).</span></span>  
  
 <span data-ttu-id="bd8ac-107">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="bd8ac-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="bd8ac-108">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="bd8ac-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="bd8ac-109">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="bd8ac-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="bd8ac-110">Безопасность</span><span class="sxs-lookup"><span data-stu-id="bd8ac-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="bd8ac-111">**Настройка параметра fill factor с помощью различных средств.**</span><span class="sxs-lookup"><span data-stu-id="bd8ac-111">**To configure the fill factor option, using:**</span></span>  
  
     [<span data-ttu-id="bd8ac-112">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bd8ac-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="bd8ac-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bd8ac-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="bd8ac-114">**Дальнейшие действия.**  [После настройки параметра fill factor](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="bd8ac-114">**Follow Up:**  [After you configure the fill factor option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="bd8ac-115">Перед началом</span><span class="sxs-lookup"><span data-stu-id="bd8ac-115">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="bd8ac-116">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="bd8ac-116">Recommendations</span></span>  
  
-   <span data-ttu-id="bd8ac-117">Этот параметр является дополнительным и его следует изменять только опытным администраторам баз данных или сертифицированным техническим специалистам [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bd8ac-117">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="bd8ac-118">безопасность</span><span class="sxs-lookup"><span data-stu-id="bd8ac-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="bd8ac-119">Permissions</span><span class="sxs-lookup"><span data-stu-id="bd8ac-119">Permissions</span></span>  
 <span data-ttu-id="bd8ac-120">Разрешения на выполнение хранимой процедуры **sp_configure** без параметров или только с первым параметром по умолчанию предоставляются всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="bd8ac-120">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="bd8ac-121">Для выполнения процедуры **sp_configure** с обоими параметрами для изменения параметра конфигурации или запуска инструкции RECONFIGURE необходимо иметь разрешение ALTER SETTINGS на уровне сервера.</span><span class="sxs-lookup"><span data-stu-id="bd8ac-121">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="bd8ac-122">Разрешение ALTER SETTINGS неявным образом предоставлено предопределенным ролям сервера **sysadmin** и **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="bd8ac-122">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="bd8ac-123">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bd8ac-123">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-fill-factor-option"></a><span data-ttu-id="bd8ac-124">Настройка параметра fill factor</span><span class="sxs-lookup"><span data-stu-id="bd8ac-124">To configure the fill factor option</span></span>  
  
1.  <span data-ttu-id="bd8ac-125">В обозревателе объектов щелкните правой кнопкой мыши сервер и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="bd8ac-125">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="bd8ac-126">Щелкните узел **Параметры базы данных** .</span><span class="sxs-lookup"><span data-stu-id="bd8ac-126">Click the **Database Settings** node.</span></span>  
  
3.  <span data-ttu-id="bd8ac-127">В поле **Коэффициент заполнения индекса, используемый по умолчанию** введите или выберите нужный коэффициент заполнения индекса.</span><span class="sxs-lookup"><span data-stu-id="bd8ac-127">In the **Default index fill factor** box, type or select the index fill factor that you want.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="bd8ac-128">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bd8ac-128">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-fill-factor-option"></a><span data-ttu-id="bd8ac-129">Настройка параметра fill factor</span><span class="sxs-lookup"><span data-stu-id="bd8ac-129">To configure the fill factor option</span></span>  
  
1.  <span data-ttu-id="bd8ac-130">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd8ac-130">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="bd8ac-131">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="bd8ac-131">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="bd8ac-132">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="bd8ac-132">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="bd8ac-133">В этом примере описывается использование процедуры [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) для задания значения параметра `fill factor` равным `100`.</span><span class="sxs-lookup"><span data-stu-id="bd8ac-133">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `fill factor` option to `100`.</span></span>  
  
```sql  
Use AdventureWorks2012;  
GO  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'fill factor', 100;  
GO  
RECONFIGURE;  
GO  
```  
  
 <span data-ttu-id="bd8ac-134">Дополнительные сведения см. в разделе [Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="bd8ac-134">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-fill-factor-option"></a><a name="FollowUp"></a> <span data-ttu-id="bd8ac-135">Дальнейшие действия. После настройки параметра fill factor</span><span class="sxs-lookup"><span data-stu-id="bd8ac-135">Follow Up: After you configure the fill factor option</span></span>  
 <span data-ttu-id="bd8ac-136">Чтобы изменения вступили в силу, необходимо перезапустить сервер.</span><span class="sxs-lookup"><span data-stu-id="bd8ac-136">The server must be restarted before the setting can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd8ac-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="bd8ac-137">See Also</span></span>  
 <span data-ttu-id="bd8ac-138">[RECONFIGURE (Transact-SQL)](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bd8ac-138">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="bd8ac-139">[ALTER INDEX (Transact-SQL)](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bd8ac-139">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 <span data-ttu-id="bd8ac-140">[CREATE INDEX (Transact-SQL)](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bd8ac-140">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 <span data-ttu-id="bd8ac-141">[Указание коэффициента заполнения для индекса](../../relational-databases/indexes/specify-fill-factor-for-an-index.md) </span><span class="sxs-lookup"><span data-stu-id="bd8ac-141">[Specify Fill Factor for an Index](../../relational-databases/indexes/specify-fill-factor-for-an-index.md) </span></span>  
 <span data-ttu-id="bd8ac-142">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="bd8ac-142">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="bd8ac-143">[sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bd8ac-143">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="bd8ac-144">sys.indexes (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="bd8ac-144">sys.indexes &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-indexes-transact-sql)  
  
  

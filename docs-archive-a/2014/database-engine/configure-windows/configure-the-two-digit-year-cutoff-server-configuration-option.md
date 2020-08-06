---
title: Настройка параметра конфигурации сервера two digit year cutoff | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- two digit year cutoff option
- four-digit years [SQL Server]
ms.assetid: d94e81b6-f2e6-47ef-b497-ec3d827a1646
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c31c1d87c8b743132dd90d495f73ef711dc1f813
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657879"
---
# <a name="configure-the-two-digit-year-cutoff-server-configuration-option"></a><span data-ttu-id="117f8-102">Настройка параметра конфигурации сервера two digit year cutoff</span><span class="sxs-lookup"><span data-stu-id="117f8-102">Configure the two digit year cutoff Server Configuration Option</span></span>
  <span data-ttu-id="117f8-103">В этом разделе описываются способы настройки параметра конфигурации сервера **two digit year cutoff** в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="117f8-103">This topic describes how to configure the **two digit year cutoff** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="117f8-104">Параметр **two digit year cutoff** предназначен для указания целого числа в диапазоне от 1753 до 9999, которое представляет граничное значение при интерпретации года, указанного двумя цифрами.</span><span class="sxs-lookup"><span data-stu-id="117f8-104">The **two digit year cutoff** option specifies an integer from 1753 to 9999 that represents the cutoff year for interpreting two-digit years as four-digit years.</span></span> <span data-ttu-id="117f8-105">Временной промежуток по умолчанию для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] составляет 1950–2049, то есть пороговый год — 2049.</span><span class="sxs-lookup"><span data-stu-id="117f8-105">The default time span for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is 1950-2049, which represents a cutoff year of 2049.</span></span> <span data-ttu-id="117f8-106">Это означает, что [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] интерпретирует двузначный год 49 как 2049, двузначный год 50 как 1950, а двузначный год 99 как 1999.</span><span class="sxs-lookup"><span data-stu-id="117f8-106">This means that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] interprets a two-digit year of 49 as 2049, a two-digit year of 50 as 1950, and a two-digit year of 99 as 1999.</span></span> <span data-ttu-id="117f8-107">Для поддержания обратной совместимости следует оставить этот параметр в значении по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="117f8-107">To maintain backward compatibility, leave the setting at the default value.</span></span>  
  
 <span data-ttu-id="117f8-108">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="117f8-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="117f8-109">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="117f8-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="117f8-110">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="117f8-110">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="117f8-111">Безопасность</span><span class="sxs-lookup"><span data-stu-id="117f8-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="117f8-112">**Настройка параметра two digit year cutoff с помощью**</span><span class="sxs-lookup"><span data-stu-id="117f8-112">**To configure the two digit year cutoff option, using:**</span></span>  
  
     [<span data-ttu-id="117f8-113">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="117f8-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="117f8-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="117f8-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="117f8-115">**Дальнейшие действия.**  [После настройки параметра two digit year cutoff](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="117f8-115">**Follow Up:**  [After you configure the two digit year cutoff option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="117f8-116">Перед началом</span><span class="sxs-lookup"><span data-stu-id="117f8-116">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="117f8-117">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="117f8-117">Recommendations</span></span>  
  
-   <span data-ttu-id="117f8-118">Этот параметр является дополнительным и его следует изменять только опытным администраторам баз данных или сертифицированным техническим специалистам [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="117f8-118">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="117f8-119">Объекты автоматизации OLE используют значение 2030 в качестве порогового значения года для двузначной записи.</span><span class="sxs-lookup"><span data-stu-id="117f8-119">OLE Automation objects use 2030 as the two-digit cutoff year.</span></span> <span data-ttu-id="117f8-120">Можно использовать параметр **two digit year cutoff** , чтобы обеспечить совместимость значений дат между [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и клиентскими приложениями.</span><span class="sxs-lookup"><span data-stu-id="117f8-120">You can use the **two digit year cutoff** option to provide consistency in date values between [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and client applications.</span></span> <span data-ttu-id="117f8-121">Однако во избежание неоднозначности дат лучше использовать четырехзначные числа для обозначения лет в данных.</span><span class="sxs-lookup"><span data-stu-id="117f8-121">However, to avoid ambiguity with dates, use four-digit years in your data.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="117f8-122">безопасность</span><span class="sxs-lookup"><span data-stu-id="117f8-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="117f8-123">Permissions</span><span class="sxs-lookup"><span data-stu-id="117f8-123">Permissions</span></span>  
 <span data-ttu-id="117f8-124">Разрешения на выполнение хранимой процедуры **sp_configure** без параметров или только с первым параметром по умолчанию предоставляются всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="117f8-124">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="117f8-125">Для выполнения процедуры **sp_configure** с обоими параметрами для изменения параметра конфигурации или запуска инструкции RECONFIGURE необходимо иметь разрешение ALTER SETTINGS на уровне сервера.</span><span class="sxs-lookup"><span data-stu-id="117f8-125">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="117f8-126">Разрешение ALTER SETTINGS неявным образом предоставлено предопределенным ролям сервера **sysadmin** и **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="117f8-126">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="117f8-127">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="117f8-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-two-digit-year-cutoff-option"></a><span data-ttu-id="117f8-128">Настройка параметра two digit year cutoff</span><span class="sxs-lookup"><span data-stu-id="117f8-128">To configure the two digit year cutoff option</span></span>  
  
1.  <span data-ttu-id="117f8-129">В обозревателе объектов щелкните правой кнопкой мыши сервер и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="117f8-129">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="117f8-130">Щелкните узел **Прочие параметры сервера** .</span><span class="sxs-lookup"><span data-stu-id="117f8-130">Click the **Misc server settings** node.</span></span>  
  
3.  <span data-ttu-id="117f8-131">В области **Поддержка года из двух цифр**в поле **Если введено две цифры года**, **рассматривать их как год между** введите или выберите значение, которое будет конечным годом необходимого временного промежутка.</span><span class="sxs-lookup"><span data-stu-id="117f8-131">Under **Two digit year support**, in the **When a two digit year is entered**, **interpret it as a year between** box, type or select a value that is the ending year of the time span.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="117f8-132">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="117f8-132">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-two-digit-year-cutoff-option"></a><span data-ttu-id="117f8-133">Настройка параметра two digit year cutoff</span><span class="sxs-lookup"><span data-stu-id="117f8-133">To configure the two digit year cutoff option</span></span>  
  
1.  <span data-ttu-id="117f8-134">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="117f8-134">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="117f8-135">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="117f8-135">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="117f8-136">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="117f8-136">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="117f8-137">В этом примере описывается использование процедуры [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) для задания значения параметра `two digit year cutoff` равным `2030`.</span><span class="sxs-lookup"><span data-stu-id="117f8-137">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `two digit year cutoff` option to `2030`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'two digit year cutoff', 2030 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="117f8-138">Дополнительные сведения см. в разделе [Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="117f8-138">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-two-digit-year-cutoff-option"></a><a name="FollowUp"></a> <span data-ttu-id="117f8-139">Дальнейшие действия. После настройки параметра two digit year cutoff</span><span class="sxs-lookup"><span data-stu-id="117f8-139">Follow Up: After you configure the two digit year cutoff option</span></span>  
 <span data-ttu-id="117f8-140">Параметр вступает в силу немедленно, без перезапуска сервера.</span><span class="sxs-lookup"><span data-stu-id="117f8-140">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="117f8-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="117f8-141">See Also</span></span>  
 <span data-ttu-id="117f8-142">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="117f8-142">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="117f8-143">[sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="117f8-143">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="117f8-144">RECONFIGURE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="117f8-144">RECONFIGURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/reconfigure-transact-sql)  
  
  

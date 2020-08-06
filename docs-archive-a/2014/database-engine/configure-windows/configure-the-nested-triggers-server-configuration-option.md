---
title: Настройка параметра конфигурации сервера nested triggers | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- nested triggers option
ms.assetid: 29d7372b-d406-4a5b-80c6-a2d231d25211
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7b27e185b0833f2e51be16393ff4d59a81046970
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665563"
---
# <a name="configure-the-nested-triggers-server-configuration-option"></a><span data-ttu-id="5651a-102">Настройка конфигурации сервера nested triggers</span><span class="sxs-lookup"><span data-stu-id="5651a-102">Configure the nested triggers Server Configuration Option</span></span>
  <span data-ttu-id="5651a-103">В этом разделе описывается настройка параметра конфигурации сервера **nested triggers** в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5651a-103">This topic describes how to configure the **nested triggers** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5651a-104">Параметр **nested triggers** определяет, допустимо ли каскадирование триггеров AFTER.</span><span class="sxs-lookup"><span data-stu-id="5651a-104">The **nested triggers** option controls whether an AFTER trigger can cascade.</span></span> <span data-ttu-id="5651a-105">Под этим подразумевается выполнение действия, вызывающего срабатывание другого триггера, который может инициировать другой триггер, и т. д.</span><span class="sxs-lookup"><span data-stu-id="5651a-105">That is, perform an action that initiates another trigger, which initiates another trigger, and so on.</span></span> <span data-ttu-id="5651a-106">Когда параметр **nested triggers** принимает значение 0, триггеры AFTER не могут вызывать каскадные действия.</span><span class="sxs-lookup"><span data-stu-id="5651a-106">When **nested triggers** is set to 0, AFTER triggers cannot cascade.</span></span> <span data-ttu-id="5651a-107">Если параметр **nested triggers** равен 1 (значение по умолчанию), триггеры AFTER могут выполнять каскадные действия глубиной до 32 уровней.</span><span class="sxs-lookup"><span data-stu-id="5651a-107">When **nested triggers** is set to 1 (the default), AFTER triggers can cascade to as many as 32 levels.</span></span> <span data-ttu-id="5651a-108">Триггеры INSTEAD OF могут быть вложенными вне зависимости от этого параметра.</span><span class="sxs-lookup"><span data-stu-id="5651a-108">INSTEAD OF triggers can be nested regardless of the setting of this option.</span></span>  
  
 <span data-ttu-id="5651a-109">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="5651a-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5651a-110">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="5651a-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5651a-111">Безопасность</span><span class="sxs-lookup"><span data-stu-id="5651a-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5651a-112">**Настройка параметра nested triggers с использованием следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="5651a-112">**To configure the nested triggers option, using:**</span></span>  
  
     [<span data-ttu-id="5651a-113">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5651a-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5651a-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5651a-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="5651a-115">**Дальнейшие действия.**  [После настройки параметра nested triggers](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="5651a-115">**Follow Up:**  [After you configure the nested triggers option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5651a-116">Перед началом</span><span class="sxs-lookup"><span data-stu-id="5651a-116">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5651a-117">безопасность</span><span class="sxs-lookup"><span data-stu-id="5651a-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5651a-118">Permissions</span><span class="sxs-lookup"><span data-stu-id="5651a-118">Permissions</span></span>  
 <span data-ttu-id="5651a-119">Разрешения на выполнение хранимой процедуры **sp_configure** без параметров или только с первым параметром по умолчанию предоставляются всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="5651a-119">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="5651a-120">Для выполнения процедуры **sp_configure** с обоими параметрами для изменения параметра конфигурации или запуска инструкции RECONFIGURE необходимо иметь разрешение ALTER SETTINGS на уровне сервера.</span><span class="sxs-lookup"><span data-stu-id="5651a-120">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="5651a-121">Разрешение ALTER SETTINGS неявным образом предоставлено предопределенным ролям сервера **sysadmin** и **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="5651a-121">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5651a-122">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5651a-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-nested-triggers-option"></a><span data-ttu-id="5651a-123">Настройка параметра nested triggers</span><span class="sxs-lookup"><span data-stu-id="5651a-123">To configure the nested triggers option</span></span>  
  
1.  <span data-ttu-id="5651a-124">В **обозревателе объектов**щелкните сервер правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="5651a-124">In **Object Explorer**, right-click a server, and then select **Properties**.</span></span>  
  
2.  <span data-ttu-id="5651a-125">На странице **Дополнительно** выберите значение **True** (по умолчанию) или **False** для параметра **Разрешить триггерам активировать другие триггеры**.</span><span class="sxs-lookup"><span data-stu-id="5651a-125">On the **Advanced** page, set the **Allow Triggers to Fire Others** option to **True** (the default) or **False**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5651a-126">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5651a-126">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-nested-triggers-option"></a><span data-ttu-id="5651a-127">Настройка параметра nested triggers</span><span class="sxs-lookup"><span data-stu-id="5651a-127">To configure the nested triggers option</span></span>  
  
1.  <span data-ttu-id="5651a-128">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5651a-128">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5651a-129">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="5651a-129">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5651a-130">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="5651a-130">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="5651a-131">В этом примере описывается использование процедуры [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) для задания значения параметра `nested triggers` равным `0`.</span><span class="sxs-lookup"><span data-stu-id="5651a-131">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `nested triggers` option to `0`.</span></span>  
  
```wmimof  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'nested triggers', 0 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="5651a-132">Дополнительные сведения см. в разделе [Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5651a-132">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-nested-triggers-option"></a><a name="FollowUp"></a> <span data-ttu-id="5651a-133">Дальнейшие действия. После настройки параметра nested triggers</span><span class="sxs-lookup"><span data-stu-id="5651a-133">Follow Up: After you configure the nested triggers option</span></span>  
 <span data-ttu-id="5651a-134">Параметр вступает в силу немедленно, без перезапуска сервера.</span><span class="sxs-lookup"><span data-stu-id="5651a-134">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5651a-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="5651a-135">See Also</span></span>  
 <span data-ttu-id="5651a-136">[Создание вложенных триггеров](../../relational-databases/triggers/create-nested-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="5651a-136">[Create Nested Triggers](../../relational-databases/triggers/create-nested-triggers.md) </span></span>  
 <span data-ttu-id="5651a-137">[RECONFIGURE (Transact-SQL)](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5651a-137">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="5651a-138">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5651a-138">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="5651a-139">sp_configure (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="5651a-139">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  

---
title: Настройка общих свойств управления на основе политик | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.PolicyManagement.f1
helpviewer_keywords:
- Policy-Based Management, configure properties
ms.assetid: 6d1e0e37-29ea-408a-a055-384984d884be
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a2efb37fafa29bcb043dedbcfa8719d0092b1c77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731522"
---
# <a name="configure-the-general-properties-of-policy-based-management"></a><span data-ttu-id="8c8b5-102">Настройка общих свойств управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="8c8b5-102">Configure the General Properties of Policy-Based Management</span></span>
  <span data-ttu-id="8c8b5-103">В этом разделе описывается настройка свойств для управления на основе политик в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c8b5-103">This topic describes how to configure the properties for Policy-Based Management in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="8c8b5-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="8c8b5-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8c8b5-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="8c8b5-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8c8b5-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="8c8b5-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8c8b5-107">**Для настройки управления на основе политик используется:**</span><span class="sxs-lookup"><span data-stu-id="8c8b5-107">**To configure Policy-Based Management, using:**</span></span>  
  
     [<span data-ttu-id="8c8b5-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8c8b5-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8c8b5-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8c8b5-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8c8b5-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="8c8b5-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8c8b5-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="8c8b5-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8c8b5-112">Permissions</span><span class="sxs-lookup"><span data-stu-id="8c8b5-112">Permissions</span></span>  
 <span data-ttu-id="8c8b5-113">Требуется членство в предопределенной роли базы данных PolicyAdministratorRole.</span><span class="sxs-lookup"><span data-stu-id="8c8b5-113">Requires membership in the PolicyAdministratorRole fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8c8b5-114">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8c8b5-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-policy-based-management"></a><span data-ttu-id="8c8b5-115">Настройка управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="8c8b5-115">To configure Policy-Based Management</span></span>  
  
1.  <span data-ttu-id="8c8b5-116">В **обозревателе объектов**щелкните знак "плюс", чтобы развернуть сервер, на котором необходимо настроить свойства управления на основе политик.</span><span class="sxs-lookup"><span data-stu-id="8c8b5-116">In **Object Explorer**, click the plus sign to expand the server where you want to configure Policy-Based Management properties.</span></span>  
  
2.  <span data-ttu-id="8c8b5-117">Щелкните знак «плюс», чтобы развернуть папку **Управление** .</span><span class="sxs-lookup"><span data-stu-id="8c8b5-117">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="8c8b5-118">Щелкните правой кнопкой мыши элемент **Управление политиками** и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="8c8b5-118">Right-click **Policy Management** and select **Properties**.</span></span>  
  
     <span data-ttu-id="8c8b5-119">В диалоговом окне **Свойства управления политиками** доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="8c8b5-119">The following options are available in **Policy Management Properties** dialog box.</span></span>  
  
     <span data-ttu-id="8c8b5-120">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="8c8b5-120">**Enabled**</span></span>  
     <span data-ttu-id="8c8b5-121">Указывает, включено ли управление на основе политик.</span><span class="sxs-lookup"><span data-stu-id="8c8b5-121">Specifies whether Policy-Based Management is enabled.</span></span>  
  
     <span data-ttu-id="8c8b5-122">**HistoryRetentionInDays**</span><span class="sxs-lookup"><span data-stu-id="8c8b5-122">**HistoryRetentionInDays**</span></span>  
     <span data-ttu-id="8c8b5-123">Указывает число дней, в течение которых хранится журнал вычисления политик.</span><span class="sxs-lookup"><span data-stu-id="8c8b5-123">Specifies the number of days that policy evaluation history should be retained.</span></span> <span data-ttu-id="8c8b5-124">Если это значение равно 0 (по умолчанию), то журнал автоматически не удаляется.</span><span class="sxs-lookup"><span data-stu-id="8c8b5-124">If this value is 0 (the default), the history will not be automatically removed.</span></span>  
  
     <span data-ttu-id="8c8b5-125">**LogOnSuccess**</span><span class="sxs-lookup"><span data-stu-id="8c8b5-125">**LogOnSuccess**</span></span>  
     <span data-ttu-id="8c8b5-126">Указывает, регистрирует ли управление на основе политик успешное вычисление политик.</span><span class="sxs-lookup"><span data-stu-id="8c8b5-126">Specifies whether Policy-Based Management logs successful policy evaluations.</span></span>  
  
    -   <span data-ttu-id="8c8b5-127">Если это значение равно false (по умолчанию), то регистрируются только вычисления политик, завершившиеся ошибками.</span><span class="sxs-lookup"><span data-stu-id="8c8b5-127">When this value is false (the default), only failed policy evaluations are logged.</span></span>  
  
    -   <span data-ttu-id="8c8b5-128">Если это значение равно true, то регистрируются и успешные вычисления, и вычисления, завершившиеся ошибками.</span><span class="sxs-lookup"><span data-stu-id="8c8b5-128">When this value is true, both successful and failed policy evaluations are logged.</span></span>  
  
4.  <span data-ttu-id="8c8b5-129">После завершения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8c8b5-129">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8c8b5-130">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8c8b5-130">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-policy-based-management"></a><span data-ttu-id="8c8b5-131">Настройка управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="8c8b5-131">To configure Policy-Based Management</span></span>  
  
1.  <span data-ttu-id="8c8b5-132">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c8b5-132">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8c8b5-133">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="8c8b5-133">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8c8b5-134">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="8c8b5-134">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- enables Policy-Based Management   
    USE msdb;  
    GO  
    EXEC dbo.sp_syspolicy_configure   
         @name = N'Enabled',   
         @value = 1;  
    GO  
    ```  
  
 <span data-ttu-id="8c8b5-135">Дополнительные сведения см. в разделе [sp_syspolicy_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-syspolicy-configure-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8c8b5-135">For more information, see [sp_syspolicy_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-configure-transact-sql).</span></span>  
  
  

---
title: Включение или отключение сбора данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- data collector [SQL Server], disabling
- data collector [SQL Server], enabling
ms.assetid: 0137971b-fb48-4a3e-822a-3df2b9bb09d7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: af5cc647a63d3a9451086fc9e2211dec809e88fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656418"
---
# <a name="enable-or-disable-data-collection"></a><span data-ttu-id="1c077-102">Включение или отключение сбор данных</span><span class="sxs-lookup"><span data-stu-id="1c077-102">Enable or Disable Data Collection</span></span>
  <span data-ttu-id="1c077-103">В этом разделе описывается включение и отключение сбора данных в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c077-103">This topic describes how to enable or disable data collection in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="1c077-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="1c077-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1c077-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="1c077-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1c077-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="1c077-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1c077-107">**Включение или отключение сбора данных с помощью следующих средств**</span><span class="sxs-lookup"><span data-stu-id="1c077-107">**To enable or disable data collection, using:**</span></span>  
  
     [<span data-ttu-id="1c077-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1c077-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1c077-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1c077-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1c077-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="1c077-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1c077-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="1c077-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1c077-112">Permissions</span><span class="sxs-lookup"><span data-stu-id="1c077-112">Permissions</span></span>  
 <span data-ttu-id="1c077-113">Для выполнения этой процедуры требуется членство в предопределенной роли базы данных **dc_admin** или **dc_operator** (с разрешением EXECUTE).</span><span class="sxs-lookup"><span data-stu-id="1c077-113">Requires membership in the **dc_admin** or **dc_operator** (with EXECUTE permission) fixed database role to execute this procedure.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1c077-114">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1c077-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-enable-the-data-collector"></a><span data-ttu-id="1c077-115">Включение сборщика данных</span><span class="sxs-lookup"><span data-stu-id="1c077-115">To enable the data collector</span></span>  
  
1.  <span data-ttu-id="1c077-116">В обозревателе объектов раскройте узел **Управление** .</span><span class="sxs-lookup"><span data-stu-id="1c077-116">In Object Explorer, expand the **Management** node.</span></span>  
  
2.  <span data-ttu-id="1c077-117">Щелкните правой кнопкой мыши **Сбор данных**, затем выберите **Включить сбор данных**.</span><span class="sxs-lookup"><span data-stu-id="1c077-117">Right-click **Data Collection**, and then click **Enable Data Collection**.</span></span>  
  
#### <a name="to-disable-the-data-collector"></a><span data-ttu-id="1c077-118">Отключение сборщика данных</span><span class="sxs-lookup"><span data-stu-id="1c077-118">To disable the data collector</span></span>  
  
1.  <span data-ttu-id="1c077-119">В обозревателе объектов раскройте узел **Управление** .</span><span class="sxs-lookup"><span data-stu-id="1c077-119">In Object Explorer, expand the **Management** node.</span></span>  
  
2.  <span data-ttu-id="1c077-120">Щелкните правой кнопкой мыши пункт **Сбор данных**и выберите команду **Отключить сбор данных**.</span><span class="sxs-lookup"><span data-stu-id="1c077-120">Right-click **Data Collection**, and then click **Disable Data Collection**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1c077-121">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1c077-121">Using Transact-SQL</span></span>  
  
#### <a name="to-enable-the-data-collector"></a><span data-ttu-id="1c077-122">Включение сборщика данных</span><span class="sxs-lookup"><span data-stu-id="1c077-122">To enable the data collector</span></span>  
  
1.  <span data-ttu-id="1c077-123">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c077-123">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1c077-124">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="1c077-124">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1c077-125">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="1c077-125">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="1c077-126">В этом примере используется хранимая процедура [sp_syscollector_enable_collector](/sql/relational-databases/system-stored-procedures/sp-syscollector-enable-collector-transact-sql) для включения сборщика данных.</span><span class="sxs-lookup"><span data-stu-id="1c077-126">This example uses [sp_syscollector_enable_collector](/sql/relational-databases/system-stored-procedures/sp-syscollector-enable-collector-transact-sql) to enable the data collector.</span></span>  
  
```sql  
USE msdb;  
GO  
EXEC dbo.sp_syscollector_enable_collector ;  
```  
  
#### <a name="to-disable-the-data-collector"></a><span data-ttu-id="1c077-127">Отключение сборщика данных</span><span class="sxs-lookup"><span data-stu-id="1c077-127">To disable the data collector</span></span>  
  
1.  <span data-ttu-id="1c077-128">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c077-128">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1c077-129">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="1c077-129">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1c077-130">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="1c077-130">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="1c077-131">В этом примере используется хранимая процедура [sp_syscollector_disable_collector](/sql/relational-databases/system-stored-procedures/sp-syscollector-disable-collector-transact-sql) для отключения сборщика данных.</span><span class="sxs-lookup"><span data-stu-id="1c077-131">This example uses [sp_syscollector_disable_collector](/sql/relational-databases/system-stored-procedures/sp-syscollector-disable-collector-transact-sql) to disable the data collector.</span></span>  
  
```sql  
USE msdb;  
GO  
EXEC dbo.sp_syscollector_disable_collector;  
```  
  
## <a name="see-also"></a><span data-ttu-id="1c077-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="1c077-132">See Also</span></span>  
 <span data-ttu-id="1c077-133">[Сбор данных](data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="1c077-133">[Data Collection](data-collection.md) </span></span>  
 [<span data-ttu-id="1c077-134">Системные хранимые процедуры (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="1c077-134">System Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql)  
  
  

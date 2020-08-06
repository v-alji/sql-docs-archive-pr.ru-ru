---
title: Изменение статистики | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- statistics [SQL Server], modifying
- modifying statistics
ms.assetid: b06299ca-ed52-411a-b245-45eac4628c99
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6dd44da6d1a80050f37f08e49773f95af0e5a339
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667632"
---
# <a name="modify-statistics"></a><span data-ttu-id="59e4d-102">Изменение статистики</span><span class="sxs-lookup"><span data-stu-id="59e4d-102">Modify Statistics</span></span>
  <span data-ttu-id="59e4d-103">Существующую статистику в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] можно изменить с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="59e4d-103">You can modify existing statistics in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="59e4d-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="59e4d-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="59e4d-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="59e4d-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="59e4d-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="59e4d-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="59e4d-107">**Для изменения статистики используются:**</span><span class="sxs-lookup"><span data-stu-id="59e4d-107">**To modify statistics, using:**</span></span>  
  
     [<span data-ttu-id="59e4d-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="59e4d-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="59e4d-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="59e4d-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="59e4d-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="59e4d-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="59e4d-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="59e4d-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="59e4d-112">Permissions</span><span class="sxs-lookup"><span data-stu-id="59e4d-112">Permissions</span></span>  
 <span data-ttu-id="59e4d-113">Должны выполняться следующие требования.</span><span class="sxs-lookup"><span data-stu-id="59e4d-113">Requires that:</span></span>  
  
-   <span data-ttu-id="59e4d-114">пользователь должен иметь разрешение ALTER на таблицу или представление;</span><span class="sxs-lookup"><span data-stu-id="59e4d-114">The user has ALTER permission on the table or view.</span></span>  
  
-   <span data-ttu-id="59e4d-115">пользователь должен быть владельцем таблицы или индексированного представления или членом одной из следующих ролей: предопределенная роль сервера **sysadmin** , предопределенная роль базы данных **db_owner** или предопределенная роль базы данных **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="59e4d-115">The user be the table or indexed view owner, or a member of one of the following roles: **sysadmin** fixed server role, **db_owner** fixed database role, or the **db_ddladmin** fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="59e4d-116">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="59e4d-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-statistics"></a><span data-ttu-id="59e4d-117">Изменение статистики</span><span class="sxs-lookup"><span data-stu-id="59e4d-117">To modify statistics</span></span>  
  
1.  <span data-ttu-id="59e4d-118">В **обозревателе объектов**щелкните значок «плюс», чтобы развернуть базу данных, в которой нужно изменить статистику.</span><span class="sxs-lookup"><span data-stu-id="59e4d-118">In **Object Explorer**, click the plus sign to expand the database in which you want to modify a statistic.</span></span>  
  
2.  <span data-ttu-id="59e4d-119">Чтобы развернуть папку **Таблицы** , щелкните значок «плюс».</span><span class="sxs-lookup"><span data-stu-id="59e4d-119">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="59e4d-120">Щелкните значок «плюс», чтобы развернуть таблицу, в которой нужно изменить статистику.</span><span class="sxs-lookup"><span data-stu-id="59e4d-120">Click the plus sign to expand the table in which you want to modify a statistic.</span></span>  
  
4.  <span data-ttu-id="59e4d-121">Щелкните значок «плюс», чтобы развернуть папку **Статистика** .</span><span class="sxs-lookup"><span data-stu-id="59e4d-121">Click the plus sign to expand the **Statistics** folder.</span></span>  
  
5.  <span data-ttu-id="59e4d-122">Щелкните правой кнопкой мыши объект статистики, который нужно изменить, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="59e4d-122">Right-click the statistics object that you wish to modify and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="59e4d-123">В диалоговом окне **Свойства статистики —** *имя_статистики* на странице **Общие** нажмите кнопку **Добавить**, **Удалить**, **Переместить вверх**, **Переместить вниз** либо любое их сочетание, чтобы изменить свойства статистики.</span><span class="sxs-lookup"><span data-stu-id="59e4d-123">In the **Statistics Properties -** *statistics_name* dialog box, on the **General** page, click **Add**, **Remove**, **Move Up**, or **Move Down**, or any combination, to alter the properties of the statistics.</span></span> <span data-ttu-id="59e4d-124">Имейте в виду, что положение столбца в сетке **Столбцы статистики** может оказывать значительное влияние на полезность статистики.</span><span class="sxs-lookup"><span data-stu-id="59e4d-124">Remember that a column's location within the **Statistics Columns** grid can substantially impact the usefulness of the statistics.</span></span>  
  
7.  <span data-ttu-id="59e4d-125">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="59e4d-125">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="59e4d-126">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="59e4d-126">Using Transact-SQL</span></span>  
 <span data-ttu-id="59e4d-127">**Изменение статистики**</span><span class="sxs-lookup"><span data-stu-id="59e4d-127">**To modify statistics**</span></span>  
  
 <span data-ttu-id="59e4d-128">Эту задачу нельзя выполнить с помощью инструкций Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="59e4d-128">This task cannot be performed using Transact-SQL statements.</span></span> <span data-ttu-id="59e4d-129">Чтобы изменить статистику с помощью Transact-SQL, нужно удалить существующую статистику и создать ее повторно с новыми атрибутами.</span><span class="sxs-lookup"><span data-stu-id="59e4d-129">To modify statistics using Transact-SQL, you must first delete the existing statistic and then re-create it with new attributes.</span></span>  
  
 <span data-ttu-id="59e4d-130">Дополнительные сведения см. в статьях [DROP STATISTICS (Transact-SQL)](/sql/t-sql/statements/drop-statistics-transact-sql) и [CREATE STATISTICS (Transact-SQL)](/sql/t-sql/statements/create-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="59e4d-130">For more information, see [DROP STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-statistics-transact-sql) and [CREATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-statistics-transact-sql).</span></span>  
  
  

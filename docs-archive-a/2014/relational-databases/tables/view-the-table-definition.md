---
title: Просмотр определения таблицы | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- showing table properties
- displaying table properties
- tables [SQL Server], properties
- viewing table properties
ms.assetid: 1865fb7c-f480-4100-9007-df5364cd002a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 53170a78a104bfce4b4e4177015461f2eb9093e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669341"
---
# <a name="view-the-table-definition"></a><span data-ttu-id="7a597-102">Просмотр определения таблицы</span><span class="sxs-lookup"><span data-stu-id="7a597-102">View the Table Definition</span></span>
  <span data-ttu-id="7a597-103">Отобразить свойства таблицы можно в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] при помощи [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a597-103">You can display properties for a table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="7a597-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="7a597-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7a597-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="7a597-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7a597-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="7a597-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7a597-107">**Отображение свойств таблицы с использованием:**</span><span class="sxs-lookup"><span data-stu-id="7a597-107">**To display table properties, using:**</span></span>  
  
     [<span data-ttu-id="7a597-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7a597-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7a597-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7a597-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7a597-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="7a597-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7a597-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="7a597-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7a597-112">Permissions</span><span class="sxs-lookup"><span data-stu-id="7a597-112">Permissions</span></span>  
 <span data-ttu-id="7a597-113">Просматривать свойства таблицы может только владелец таблицы или лицо, получившее разрешения на таблицу.</span><span class="sxs-lookup"><span data-stu-id="7a597-113">You can only see properties in a table if you either own the table or have been granted permissions to that table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7a597-114">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7a597-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-show-table-properties-in-the-properties-window"></a><span data-ttu-id="7a597-115">Отображение свойств таблицы в окне «Свойства»</span><span class="sxs-lookup"><span data-stu-id="7a597-115">To show table properties in the Properties window</span></span>  
  
1.  <span data-ttu-id="7a597-116">В обозревателе объектов выберите таблицу, для которой необходимо просмотреть свойства.</span><span class="sxs-lookup"><span data-stu-id="7a597-116">In Object Explorer, select the table for which you want to show properties.</span></span>  
  
2.  <span data-ttu-id="7a597-117">Щелкните таблицу правой кнопкой мыши и в контекстном меню выберите пункт **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="7a597-117">Right-click the table and choose **Properties** from the shortcut menu.</span></span> <span data-ttu-id="7a597-118">Дополнительные сведения см. в статье [Table Properties](table-properties-ssms.md).</span><span class="sxs-lookup"><span data-stu-id="7a597-118">For more information, see [Table Properties](table-properties-ssms.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7a597-119">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7a597-119">Using Transact-SQL</span></span>  
  
#### <a name="to-show-table-properties"></a><span data-ttu-id="7a597-120">Отображение свойств таблицы</span><span class="sxs-lookup"><span data-stu-id="7a597-120">To show table properties</span></span>  
  
1.  <span data-ttu-id="7a597-121">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a597-121">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7a597-122">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="7a597-122">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7a597-123">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="7a597-123">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="7a597-124">В примере возвращаются все столбцы из представления каталога `sys.tables` для указанного объекта.</span><span class="sxs-lookup"><span data-stu-id="7a597-124">The example returns all columns from the `sys.tables` catalog view for the specified object.</span></span>  
  
    ```  
    SELECT * FROM sys.tables  
    WHERE object_id = 1973582069;  
  
    ```  
  
 <span data-ttu-id="7a597-125">Дополнительные сведения см. в разделе [sys.tables (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-tables-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7a597-125">For more information, see [sys.tables &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-tables-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  

---
title: Изменение порядка столбцов в таблице | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- columns [SQL Server], change order in a table
- column order, change
ms.assetid: cd99ef56-9085-431a-a0fc-58e7add5399f
author: stevestein
ms.author: sstein
ms.openlocfilehash: d162f9dc793ceb9ea423d94922f7358f1729712e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664100"
---
# <a name="change-column-order-in-a-table"></a><span data-ttu-id="fb0cc-102">Изменение порядка столбцов в таблице</span><span class="sxs-lookup"><span data-stu-id="fb0cc-102">Change Column Order in a Table</span></span>
  <span data-ttu-id="fb0cc-103">В [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] порядок столбцов можно изменить в конструкторе таблиц с использованием [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb0cc-103">You can change the order of columns in Table Designer in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="fb0cc-104">Изменение порядка столбцов в таблицы влияет на коды и приложения, которые зависят от определенного порядка столбцов.</span><span class="sxs-lookup"><span data-stu-id="fb0cc-104">Changing the column order of a table may affect code and applications that depend on the specific order of columns.</span></span> <span data-ttu-id="fb0cc-105">Это касается запросов, представлений, хранимых процедур, определяемых пользователем функций и клиентских приложений.</span><span class="sxs-lookup"><span data-stu-id="fb0cc-105">These include queries, views, stored procedures, user-defined functions, and client applications.</span></span> <span data-ttu-id="fb0cc-106">Внимательно рассмотрите любые изменения, которые необходимо сделать со столбцом таблицы.</span><span class="sxs-lookup"><span data-stu-id="fb0cc-106">Carefully consider any changes you want to make to column order before making it.</span></span> <span data-ttu-id="fb0cc-107">Рекомендуется указывать порядок, в котором возвращаются столбцы, на уровне приложения и запроса.</span><span class="sxs-lookup"><span data-stu-id="fb0cc-107">Best practice is to specify the order in which the columns are returned at the application and query level.</span></span> <span data-ttu-id="fb0cc-108">Не следует предполагать, что SELECT \* будет возвращать все столбцы в ожидаемом порядке, основанном на порядке их определения в таблице.</span><span class="sxs-lookup"><span data-stu-id="fb0cc-108">You should not rely on the use of SELECT \* to return all columns in an expected order based on the order in which they are defined in the table.</span></span> <span data-ttu-id="fb0cc-109">Всегда указывайте столбцы в запросах и приложениях по именам в том порядке, в котором они должны следовать.</span><span class="sxs-lookup"><span data-stu-id="fb0cc-109">Always specify the columns by name in your queries and applications in the order in which you would like them to appear.</span></span>  
  
 <span data-ttu-id="fb0cc-110">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="fb0cc-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="fb0cc-111">**Изменение порядка столбцов с помощью следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="fb0cc-111">**To change the column order, using:**</span></span>  
  
     [<span data-ttu-id="fb0cc-112">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fb0cc-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="fb0cc-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fb0cc-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="fb0cc-114">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fb0cc-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-the-column-order"></a><span data-ttu-id="fb0cc-115">Изменение порядка столбцов</span><span class="sxs-lookup"><span data-stu-id="fb0cc-115">To change the column order</span></span>  
  
1.  <span data-ttu-id="fb0cc-116">В **обозревателе объектов**щелкните правой кнопкой мыши таблицу со столбцами, которые нужно переупорядочить, и выберите пункт **Конструктор**.</span><span class="sxs-lookup"><span data-stu-id="fb0cc-116">In **Object Explorer**, right-click the table with columns you want to reorder and click **Design**.</span></span>  
  
2.  <span data-ttu-id="fb0cc-117">Выберите окно, находящееся слева от названия столбца, который нужно переупорядочить.</span><span class="sxs-lookup"><span data-stu-id="fb0cc-117">Select the box to the left of the column name that you want to reorder.</span></span>  
  
3.  <span data-ttu-id="fb0cc-118">Перетащите столбец в другое местоположение внутри таблицы.</span><span class="sxs-lookup"><span data-stu-id="fb0cc-118">Drag the column to another location within the table.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="fb0cc-119">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fb0cc-119">Using Transact-SQL</span></span>  
 <span data-ttu-id="fb0cc-120">**Изменение порядка столбцов**</span><span class="sxs-lookup"><span data-stu-id="fb0cc-120">**To change the column order**</span></span>  
  
 <span data-ttu-id="fb0cc-121">Эту задачу нельзя выполнить с помощью инструкций Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="fb0cc-121">This task cannot be performed using Transact-SQL statements.</span></span>  
  
###  <a name="TsqlExample"></a>  

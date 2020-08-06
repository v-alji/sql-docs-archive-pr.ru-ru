---
title: Типы курсоров | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, cursors
- ODBC applications, cursors
- cursors [ODBC], types
- ODBC cursors, types
ms.assetid: 3a916cc7-f352-42cb-8b83-f78e06cef991
author: rothja
ms.author: jroth
ms.openlocfilehash: 6937dbb9ce42cd5631201e0c97be42b211742ada
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657790"
---
# <a name="cursor-types"></a><span data-ttu-id="07654-102">Типы курсоров</span><span class="sxs-lookup"><span data-stu-id="07654-102">Cursor Types</span></span>
  <span data-ttu-id="07654-103">ODBC определяет четыре типа курсоров, поддерживаемых корпорацией Майкрософт [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] драйвером ODBC для собственного клиента.</span><span class="sxs-lookup"><span data-stu-id="07654-103">ODBC defines four cursor types supported by Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span> <span data-ttu-id="07654-104">Эти курсоры изменяют возможность обнаружения изменений в результирующем наборе и используемых ими ресурсах, таких как память и пространство в **базе данных tempdb**.</span><span class="sxs-lookup"><span data-stu-id="07654-104">These cursors vary in their ability to detect changes to the result set and in the resources they consume, such as memory and space in **tempdb**.</span></span> <span data-ttu-id="07654-105">Курсор может обнаружить изменения в строках только при попытках повторной выборки этих данных; не существует способа для источника данных известить курсор об изменениях в текущих выбранных строках.</span><span class="sxs-lookup"><span data-stu-id="07654-105">A cursor can detect changes to rows only when it tries to refetch those rows; there is no way for the data source to notify the cursor of changes to the currently fetched rows.</span></span> <span data-ttu-id="07654-106">На способность курсора обнаруживать изменения, которые не были внесены через курсор, также влияет уровень изоляции транзакций.</span><span class="sxs-lookup"><span data-stu-id="07654-106">A cursor's ability to detect changes that were not made through the cursor is also influenced by the transaction isolation level.</span></span>  
  
 <span data-ttu-id="07654-107">Существует четыре типа курсоров ODBC, поддерживаемых [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="07654-107">These are the four ODBC cursor types supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="07654-108">Однопроходные курсоры не поддерживают прокрутку, они поддерживают только последовательную выборку строк от начала курсора до его конца.</span><span class="sxs-lookup"><span data-stu-id="07654-108">Forward-only cursors do not support scrolling; they only support fetching rows serially from the start to the end of the cursor.</span></span>  
  
-   <span data-ttu-id="07654-109">Статические курсоры создаются в **базе данных tempdb** при открытии курсора.</span><span class="sxs-lookup"><span data-stu-id="07654-109">Static cursors are built in **tempdb** when the cursor is opened.</span></span> <span data-ttu-id="07654-110">Они всегда отображают результирующий набор точно в том виде, в котором он был при открытии курсора.</span><span class="sxs-lookup"><span data-stu-id="07654-110">They always display the result set as it was when the cursor was opened.</span></span> <span data-ttu-id="07654-111">Они никогда не отражают изменения в данных.</span><span class="sxs-lookup"><span data-stu-id="07654-111">They never reflect changes to the data.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="07654-112">статические курсоры всегда доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="07654-112">static cursors are always read-only.</span></span> <span data-ttu-id="07654-113">Так как статический серверный курсор создается в виде рабочей таблицы в **базе данных tempdb**, размер результирующего набора курсора не может превышать максимальный размер строки, разрешенный [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="07654-113">Because a static server cursor is built as a work table in **tempdb**, the size of the cursor result set cannot exceed the maximum row size allowed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="07654-114">Курсоры, управляемые набором ключей, имеют членство и порядок строк в результирующем наборе, установленные при открытии курсора.</span><span class="sxs-lookup"><span data-stu-id="07654-114">Keyset-driven cursors have the membership and order of rows in the result set fixed when the cursor is opened.</span></span> <span data-ttu-id="07654-115">Изменения в неключевых столбцах видимы через курсор.</span><span class="sxs-lookup"><span data-stu-id="07654-115">Changes to nonkey columns are visible through the cursor.</span></span>  
  
-   <span data-ttu-id="07654-116">Динамические курсоры — это противоположность статических курсоров.</span><span class="sxs-lookup"><span data-stu-id="07654-116">Dynamic cursors are the opposite of static cursors.</span></span> <span data-ttu-id="07654-117">Динамические курсоры отражают все изменения строк в результирующем наборе.</span><span class="sxs-lookup"><span data-stu-id="07654-117">Dynamic cursors reflect all changes made to the rows in their result set.</span></span> <span data-ttu-id="07654-118">Значения типа данных, порядок и членство строк в результирующем наборе могут меняться для каждой выборки.</span><span class="sxs-lookup"><span data-stu-id="07654-118">The data values, order, and membership of the rows in the result set can change on each fetch.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07654-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="07654-119">See Also</span></span>  
 [<span data-ttu-id="07654-120">Использование курсоров &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="07654-120">Using Cursors &#40;ODBC&#41;</span></span>](using-cursors-odbc.md)  
  
  
